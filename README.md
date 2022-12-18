# Network-log-parser
## Generate the Log files
1. Open Windows PowerShell with administrator privileges.
2. execute pktmon command
3. ```pktmon start -c ```(this command will start the packet capture)
4. wait for 30 sec to 1 minute (or in this time frame you can surf the internet like youtube, google, etc. for data enrichment) for ETL file generation
5. ```pktmon stop ```(this command will write all the packets in a PktMon.etl file)
6. Now process the ```PktMon.etl``` file to extract the useful information for the key-value pair
7. You can convert PktMon.etl file to pcap or text file for better visibility of logs

For pcap conversion:  
```
pktmon etl2pcap PktMon.etl --out <out_file>.pcap  
```
For text conversion:   
```
pktmon etl2txt PktMon.etl --out <out_file>.txt"
```

## The parser
The parser extract the following nine fields from the txt file and writes it to the output file in csv format.
1. PktGroupId
2. PktNumber
3. Appearance
4. Direction
5. Type
6. Component
7. Edge
8. Filter
9. OriginalSize
10. LoggedSize

```
Note: There is a sample input file ```test.txt``` and the output file ```out.csv``` generated from it.
