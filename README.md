md-mapping
==========

The files in this repository define semantic mappings to convert from
community specific metadata schemata into the internal schema of the
Joint Metadata Domain (DASISH Task 5.4).

The mapping software that uses these files is in a separate repository
at https://github.com/TheLanguageArchive/md-mapper from where the
deployment script updates it automatically.


# Deployment instructions

To follow these steps, you need the following: Perl, Maven, JDK 7, git
(ideally version 1.7.10 or later) and tar.

1. Choose an empty directory, which will become the working directory,
and enter it.
2. ````git clone http://github.com/TheLanguageArchive/md-mapper.git````
3. ````git clone https://github.com/DASISH/md-mapping.git````
4. ````cd md-mapper````
5. ````./update-deploy.sh -f````

On subsequent invocations of update-deploy.sh don't use the -f flag.

The above is the simplest possible set-up. Different directory
structures are possible; see the update-deploy script for available
parameters.
