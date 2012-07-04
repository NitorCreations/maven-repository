Publishing artifacts in this repository
=======================================

This repo is based on [this](http://cemerick.com/2010/08/24/hosting-maven-repos-on-github/) article with the addition of generatiing indexes.

Required steps
--------------

1. Check out this repository into a directory that you will have to specify when you deploy

        $ git clone git clone git@github.com:NitorCreations/maven-repository.git

1. Deploy your artifact with the checked out repo as altDeploymentRepository
    
        $ cd your-project; mvn -DaltDeploymentRepository=releases::default::file:../maven-repository/releases clean deploy

1. Regenerate the index

        $ cd ../maven-repository/.index; mvn install; mvn clean

1. Git-add new stuff and commit

        $ cd ..; git add .; git commit -m "Added vX.Y of your-project"; git push


