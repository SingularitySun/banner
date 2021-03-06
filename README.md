banner
======

A fork of the BANNER Named Entity Recognizer from Arizona State.
This is based on a CVS snapshot from 11/27/2014.

Installation instructions
-------------------------

* Add `BANNER_DATA` to your environment pointing to the absolute path to the `banner_data/` directory in this package.
* Optionally, only if changes are made to the source code in this package, run: `sbt publish-local`.

Changes to the original code
----------------------------

The following changes were made to the original Banner code:
* Removed the following packages from `src`: `test`, `edu.umass.cs.mallet.projects`. They are not necessary for this project.
* Moved the code from `src/` to `src/main/java/`.
* Moved all data resources (`dict/`, `nlpdata/`, `regex.txt`, `banner.properties`) under the new `banner_data/` directory. Adjusted `banner.properties` to point to the new locations.
* Trained a model using all BC2 training data, and saved it as `banner_data/banner_model.dat`.
* Added the `BannerWrapper` class, which creates a Banner NER with default options, based on the `banner_data` directory.
* Added the `BannerProperties.load(Properties properties)` method, which is needed by the `BannerWrapper` class.

Authors
-------

BANNER was created by Bob Leaman and is advised by Dr. Graciela Gonzalez, both members of the BioAI lab at Arizona State University. See the Banner project web page for more details: http://banner.sourceforge.net/. This project is distributed under the BANNER original license (see license.txt).

The packaging as a sbt project was implemented by Mihai Surdeanu and Marco Valenzuela.
