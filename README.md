# Introduction to the Course Materials Development Templates

This contains the template for creating SUSE Training slides, lecture manuals and lab manuals.  All templates are for use with LibreOffice.

## Lab Manual

Lab manuals are created using a modular approach. The lab manual itself is a master document (.odm) file. Each exercise is its own separate document and each section divider is its own separate document. 

The section breaks documents and the exercise documents are then linked into the lab manual master document in the navigator pane to create the actual manual. 

The section break documents and the exercise documents contain the styles used when generating the TOC. These styles are also used to automatically generate all section numbers and exercise numbers are when the lab manual master document TOC is generated/updated.

A best practice is to create a directory named **lab** and place the lab manual master document in this directory. Then create a subdirectory of the lab folder named **labs**. In the directory you place all of your section and exercise documents. The idea is that this directory is a flat namespace and linking the individual documents into the lab manual master document provides the organizational overlay. You should also not put the section or exercise numbers in the file names of the section break and exercise documents. This will allow for easy reordering of these files when they are linked into the master document without requiring the renaming of the files. (Trust me on this. It really makes things much easier in the long run if you do this. No, really. Trust me.)

(See the example lab manual provided.)

**Example directory structure:**

```
course_name/
           |-lab/
                |-LAB_MANUAL-course_name.odm
                |
                |-labs/
                      |-SECTION-section_name_A.odt
                      |-SECTION-section_name_B.odt
                      |-EXERCISE-exercise_name_A.odt
                      |-EXERCISE-exercise_name_B.odt
                      |-EXERCISE-exercise_name_C.odt

```

## Slide Decks

A separate slide deck should be created for each section of the course. The sections decks are then subdivided into (optionally) Topics and (required) Objectives. Divider slides for each of these is provided in the template.



## Lecture Manual

The lecture manual is created by copying the contents of each of the sections decks into the Lecture Manual deck between the Table of Contents slide and the SUSE graphic splash slide.

The table of contents must be manually edited on the Notes View of the Table of Contents slide.

The Notes View of the slides in the slide decks and lecture manual deck are formatted so that a PDF manual can be generated of the lecture manual. For this reason it is strongly encouraged to create graphic orient slides in the Slide View and put any large amounts of text in the Notes View of the slide. This will allow for a better lecture manual to be generated. It will also improve your slides as slides are more of a graphical medium than a textual medium.

If you have notes that are too long to fit in the provided notes section of the Notes View of a slide, a special "notes only" slide has been provided in the section slide deck template. Put a copy of this slide following the slide that's notes are too long an then, in the Notes View of the "notes only" slide, put the additional text that won't fit on the original slide's notes section. When the manual is generate the notes only slides will only display text and not the "slide" portion of the slide.