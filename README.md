# Allele-age-and-frequency
Allele Age Estimation and Frequency Calculation Codes

RELATE CODES FOR ANCIENT SAMPLES

1. VCF to HAPS/SAMPLE FILES

/{relatepath}/relate_v1.1.9_x86_64_static/bin/RelateFileFormats --mode ConvertFromVcf --haps ${output}.haps --sample ${output}.sample -i ${vcffile}


2. RELATE PREPARATION STEPS
   
/{relatepath}/relate_v1.1.9_x86_64_static/scripts/PrepareInputFiles/PrepareInputFiles.sh --haps ${hapsfile} --sample ${samplefile} --ancestor ${ancestorfile} --mask ${maskfile} --remove_ids ${toberemovedlist} --poplabels ${poplabelsfile} -o ${prepared_outputfile}


3. ALLELE AGE CALCULATION

/{relatepath}/relate_v1.1.9_x86_64_static/bin/Relate --mode All -m 3e-9 -N 30000 --haps ${prepared_outputfile}.haps --sample ${prepared_outputfile}.sample --map $mapfile --annot ${prepared_outputfile}.annot --dist ${prepared_outputfile}.dist --sample_ages ${sampleages} --seed 1 -o ${output}

