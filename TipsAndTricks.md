# Quick for loop to process multiple folders #
Here is a one liner, to process a ADORE-DORIS step over multiple folders containing DORIS results (crops or interferograms). In the example I am in the interferograms folder (`${projectFolder}/process/run7/i12s`) and the contents are:
```
ADORE: ls
20091228_20100108  20100130_20100221  20100221_20100304  20100520_20100509  20100520_20100531
```
To process comprefdem step for all these pairs one can use the following command:
```
ADORE: for pair in `ls`; do eval "cd ${pair};settings load;comprefdem;cd .."; done
```
If you would like to use quotes in the command do not forget to escape them with a preceding \.
```
ADORE: for pair in `ls`;do eval "cd ${pair}; settings load; quejob \"snaphu -f snaphu.conf *.srp 2800\" -- -l nodes=demeter:ppn=1; cd .."; done
```