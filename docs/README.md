# Jens Edlund's writing

This is based on the SBTal standard template, but we
place each specific top-level adoc file in its own directory
under `/docs/WORK/`, where `WORK` is a short version 
of the name of the work. Full sections of the writing 
are placed in that same directory, but generic texts 
are better places in the generic include directory.
Top level files may load their own config (that would be 
placed in their main directory, but this should start out
loading the general config (which it can then override).

To build, start by checking the `repoversion` attribute
in `/docs/aciidoc/attributes/config.adoc` - it should
be set to the version you're about to release. If it 
isn't, set it commit and push.

In this directory (`/docs`), execute 

```
docker run -ir -v "$PWD":/adoc --rm sprakbankental/os bash
cd /adoc/asciidocs
adocs *.adoc
adocs-pdf *.adoc
exit
```

This will build HTML version in `/docs/html/` and PDF 
versions in `/docs/pdf/`. 

Commit and push the documents, and you're done.

There is ususally no need to commit documentaiton between 
releases. You can build them locally following the 
instruction above, to see what your updates look like, 
but it is sufficient to check in the files in 
`/docs/adocs/` and leave the HTML and PDF checkins to
the moments before the next new release.

