# Introduction to the Course Materials Development Templates

This contains the template for creating SUSE Training slides, lecture manuals and lab manuals.  All templates are for use with LibreOffice.

## Styles

A set of formatting styles have been created to provide for a uniform look and feel and to make the materials easier for the student to understand.

A pre-defined set of hot-keys has been specified for quick applications of these styles to text in the lecture manual. This can be imported into to LibreOffice Writer using the provided `LibreOffice_formatting_hotkeys.cfg` file.

LibreOffice Writer: **Tools -> Customize... -> Keyboard -> Load** 

(Note that these styles and hotkeys only work in LibreOffice Writer. You must manually create this formatting when working in your slides decks in LibreOffice Impress.)

The styles used are listed below along with their hotkeys:

```
LibreOffice Formatting HotKeys:
---------------------------------------------

Use                             Format          Style               Hotkey
---                             ------          -----               ------
Emphasis                        Bold            SUSE-emphasis       Ctrl+Shift+E
Light Emphasis                  Bold Gray       SUSE-emphasis.light Ctrl+Shift+Q
Warning                         Bold Red        SUSE-warning        Ctrl+Shift+W
Lab Variable                    Bold+Italic     SUSE-variable       Ctrl+Shift+V
Console/file contents           Black+monospace SUSE-monospace      Ctrl+Shift+M
Commands                        Blue+monospace  SUSE-command        Ctrl+Shift+C
Filenames and paths             Green+monospace SUSE-filename       Ctrl+Shift+N

extra space before/after text   n/a             SUSE-extra_spacing  Ctrl+Shift+S
```

A description of how the styles should be used is on the **Documentation Conventions** page on the lab manual master document.

(Also see the example lab manual provided.)

## Fonts

To make cross platform/OS development easier and to provide consistent output, two special fonts that are used in the course manuals. These fonts are the Google's **Arimo** font (an Arial variant) used for all normal text and Google's **AnonymousPro** font used for all monospace text. These fonts are provided in this repository but can also be installed via RPM in SUSE Linux distributions.

Ensure that these fonts are installed before working with the templates.

## Graphics

There are two graphics that are provided for use when creating Note/Tip/Warning/Important block in the lab manual: `lightbulb-yellow-gray.png`, `warning-red-triangle.png`

These graphics should reside an a subdirectory of your course development directory named **graphics**.

Any other graphics such as screenshots should also reside in the **graphics** directory or subdirectories of the **graphics** directory.

**Example directory structure:**

```
course_name/
           |-graphics/
                     |-lightbulb-yellow-gray.png
                     |-warning-red-triangle.png


```

## Lab Manual

Lab manuals are created using a modular approach. The lab manual itself is a master document (.odm) file. Each exercise is its own separate document and each section divider is its own separate document. 

The section breaks documents and the exercise documents are then linked into the lab manual master document in the navigator pane to create the actual manual. 

The section break documents and the exercise documents contain the styles used when generating the TOC. These styles are also used to automatically generate all section numbers and exercise numbers are when the lab manual master document TOC is generated/updated.

A best practice is to create a directory named **lab** and place the lab manual master document in this directory. Then create a subdirectory of the lab folder named **labs**. In the directory you place all of your section and exercise documents. The idea is that this directory is a flat namespace and linking the individual documents into the lab manual master document provides the organizational overlay. You should also not put the section or exercise numbers in the file names of the section break and exercise documents. This will allow for easy reordering of these files when they are linked into the master document without requiring the renaming of the files. (Trust me on this. It really makes things much easier in the long run if you do this. No, really. Trust me.)

If you have a section that does not have any corresponding exercises, put a copy of the `NO_EXERCISES.odt` file in the lab directory along with the lab manual .odm file and then link the NO_EXERCISES file into the lab manual in the place the there would be exercises. This will inform the student that there are not exercises for that section and will also show this in the TOC.

**Example directory structure:**

```
course_name/
           |-graphics/
           |         |-lightbulb-yellow-gray.png
           |         |-warning-red-triangle.png
           |
           |-lab/
                |-LAB_MANUAL-course_name.odm
                |-NO_EXERCISES.odt
                |
                |-labs/
                      |-SECTION-section_name_A.odt
                      |-SECTION-section_name_B.odt
                      |-EXERCISE-exercise_name_A.odt
                      |-EXERCISE-exercise_name_B.odt
                      |-EXERCISE-exercise_name_C.odt

```

(See the example lab manual provided.)


## Slide Decks

A separate slide deck should be created for each section of the course. The sections decks are then subdivided into (optionally) Topics and (required) Objectives. Divider slides for each of these is provided in the template.

