Glove Pretrained embeddings with Anonymized Newsela dataset.

Train and Test:
Before training we need copy test, train, and validation data.
```
src: /data2/text_simplification/dataset/ 
dst: pretrained_embeddings/data/newsela_Zhang_Lapata_splits
```
and copy glove embeddings.
```
src: /data1/embeddings/eng/glove.6B.300d.txt
dst: pretrained_embeddings/data/emb/
```

Training:
run.sh script copies the required data into current sockeye environment and then execute processing and training steps.
```
Execute ./run.sh
```

Testing:
Execute the below command to translate source sentences using the trained model.
```
../../scripts/translate.sh -i <path-to-source> -o <output-file> -p <hpm-file> -e sockeye_gpu
```
example,
```
../../scripts/translate.sh -i data/newsela_Zhang_Lapata_splits/V0V4_V1V4_V2V4_V3V4_V0V3_V0V2_V1V3.aner.ori.test.src.aner -o data/output_glove/V0V4_V1V4_V2V4_V3V4_V0V3_V0V2_V1V3.aner.ori.test.src.aner.1best -p anon_glove_zhanglapata.hpm -e sockeye_gpu
```

