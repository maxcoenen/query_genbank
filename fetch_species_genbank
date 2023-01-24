#!/usr/bin/env bash


## Edit list of species to edit query
for species in \
"Solanum lycopersicum" \
"Solanum lycopersicoides" \
"Solanum pimpinellifolium" \
"Solanum habrochaites" \
"Solanum galapagense" \
"Solanum peruvianum" \
"Solanum pennellii" \
"Solanum sitiens"
do
    ## Download Solanum chromosome&scaffold-level assemblies
    esearch -db assembly \
    -query """${species} [ORGN] AND (("chromosome level"[filter] \
              OR "scaffold level"[filter]) AND all[filter] \
              NOT anomalous[filter])""" |
    efilter -query "representative [PROP]" |
    elink -target nuccore -name assembly_nuccore_refseq |
    efetch -format fasta > $(awk '($2)' ${species}).fa
done 
