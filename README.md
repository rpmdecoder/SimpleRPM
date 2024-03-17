# SimpleRPM
 RPM Utility that simplifies the creation of an rpm

This is a downloadable rpm which contains a utility for creating an rpm. 
After downloading and installing, add the following to your PATH 
'/var/opt/tgsrpm/scripts/rpm_utils'. Then type rpmgo. If not updating 
your PATH, then just type /var/opt/tgsrpm/scripts/rpm_utils/rpmgo
This utility is used to create a custom .spec file, which only 
needs 2 questions answered. Once the .spec file is created, 
run rpmbuild against it. 

This utility builds .spec files in a different way. Don't have to .tar 
the source. Don't have to have all your files in the same directories
that mirror the final destination. For anyone new to building rpms', 
it can get frustrating trying to figure out the (complex) flow needed
to build an rpm. This utility greatly simplifies everything for anyone
trying to get their first rpm out the door. 

A large number of developers just need to put 'files' on the server and 
want to use an .rpm package to deliver those files. They basically say
'I want these set of scripts' to go to 'this directory'. This utility
takes the approach of using those 2 pieces of information as all it needs
to build the necessary rpm package. 

[Sample]

My sources are located at: 

/var/opt/tgsrpm/SOURCES/finalprojct/script1.sh

/var/opt/tgsrpm/SOURCES/finalprojct/script2.sh

They need to look like this on the server:

script1.sh             /var/custom/utils/scripts       root:fxuser      755

script2.sh             /var/custom/utils/scripts       root:fxuser      755


Put those 2 pieces of information in the .spec file and it will
create the RPM to deploy those 2 files. 
