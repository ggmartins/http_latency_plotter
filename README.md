<p align="center">
Got a new BISmark router from the NOISE research team. Which wireless router is better? <br>
  <b>Linksys WRT160NL (current) X Netgear n600 (new)</b>
<br>
  I will try to address that with one of my favorite network measurement tools (HTTPing).
</p>


|![Cabled](https://github.com/ggmartins/http_latency_plotter/blob/master/cabled.png?raw=true)|![Wireless](https://github.com/ggmartins/http_latency_plotter/blob/master/wireless.png?raw=true)|
|:---:|:---:|

http_latency_plotter
====================

HTTP round-trip time latency graphic plotter written in Python

Usage: `http_latency_plotter.py [-h] [-v] [-f FILENAME] [-p]`

```
optional arguments:
  -h, --help            show this help message and exit
  -v, --verbosity       enable verbose outout
  -f FILENAME, --filename FILENAME
                        .csv filename to update data
  -p, --justplot        plot available .csv files
```
Edit http_latency_plotter.py head to change default params:

```
  maxsample=500
  httpaddr="ipaddr"
  httpmethod="HEAD"
  httppath="/"
  outfile="output"
```

Use cases:

  `$./http_latency_plotter.py <enter>`

Generates [output.csv] and plot data to [output.pdf] if matplotlib available (Recommended for Pythonista)


  `$./http_latency_plotter.py -f test1`

Generates [test1.csv] and plot data to [output.pdf]. Run more times to append (NOT overide) test1.csv with new data.


  `$./http_latency_plotter.py -f test2`

Generates [test2.csv] and plot data [output.pdf] using test1.csv and test2.csv and any other .csv in the dir. 
Repeat the step changing the network configuration to generate multiple lines in the graphic.


  `$./http_latency_plotter.py -p`
  
Use all .csv in the dir to generate graphics only (will not run HTTP requests and generate more data)

