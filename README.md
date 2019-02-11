# ONTMAT1
New version of ONTMAT
To test ONTMAT under SEALS platform of OAEI yo must follow the next instructions extracted from sealClienttutorial (https://github.com/DanFaria/OAEI_SealsClient/blob/master/SealsClientTutorial.pdf):

-Please, extract ONTMAT.rar Folder in the directory as (ex F:\temp). 
 
-Then creat file called ONTMAT in the same directory (ex F:\temp). In this file, extract ONTMAT.ZIP and let a copy of ONTMAT.ZIP in (ex F:\temp)

-The jar file seals-omt-validator.jar(http://oaei.ontologymatching.org/2018/seals.html) can be used to check the structure and
content (e.g., correctness of references) of the package.
For that purpose you need to have the tool zipped (ONTMAT.zip is included in ONTMAT.rar).

-Given that in the current working directory there are seals-omt-validator.jar
and ONTMAT.zip, the zipped package can be checked  with the fol-
lowing command:

	java -cp seals-omt-validator.jar eu.sealsproject.platform.res.tool.utils.clients.validation.PackageValidator -v all -r ONTMAT.zip

In case of a successful test, the following output is displayed.
log4j:WARN No appenders could be found for logger+
(eu.sealsproject.platform.res.tool.bundle.factory.impl.DirectoryNormalizer).
log4j:WARN Please initialize the log4j system properly.
Package 'A:\temp\demomatcher-package.zip' is valid
Package structure validation report:
- Tool package configuration: [Passed]
- Binary directory..........: [Passed]
- Configuration directory...: [Passed]
- Library directory.........: [Passed]
Package descriptor validation report:
- PackageConfiguration.............: [Passed]
- DeployCapabilityConfiguration....: [Passed]
+ Shell script configuration:
- Script file 'deploy.bat' found.
- UndeployCapabilityConfiguration..: [Passed]
+ Shell script configuration:
- Script file 'undeploy.bat' found.
- StartStopDependency..............: [Passed]
- StartCapabilityConfiguration.....: [Passed]
+ Shell script configuration:
- Script file 'start.bat' found.
- StopCapabilityConfiguration......: [Passed]
+ Shell script configuration:
- Script file 'stop.bat' found.
- InvokeCapabilityConfiguration....: [Passed]
+ Java application configuration:
- Jar file 'demomatcher-bridge.jar' found.
- Class 'de.unima.ki.demomatcher.seals.MatcherBridge' found.
- Dependencies specified:
+ Dependency   ' lib/demomatcher.jar'  found and valid. 
+ Dependency  ‘lib/owlapi.jar '  found and valid.
+ Dependency  ’lib/ONTMAT.jar'  found and valid.
+ Dependency  ’lib/antlr-2.7.5.jar'  found and valid.
+ Dependency  ’lib/arq.jar'  found and valid.
+ Dependency  ’lib/arq-extra.jar'  found and valid.
+ Dependency  ’lib/axis.jar'  found and valid.
+ Dependency  ’lib/commons-discovery-0.4.jar'  found and valid.
+ Dependency  ’lib/commons-lang-2.0.jar'  found and valid.
+ Dependency  ’lib/commons-logging-1.1.1.jar'  found and valid.
+ Dependency  ’lib/concurrent.jar'  found and valid.
+ Dependency  ’lib/edtftpj-1.5.2.jar'  found and valid.
+ Dependency  ’lib/ekitspell.jar'  found and valid.
+ Dependency  ’lib/icu4j_3_4.jar'  found and valid.
+ Dependency  ’lib/iri.jar'  found and valid.
+ Dependency  ’lib/jcalendar.jar'  found and valid.
+ Dependency  ’lib/jdom.jar'  found and valid.
+ Dependency  ’lib/jep-2.4.0.jar'  found and valid.
+ Dependency  ’lib/json.jar'  found and valid.
+ Dependency  ’lib/junit.jar'  found and valid.
+ Dependency  ’lib/jwnl.jar'  found and valid.
+ Dependency  ’lib/kazuki.jar'  found and valid.
+ Dependency  ’lib/lawrapper.jar'  found and valid.
+ Dependency  ’lib/log4j-1.2.12.jar'  found and valid.
+ Dependency  ’lib/lucene-core-2.3.1.jar'  found and valid.
+ Dependency  ’lib/orphanNodesAlg.jar'  found and valid.
+ Dependency  ’lib/owlapi.jar'  found and valid.
+ Dependency  ’lib/owlsyntax.jar'  found and valid.
+ Dependency  ’lib/protege.jar'  found and valid.
+ Dependency  ’lib/protege-owl.jar'  found and valid.
+ Dependency  ’lib/simmetrics.jar'  found and valid.
+ Dependency  ’lib/gtranslateapi-1.0.jar'  found and valid.
- ShellScriptFileUniqueness........: [Passed]

	In this example the validation has been passed successfully. In case of problems,
they are reported.

-In the SEALS platform the matcher will be executed in a certain folder. To
simulate this behavior for the purpose of doing this test, you first have to set the 
system variable SEALS_HOME to some folder on your machine where you have full
read, write and execution rights. Under Windows use the following command.

A:\temp>set SEALS_HOME=A:\seals\sealshome

If you are using a Unix system you have to type the following:
christian@arnheim:~$ export SEALS_HOME="/home/christian/sealshome"

-Note that this variable is only valid in the same terminal. Please change now the
current directory to the SEALS_HOME directory in order to execute the matcher!
they have prepared a client which connects to the tool via its bridge and executes
its align method as it will be the case when the tool is deployed in the SEALS
platform.

	It is available in the jar file seals-omt-client.jar (https://github.com/DanFaria/OAEI_SealsClient/releases)that contains also
the interfaces to be implemented. The client works directly on the unzipped tool
package, so please unzip ONTMAT.zip tool package before proceeding into A:/temp/ONTMAT).

	To test a confernce data (by the proposed tool ONTMAT) of the SEALS client:
	-a connection to the internet is required to retrieve the input ontologies.
	-you should run it with the following command

	java -jar F:/temp/seals-omt-client.jar F:/temp/ONTMAT -x http://repositories.seals-project.eu/tdrs/ conference conference-v1 F:\results\

If everything is ne and you are connected to the internet, the following messages
are printed to the screen.
>>> Preparing environment ...
>>> All files are copied to SEALS_HOME. Press y to start: y