In most cases you will only need the Section to be subdivided into Objectives. In some cases, where the Section contains a large number of Objectives and these Objectives can be grouped together into similar Topic areas, you can subdivide the Section into Topics and then put the corresponding Objectives under each Topic. If you do not need Topics then remove the Topic oriented slides from your Section decks. (You will notice that the section oriented dividers and slides are one color, the Topic oriented dividers and slides are another color and the Objective oriented dividers and slides are another color still.)

All section oriented slides should reside in a directory named slides in your course development directory.

**Example directory structure:**

```
course_name/
           |-graphics/
           |         |-lightbulb-yellow-gray.png
           |         |-warning-red-triangle.png
           |
           |-slides/
           |       |-SECTION-01-section_title.odp
           |       |-SECTION-02-section_title.odp
           |       |-SECTION-03-section_title.odp
           |
           |-lab/
                |-LAB_MANUAL-course_name.odm
                |-NO_EXERCISES.odt
                |
                |-labs/
                      |-SECTION-section_name_A.odt
                      |-SECTION-section_name_B.odt
                      |-EXERCISE-exercise_name_A.odt
                      |-EXERCISE-exercise_name_B.odt
                      |-EXERCISE-exercise_name_C.odt

```

## Lecture Manual

The lecture manual is created by copying the contents of each of the sections decks into the Lecture Manual deck between the Table of Contents slide and the SUSE graphic splash slide.

The table of contents must be manually edited on the Notes View of the Table of Contents slide.

The Notes View of the slides in the slide decks and lecture manual deck are formatted so that a PDF manual can be generated of the lecture manual. For this reason it is strongly encouraged to create graphic orient slides in the Slide View and put any large amounts of text in the Notes View of the slide. This will allow for a better lecture manual to be generated. It will also improve your slides as slides are more of a graphical medium than a textual medium.

If you have notes that are too long to fit in the provided notes section of the Notes View of a slide, a special "notes only" slide has been provided in the section slide deck template. Put a copy of this slide following the slide that's notes are too long an then, in the Notes View of the "notes only" slide, put the additional text that won't fit on the original slide's notes section. When the manual is generate the notes only slides will only display text and not the "slide" portion of the slide.

The lecture manual slide deck should reside in a lecture subdirectory of your course development directory.

**Example directory structure:**

```
course_name/
           |-graphics/
           |         |-lightbulb-yellow-gray.png
           |         |-warning-red-triangle.png
           |
           |-slides/
           |       |-SECTION-01-section_title.odp
           |       |-SECTION-02-section_title.odp
           |       |-SECTION-03-section_title.odp
           |
           |-lecture/
           |        |-LECTURE_MANUAL-course_name.odp
           |
           |-lab/
                |-LAB_MANUAL-course_name.odm
                |-NO_EXERCISES.odt
                |
                |-labs/
                      |-SECTION-section_name_A.odt
                      |-SECTION-section_name_B.odt
                      |-EXERCISE-exercise_name_A.odt
                      |-EXERCISE-exercise_name_B.odt
                      |-EXERCISE-exercise_name_C.odt
```

## Course Manual PDFs

When the course manual development is complete the lab manual and lecture manual should be exported as PDF files. These files should reside in a subdirectory of your course development directory named pdf.

**Example directory structure:**

```
course_name/
           |-graphics/
           |         |-lightbulb-yellow-gray.png
           |         |-warning-red-triangle.png
           |
           |-slides/
           |       |-SECTION-01-section_title.odp
           |       |-SECTION-02-section_title.odp
           |       |-SECTION-03-section_title.odp
           |
           |-lecture/
           |        |-LECTURE_MANUAL-course_name.odp
           |
           |-lab/
           |    |-LAB_MANUAL-course_name.odm
           |    |-NO_EXERCISES.odt
           |    |
           |    |-labs/
           |          |-SECTION-section_name_A.odt
           |          |-SECTION-section_name_B.odt
           |          |-EXERCISE-exercise_name_A.odt
           |          |-EXERCISE-exercise_name_B.odt
           |          |-EXERCISE-exercise_name_C.odt
           |
           |-pdf/
                |-LAB_MANUAL-course_name.pdf
                |-LECTURE_MANUAL-course_name.pdf
```

When generating the Lecture manual PDF from the Lecture Manual slide deck, ensure that **Export notes pages** and **Export only notes pages** are selected: 

**File -> Export as PDF** (**Export notes pages**: checked, **Export only notes pages**: checked)


# HowTo Videos
(forthcoming)





