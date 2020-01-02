# ACE 2005 Data Prep

## Description

This project is forked from [mgormley/ace-data-prep](https://github.com/mgormley/ace-data-prep). It ties together numerous tools. It converts from the [ACE
2005 file format](https://catalog.ldc.upenn.edu/LDC2006T06) (.sgm and .apf.xml files) to Concrete. It also
annotates the ACE 2005 data using Stanford CoreNLP and the
chunklink.pl script from CoNLL-2000. The data is the same as that used in (Yu, Gormley, & Dredze, NAACL 2015) and (Gormley, Yu, & Dredze, EMNLP 2015). For project details, please check the files in folder "mgormley/ace-data-prep" or its original [publication](https://github.com/mgormley/ace-data-prep).

## Tips for running [mgormley/ace-data-prep](https://github.com/mgormley/ace-data-prep)

### No rule to make target xxx under Windows environment
If you meet the following exception:

    make: *** No rule to make target '/output/ace-05-comms/CNN_LE_20030504.1200.02-2.concrete', needed by '/output/ace-05-comms-ptb-anno/CNN_LE_20030504.1200.02-2.concrete'. Stop.

You can try to solve it by running [mgormley/ace-data-prep](https://github.com/mgormley/ace-data-prep) on **Linux environment**. 

### Error: Could not find or load main class under Linux remote environment
If you meet the following exception:

    Error: Could not find or load main class edu.jhu.hlt.concrete.stanford.AnnotateTokenizedConcrete；

when running the command

    make LDC_DIR=./data OUT_DIR=./output ace05splits

in a remote linux machine, you can try to solve it by executing this command under a **local Linux machine**

### Error: com.sun.xml.internal.bind.v2.ContextFactory not found
If you meet the following exception:

    Error: com.sun.xml.internal.bind.v2.ContextFactory not found

when running the command

    make LDC_DIR=./data OUT_DIR=./output ace05splits

in a local Linux machine, you can try to solve it by (1) check the version of your java and then (2) if the version is larger than 1.8.x, add the following dependency in **'pom-cs.xml' under [mgormley/ace-data-prep/scripts/maven](https://github.com/mgormley/ace-data-prep/tree/master/scripts/maven)**
    
    <dependency>
       <groupId>com.sun.xml.bind</groupId>
       <artifactId>jaxb-impl</artifactId>
       <version>2.1.2</version>
    </dependency>
    
    <dependency>
       <groupId>javax.xml.bind</groupId>
       <artifactId>jaxb-api</artifactId>
       <version>2.1</version>
    </dependency>
    
## Notation
If you think my tips here are helpful for you, please give me **a star** and feel free to fork this project. 

## Author
Hong Lin: honglin@zju.edu.cn
