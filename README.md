# pyseff
Inspired by [seff](https://github.com/SchedMD/slurm/blob/master/contribs/seff/seff), a tool to calculate the efficiency of SLURM jobs.  Unfortunately, it uses perl and I don't want to install it on our systems.  This is a quick and dirty alternative using python and the output from `sacct` command.  
For actual solutions and pythonic ways to do stuff with slurm, check out [pyslurm](https://github.com/pyslurm/pyslurm) or [simple_slurm](https://github.com/amq92/simple_slurm).  
This probably won't work on job arrays, or have any meaningful output for OUT_OF_MEMORY jobs.

## Usage

```bash
usage: pyseff.py [-h] [-j JOBID] [--fromdate FROMDATE] [-o OUTPUT]
```

## Options:
  * `-j JOBID`, `--jobid JOBID` [default: None]
    Specific job ID to analyze
  * `--fromdate FROMDATE` [default: 2025-01-01]
    Start date for job analysis (format: YYYY-MM-DD) [default from 2025-01-01]
  * `-o OUTPUT`, `--output OUTPUT` [default: None]
    Output file path (if not specified, prints to screen)

## Example

```bash
python pyseff.py -j 1234567890 --fromdate 2024-01-01
```
## dependencies

* python 3.x
* [polars](https://github.com/pola-rs/polars?tab=readme-ov-file#python-1)
