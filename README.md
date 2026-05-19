# Embracing Respiration-Induced Motion in Cardiovascular MRI

LaTeX files for my PhD thesis. Published manuscript available online at the [UW Madison Library](https://digital.library.wisc.edu/1711.dl/DS37JIXEDCBSB8D).

## Abstract

Respiratory motion is a well-known complicating factor in Magnetic Resonance Imaging (MRI), especially when imaging elements of the cardiovascular system. Periodic motion of the lungs during the respiratory cycle affects the torso and abdomen, which impacts imaging of the heart, aorta, liver, and other organs and vessels. The resulting motion artifacts, which appear in traditional Cartesian imaging as distinct replicas in the phase-encoding direction, negatively impact the quality of diagnostic information that can be gleaned from MR images. One common way to mitigate motion artifacts in clinical imaging is to instruct subjects to hold their breath for the duration of the acquisition. However, breath-holds can be infeasible for long acquisitions or for subjects who have difficulty holding their breaths. Alternatively, the acquisition can be gated such that data are only acquired during a single phase of respiration, but this can lead to considerable reductions in scan efficiency. Additionally, respiration has important physiological consequences, and there is merit to exploring the impacts of respiration and respiration-induced motion on the cardiovascular system.

In this thesis, I seek to implement and optimize methods for not only mitigating the effects of respiration in cardiovascular MRI, thereby enabling otherwise impossible imaging, but also to utilize information from the respiratory cycle to improve data efficiency, reduce scan time, and extract valuable diagnostic information. This will be performed in three different scientific contexts, each focusing on a different anatomical region: (1) validation and improvement of radial 2D Phase Contrast (2DPC) MRI for measuring pulse wave velocity in the aorta with sequential and simultaneous multi-slice acquisitions; (2) acceleration of the acquisition of radial, free-breathing 4D flow MRI in the portal venous system; and (3) implementation of a 5D MRI approach for resolving cardiac and respiratory motion of the heart in radiation therapy treatment planning.

## Compilation

Requires installation of TexLive (2025 or later) for compilation and biber for reference management. Due to accessibility requirements set by the graduate school in April 2026, all dissertations must be properly tagged PDFs to allow for accessibility tools like screen readers to work. In the preamble of the document, there is a conditional `ifFinal` defined along with two values `Finaltrue` and `Finalfalse`. To compile a final version of this document with complete PDF tagging, uncomment `Finaltrue` and compile the document with `lualatex`. However, this compilation is pretty slow, so for drafting purposes uncomment `Finalfalse` instead and compile with `pdflatex`. Note that for references to compile properly, you will need to run biber before compiling, however, biber requires intermediate outputs from the documents to run, so you will need to do something like `pdflatex main` → `biber main` → `pdflatex main` again. You generally only need to do this once while writing though, unless you are clearing your intermediate outputs often or switching between compilers.

```bash
# reference compilation
biber main

# for faster draft compilation
pdflatex -synctex=1 -interaction=nonstopmode -file-line-error -recorder  "main.tex"

# for final compilation with pdf tagging
lualatex -synctex=1 -interaction=nonstopmode -file-line-error -recorder  "main.tex"
```

While you can compile the document standalone, I preferred using the LaTeX Workshop extension in VS Code which allows for convenient management and compilation of the document while writing. Additionally, some useful VS Code extensions I also used include LTeX for spell and grammar checking and Zotero LaTeX for reference autocompletion.
