To set up QF-Test for imbus TestBench test automation, 
copy the file "itep.jar" and all JAR files from the libs/ 
folder in the iTEP directory to <QF-Test>/plugin/qftest.

NOTE : In case of trial version, copy and paste all above mentioned JAR files to the folder : QF-Test tool-> help(hilfe) -> Info -> Systeminfo -> dir.plugin -> qftest

The files of the TestBench QF-Test wrapper explained:

1) testaut.properties
   user.properties
   These two files are for configuring the basic behavior 
   of the wrapper, as explained in testaut.properties.
   For English version please change the entry "reportFileToExecute" to 
   "[...] report-en.zip" in user.properties.

2) report/report-*.zip
   A sample TestBench export file that can be executed 
   with the wrapper.
   You find a German and English version.

3) suite/TestBench_*.qft
   The implementation of the wrapper. Normally, these files 
   need NOT be modified.

4) suite/demo/CarConfig*.qft
   They (German and English version) are the starting point for running 
   the automated tests and using the TestBench QF-Test wrapper. 
   Both suites need the corresponding report/report*.zip file for test execution. 


Rerun Definition:
We can automatically execute nodes again in the event of an error/ exception. To repeat such failed test-cases / nodes immediately, 
use the following doctag in the 'Comment (Bemerkung)' attribute for each executable node (or for whole Testsuite ) in the test suite of QF-Test Tool :
"
@rerun attempts=3;errorlevel>=ERROR;newerrorlevel=WARNING;
          handler=handlers.errorhandler    
"
(NOTE : With errorlevel = ERROR, the node will only be executed again in case of errors, with errorlevel> = ERROR in case of errors and exceptions.)
For more details refer to provided reference manual /Program Files/QFS/QF-Test/qftest-4.6.0/doc/manual/de/user_rerun.html#usec_rerun


For TestBench specific questions, please address the imbus 
TestBench support at support@imbus.de

