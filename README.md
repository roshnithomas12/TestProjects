While running spring boot, in VM arguments specify:

-javaagent:{projectRootPath}/jacocoagent.jar=port=36320,output=tcpserver
 
 after executing tests, execute below scripts
 mvn jacoco:dump@pull-test-data -Dapp.host=localhost -Dapp.port=36320 -Dskip.dump=false
 mvn antrun:run@generate-report -Dskip.int.tests.report=false
# 
