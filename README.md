# utl_unfreeze_sas
Occasionally the SAS editor may freeze. This will unfreeze the editor

    ```  SAS editor frozen (frozen SAS issue)  ```
    ```    ```
    ```  This seems to work 99.99% of the time?  ```
    ```    ```
    ```  Hit F8 and then  highlight the inserted line and hit right mouse button RMB.  ```
    ```    ```
    ```  keydef  RMB     log;clear;out;clear;pgm;submit;home;rec;home;log;z;z;  ```
    ```  keydef "F8"     '~;;;;/*''*/ *);*};*];*/;/*"*/;%mend;run;quit;%end;end;run;endcomp;%utlfix;';  ```
    ```    ```
    ```    ```
    ```  Paste the keydef command below into the old text editor 'clean' command line.  ```
    ```  Not the command bar or EE dual command lines?  ```
    ```  This works for me, but you may need to type into keys window.  ```
    ```  If you type it in make sure you change /*''*/ to /*'*/.  ```
    ```    ```
    ```  keydef "F8" '~;;;;/*''*/ *);*};*];*/;/*"*/;%mend;run;quit;%end;end;run;endcomp;%utlfix;';  ```
    ```    ```
    ```  Put the macro below in your autocall library.  ```
    ```  Turn on 'options cmdmac'  ```
    ```    ```
    ```  %macro utlfix(dum);  ```
    ```    ```
    ```  * fix frozen sas and restore to invocation ;  ```
    ```   dm "odsresults;clear;";  ```
    ```   options ls=171 ps=65;run;quit;  ```
    ```   ods listing;  ```
    ```   ods select all;  ```
    ```   ods graphics off;  ```
    ```   proc printto;run;  ```
    ```   goptions reset=all;  ```
    ```   endsubmit;  ```
    ```   endrsubmit;  ```
    ```   run;quit;  ```
    ```   %utlopts;  ```
    ```    ```
    ```  %mend utlfix;  ```
    ```    ```
    ```  for my performance command macros  ```
    ```  https://www.dropbox.com/s/pwx0r8dqko1ocoj/utl_perpac.sas?dl=0  ```
    ```    ```
    ```  My function keys (requires MX310 mouse with over 20 actions)  ```
    ```    ```
    ```  Obs    KEY        LEN    VAL  ```
    ```    ```
    ```    1    F1          71    pgm;file &pgm..sas;file c:\ver\&pgm.&_q..sas;%let _q=%eval(0&_q +1);  ```
    ```    2    F2          30    store;note;notesubmit '%avgha'  ```
    ```    3    F3           6    left 3  ```
    ```    4    F4           7    right 3  ```
    ```    5    F5          30    store;note;notesubmit '%dmpa;'  ```
    ```    6    F6          31    store;note;notesubmit '%dmpha;'  ```
    ```    7    F7          67    log;file "./&pgm..log";note zx;notesubmit "%utl_logcurchk(./&pgm);"  ```
    ```    8    F8           5    rfind  ```
    ```    9    F9           7    rchange  ```
    ```   10    F11         33    store;note;notesubmit '%debugha;'  ```
    ```   11    F12         73    ~;;;;/*'*/ *);*};*];*/;/*"*/;%mend;run;quit;%end;end;run;endcomp;%utlfix;  ```
    ```   12    SHF F1      24    note;notesubmit '%dmpa;'  ```
    ```   13    SHF F2      25    note;notesubmit '%lsala;'  ```
    ```   14    SHF F6      67    ~n ? "hil";n=*"PFil Mason";n gt:"Phil";n le:"Phim"; sql - eqt    */  ```
    ```   15    SHF F7      67    ~libname x excel ".xls";proc sql;update x;set y=2;where n="Roger"*/  ```
    ```   16    SHF F8      12    :a;copy box;  ```
    ```   17    SHF F9      12    :a:copy hdr;  ```
    ```   18    SHF F10     70    ~options minoperator;%macro t(x=a)/minoperator;%if &x in (a b c) %then  ```
    ```   19    SHF F11     24    note;notesubmit '%cona;'  ```
    ```   20    SHF F12     31    store;note;notesubmit '%frqva;'  ```
    ```   21    CTL F1      31    store;note;notesubmit '%dmpha;'  ```
    ```   22    CTL F2      32    store;note;notesubmit '%lsalha;'  ```
    ```   23    CTL F3      10    ~available  ```
    ```   24    CTL F11     31    store;note;notesubmit '%conha;'  ```
    ```   25    CTL F12     31    store;note;notesubmit '%cntva;'  ```
    ```   26    ALT F1      30    store;note;notesubmit '%vuha;'  ```
    ```   27    ALT F2      28    vt _last_ colheading=names;"  ```
    ```   28    ALT F3      64    ~proc report data=c nowd named list wrap;columns _all_;run;quit;  ```
    ```   29    ALT F11     31    store;note;notesubmit '%xlsha;'  ```
    ```   30    ALT F12     30    store;note;notesubmit '%unva;'  ```
    ```   31    CTL B        3    :tf  ```
    ```   32    CTL D       10    ~available  ```
    ```   33    CTL E       10    ~available  ```
    ```   34    CTL G        8    note g.g  ```
    ```   35    CTL H        8    note h.h  ```
    ```   36    CTL I        3    :lc  ```
    ```   37    CTL J        3    :uc  ```
    ```   38    CTL K        4    :mcu  ```
    ```   39    CTL L        4    :mcl  ```
    ```   40    CTL M       79    ~proc format;value $a;proc catalog cat=work.formats;modify a.formatc(desc=dea);  ```
    ```   41    CTL Q        9    ~aailable  ```
    ```   42    CTL R       11    wattention;  ```
    ```   43    CTL T       73    ~proc tabulate data=class;class sex age;table age,sex*(n pctn<age>)/rts=8  ```
    ```   44    CTL U       80    ~do until(last.s);set c;by s;a+ag;end;do until(last.s);set c;by s;output;end;a=0  ```
    ```   45    CTL W       10    ~available  ```
    ```   46    CTL Y       34    ~where name like "B_B" "%B%" "B%B"  ```
    ```   47    RMB         53    log;clear;out;clear;pgm;submit;home;rec;home;log;z;z;  ```
    ```   48    SHF RMB     25    note;notesubmit '%ls40a;'  ```
    ```   49    CTL RMB     32    store;note;notesubmit '%ls40ha;'  ```
    ```   50    MMB         13    ~mapped to F1  ```
    ```   51    SHF MMB     17    ~mapped to shf F1  ```
    ```   52    CTL MMB     17    ~mapped to ctl F1  ```
    ```    ```
    ```    ```
