# EOLES_elecRES in Julia

This repository is a translation to [Julia](https://julialang.org/) (with the [JuMP](https://jump.dev/) package) 
of the 100% renewable electricity optimization model [EOLES_elecRES](https://github.com/BehrangShirizadeh/EOLES_elecRES) which is written in [GAMS](https://www.gams.com/latest/docs/UG_MAIN.html)
by B. Shirizadeh, Q. Perrier and P. Quirion.

The goal is to allow running the open source EOLES_elecRES model in an **open source environment** (while GAMS is commercial).
The translation is kept as close as possible to the original GAMS code and is meant to be fully compatible,
e.g. by running on the same input files.


## Repository content

- [EOLES_elecRES_Julia.ipynb](EOLES_elecRES_Julia.ipynb): Jupyter notebook. Port of the [EOLES_elecRES.gms](https://github.com/BehrangShirizadeh/EOLES_elecRES/blob/master/model/EOLES_elecRES.gms) GAMS model.
  - status: OK (produces very similar results, but needs some more checks with respect to the gas storage size)
  - [inputs](inputs): copy of the input folder of `EOLES_elecRES`
- [EOLES_elecRES_simplified.ipynb](EOLES_elecRES_simplified.ipynb): **simplified** model
  - no reserve (FRR)
  - less sources: no more biogas generation, no hydro (lake, river and pumped hydro)
  - generation is PV and wind (onshore and offshore)
  - storage is battery and power to gas (methanation)
  - [inputs_simplified](inputs_simplified) same inputs as in the full model, but with the removed technologies removed from the data files
  - [outputs_simplified](outputs_simplified): save results from running the simplified model (sizing and time series)

- Graphical representation of the equations (made with [draw.io/diagrams.net](https://www.diagrams.net/))

![graphical representation of the equations](EOLES_elecRES.png)

## License

See [LICENSE.txt](LICENSE.txt).
This derivative work is made available under the same
[CC BY-NC-SA 4.0](http://creativecommons.org/licenses/by-nc-sa/4.0/) license as the original `EOLES_elecRES` model.