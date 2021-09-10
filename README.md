# Project: MADB
CSE6242 Spring 2021 Project
TEAM: VIZ THIS

A more informational manual can be found on the launched website
at 127.0.0.1:5000/how-it-works.html

# Description
This project is designed to take a large netflow (summarized PCAP/network data) dataset.
It (if necessary) breaks this dataset down, preprocesses it, and runs the MIDAS (https://github.com/Stream-AD/MIDAS) dynamic graph anomaly detection algorithm to check for anomalous network traffic.
MIDAS output is postprocessed using a 2-component Gaussian Mixture Model to assign the probability of anomalousness of the network traffic, then aggregated on the IP address/network device level. Finally, the aggregated result is visualized in a local website, so the user can see which network devices are acting suspiciously.

# Installation
Python 3.x will be required to run the scripts.
Python packages needed will be:
pandas
sklearn
flask

A build of the MIDAS exe is included, but the code (and some minor changes) to build it yourself are located at: https://github.gatech.edu/jkalafut3/MIDAS_NETWORK
The git directory shouldn't require any modifications.

# Execution
A pre-parsed dataset is included.
To run flask and view the webpage (and data visualization) simply run flask_and_display.py

To process other data:
Acquire a dataset. Scripts are customized for UGR'16 datasets, like this:
https://nesg.ugr.es/nesg-ugr16/july_week5.php#INI
All the code processing can be done by calling process_and_run.py [netflow.csv]
If you only want parts to be done or processed, you can un/comment areas of process_and_run.py
It also shows which other scripts are being called, and those other scripts can optionally be modified as well.

Once process_and_run.py is complete, you can call flask_and_display.py [node file] [edge file] to move the files and launch the site.
To view the data at a later data, simply call flask_and_display.py ( No arguments, the data does not need to be reprocessed or moved ).

# Team Members
- Benjamin Hawtof
- Dina Broydo
- Jerry Mahone
- John Kalafut
- Michael Kim
- Priscilla Mariani
