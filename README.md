## Important Files:


•	do.sh

•	do_margin.sh

•	run.cc

•	runtwitter.cc


## Edited Files 
*The images in ReadMe.docx*

•	leveldb/benchmarks/db_bench.cc

•	leveldb/table/block.h

•	leveldb/table/block.cc 

•	leveldb/table/block_builder.h

•	leveldb/table/block_builder.cc

## Prerequisite
• Make sure you have cmake installed. No cmake, run this: ```sudo apt install cmake```

• Make sure you have build-essential installed. No build-essential, run this: ```sudo apt install build-essential```

• Make sure you have libsnappy-dev installed. No libsnappy-dev, run this: ```sudo apt install libsnappy-dev```



## How to compile levelDB with Segmented Linear Regression
1. ```cd /home```
2. ```git clone https://github.com/imagesid/levelDB-with-SLR-Prediction-Search.git``` 
3. ```mv levelDB-with-SLR-Prediction-Search leveldb```
4. ```cd "leveldb/leveldb"```
5. ```mkdir -p build && cd build```
5. ```cmake -DCMAKE_BUILD_TYPE=Release .. && cmake --build .```

*Note: My current working directory is /home/leveldb* 

## How to run the db_bench:

1.	Single benchmark the OSM Dataset:

```./db_bench --benchmarks="readseqslr" --histogram=1  --use_existing_db=1 --db=/home/leveldb/dbonly/test5```

2.	Multiple benchmarks the OSM Dataset:

```./db_bench --benchmarks="readseqslr, readseqslr , readseqslr , readseqslr , readseqslr " --histogram=1  --use_existing_db=1 --db=/home/leveldb/dbonly/test5```

3.	Single benchmark the Twitter User Dataset:

```./db_bench --benchmarks="readseqslrtwitter" --histogram=1  --use_existing_db=1 --db=/home/leveldb/dbonly/test5```

4.	Multiple benchmarks the Twitter User Dataset:

```./db_bench --benchmarks=" readseqslrtwitter, readseqslrtwitter, readseqslrtwitter, readseqslrtwitter, readseqslrtwitter " --histogram=1  --use_existing_db=1 --db=/home/leveldb/dbonly/test5```

5.	Build, compile the scripts and run db_bench in one command:

```./do.sh {dataset} {slr}```

Example:

```./do.sh osm true```

```./do.sh twitter false```

Note:
- Edit do.sh to edit the path.
- If there is permission error, please run ```chmod +x do.sh```
- If there is bad interpreter error, please run ```sed -i -e 's/\r$//' do.sh```
- You can also change ```./do.sh``` to ```bash.sh```
- Make sure you have cmake and g++ installed


