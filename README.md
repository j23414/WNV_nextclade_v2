# WNV_nextclade_v2

[WNV Nextclade V2](https://clades.nextstrain.org/?dataset-url=https://github.com/j23414/WNV_nextclade_v2/tree/main/all)

<!--

## Pull reference and gff files

```
git clone https://github.com/nextstrain/nextclade_dataset_template.git
cd nextclade_dataset_template
python scripts/generate_from_genbank.py \
  --reference AF481864 \
  --output-dir all
```

## Build a basic tree

```
# === Input files
INFILE="sequences.fasta"
META="metadata.tsv"
REF="reference.fasta"
ROOTNAME="AF481864"
REF_GFF="annotation.gff" # Swap this out for correct reference GenBank or GFF

[[ -d "results" ]] || mkdir results

augur align \
  --sequences ${INFILE} \
  --reference-sequence ${REF} \
  --output results/aln.fasta \
  --fill-gaps \
  --nthreads `nproc`


augur tree \
  --alignment results/aln.fasta \
  --output results/tree.nwk \
  --nthreads `nproc`

augur refine \
  --tree results/tree.nwk \
  --alignment results/aln.fasta \
  --metadata metadata.tsv \
  --metadata-id-columns accession \
  --root $ROOTNAME \
  --timetree \
  --output-tree results/refined_tree.nwk \
  --output-node-data results/branch_labels.json

augur ancestral \
  --tree results/refined_tree.nwk \
  --alignment results/aln.fasta \
  --output-node-data results/nt-muts.json \
  --inference joint

augur translate \
  --tree results/refined_tree.nwk \
  --ancestral-sequences results/nt-muts.json \
  --reference-sequence ${REF_GFF} \
  --output results/aa-muts.json

augur traits \
  --tree results/refined_tree.nwk \
  --metadata metadata.tsv \
  --metadata-id-columns accession \
  --output results/clade_membership.json \
  --columns clade_membership 

augur export v2 \
  --tree results/refined_tree.nwk \
  --metadata metadata.tsv \
  --metadata-id-columns accession \
  --node-data \
    results/branch_labels.json \
    results/clade_membership.json \
    results/nt-muts.json \
    results/aa-muts.json \
  --output results/tree.json \
  --auspice-config auspice_config.json
```
-->

