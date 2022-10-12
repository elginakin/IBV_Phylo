---
Title: GISAID IBV Database 
Subtitle: 

Sequences Downloaded 08162022 - representative of this time only

GISAID Download Parameters 
Total Sequences 
All 8 segments downloaded 
Full Sequences Only 

Total Unique Isolates: 11,154
Total Sequences: 89, 832 total sequences 
    - Includes all segments

---

Filter Sucession Pipeline 
 - Passage History -> Original, original sample, Clinical specimen
    - Seq #:
 - By Segment: total 8 different files with clinical isolates by segment 
    - Seq #: 

wd = /Users/elgin/Library/CloudStorage/OneDrive-JohnsHopkins/2_Pekosz/GISAID_Local_Database/IBV

seqkit stats *.fasta > fasta_summary.fasta 

## Parse fasta header by regex

Use excel bc you dont know regex idiot - generate list for each segment of clinical isolates


```sh

#need to use a regex expression to parse the | sperated FASTA ID 
#can you use REGEX expression from list in file? 
#Passage History

#NP
seqkit grep -n -f clinical_NP.txt gisaid_epiflu_sequence-segmented.fasta -o gisaid_epiflu_sequence-segmented_clinical-NP.fasta
#HA
seqkit grep -n -f clinical_HA.txt gisaid_epiflu_sequence-segmented.fasta -o gisaid_epiflu_sequence-segmented_clinical-HA.fasta
#NA
seqkit grep -n -f clinical_NA.txt gisaid_epiflu_sequence-segmented.fasta -o gisaid_epiflu_sequence-segmented_clinical-NA.fasta
#PB1
seqkit grep -n -f clinical_PB1.txt gisaid_epiflu_sequence-segmented.fasta -o gisaid_epiflu_sequence-segmented_clinical-PB1.fasta
#PB2
seqkit grep -n -f clinical_PB2.txt gisaid_epiflu_sequence-segmented.fasta -o gisaid_epiflu_sequence-segmented_clinical-PB2.fasta
#MP
seqkit grep -n -f clinical_MP.txt gisaid_epiflu_sequence-segmented.fasta -o gisaid_epiflu_sequence-segmented_clinical-MP.fasta
#NS
seqkit grep -n -f clinical_NS.txt gisaid_epiflu_sequence-segmented.fasta -o gisaid_epiflu_sequence-segmented_clinical-NS.fasta
# PA
seqkit grep -n -f clinical_PA.txt gisaid_epiflu_sequence-segmented.fasta -o gisaid_epiflu_sequence-segmented_clinical-PA.fasta

#summary 
seqkit stats *.fasta > extracted_seq_stats.txt
```

## CDhit collapse sequences by homology - 
    - Filter by 100% identity (duplicate sequences)

## Building Tree by segment 

Start with HA segment tree building 
