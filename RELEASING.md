# Releasing the dataset

## Recreate the raw data from glottography-data

In case of upstream changes in glottography-data:
```shell
cldfbench download cldfbench_goddard1999native.py
```

## Recreate the CLDF data

```shell
cldfbench makecldf cldfbench_goddard1999native.py --glottolog-version v5.2
cldfbench cldfreadme cldfbench_goddard1999native.py
cldfbench zenodo --communities glottography cldfbench_goddard1999native.py
cldfbench readme cldfbench_goddard1999native.py
```

## Validation

```shell
cldf validate cldf
```

```shell
cldfbench geojson.validate cldf
```

```shell
cldfbench geojson.glottolog_distance cldf --format pipe
```

```shell
cldfbench geojson.glottolog_distance cldf --format tsv | csvformat -t | csvgrep -c Distance -r"^0\.?" -i | csvsort -c Distance | csvcut -c ID,Distance | csvformat -E | termgraph
```

```
cree1270: ▇▇▇▇▇▇ 1.12 
sius1254: ▇▇▇▇▇▇▇ 1.19 
adai1235: ▇▇▇▇▇▇▇ 1.20 
matt1238: ▇▇▇▇▇▇▇ 1.22 
nort2945: ▇▇▇▇▇▇▇ 1.26 
sars1236: ▇▇▇▇▇▇▇ 1.29 
yaqu1251: ▇▇▇▇▇▇▇ 1.33 
eude1234: ▇▇▇▇▇▇▇▇ 1.40 
jica1244: ▇▇▇▇▇▇▇▇ 1.44 
otta1242: ▇▇▇▇▇▇▇▇▇ 1.57 
arap1274: ▇▇▇▇▇▇▇▇▇ 1.59 
wiyo1248: ▇▇▇▇▇▇▇▇▇ 1.68 
nauk1242: ▇▇▇▇▇▇▇▇▇▇ 1.84 
nask1242: ▇▇▇▇▇▇▇▇▇▇▇ 1.92 
chey1247: ▇▇▇▇▇▇▇▇▇▇▇▇ 2.08 
pima1248: ▇▇▇▇▇▇▇▇▇▇▇▇ 2.13 
nawa1259: ▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.27 
plai1258: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.36 
ston1242: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.56 
pawn1254: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.71 
kick1244: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 2.78 
pota1247: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 3.63 
mesk1242: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 3.82 
nort2943: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 5.42 
koas1236: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 6.08 
alab1237: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 6.79 
aleu1260: ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 8.41 
```
