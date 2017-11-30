
### If you find TreeShrink helpful for your research, please cite the following paper
Mai, Uyen, and Siavash Mirarab. “TreeShrink: Efficient Detection of Outlier Tree Leaves.” In RECOMB-CG 2017, Proceedings, 116–40. 2017. doi:10.1007/978-3-319-67979-2_7.

### Dependencies:
- Python and [Dendropy (version 4.2.0 recommended)](https://pythonhosted.org/DendroPy/downloading.html)
- R and the [BMS package](http://bms.zeugner.eu/getBMS/)


### Usage: 
```bash
treeshrink.py [-h] -i INPUT [-d OUTDIR] [-t TEMPDIR] [-o OUTPUT] [-c]
                     [-k K] [-q QUANTILES] [-m MODE]
```
optional arguments:
```
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input trees
  -d OUTDIR, --outdir OUTDIR
                        Output directory. Default: inferred from the input
                        trees
  -t TEMPDIR, --tempdir TEMPDIR
                        Directory to keep temporary files. If specified, the
                        temp files will be kept
  -o OUTPUT, --output OUTPUT
                        The name of the output trees. Default: inferred from
                        the input trees
  -c, --centroid        Do centroid reroot in preprocessing. Highly
                        recommended for large trees. Default: NO
  -k K, --k K           The maximum number of leaves that can be removed.
                        Default: auto-select based on the data
  -q QUANTILES, --quantiles QUANTILES
                        The quantile(s) to set threshold. Default is 0.05
  -m MODE, --mode MODE  Filtering mode: 'per-species', 'per-gene', 'all-
                        genes'. Default: 'per-species'
```

### Examples:
The TreeShrink package comes with several testing trees that can be found in the test_data folder.

The following command will produce the shrinked trees and the corresponding removing sets at alpha = 0.05 (default)
```bash
python treeshrink.py -i test_data/mm10.trees
```

After running the command, the program will generate the folder test_data/mm10_kshrink/, inside which you will find the shrinked trees (mm10_shrinked_0.05.trees) and the removing sets (mm10_shrinked_RS_0.05).
