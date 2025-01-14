# WikiDIR

A significant amount of local knowledge and culture-specific knowledge can only be found in documents written in dialects, yet cross-dialect information retrieval (CDIR) has not been extensively studied. In this work, we propose WikiDIR, a retrieval dataset for German dialects. The dataset is described in detail in our paper [Cross-Dialect Information Retrieval: Information Access in Low-Resource and High-Variance Languages](https://arxiv.org/abs/2412.12806) by Robert Litschko, Oliver Kraus, Verena Blaschke and Barbara Plank.  


## Dataset
We make the [WikiDIR dataset](https://huggingface.co/datasets/rlitschk/wikidir/) available on huggingface 🤗. Each folder (e.g. `de.bar/`) contains German queries, documents written in dialects and relevance labels. Query and document ID's correspond to Wikipedia CurID's, you can use them browse to the Wikipedia article from they were extracted:
- https://de.wikipedia.org/?curid=3215
- https://bar.wikipedia.org/?curid=12259


Queries: `queries.jsonl`
```python
{"id": "3215", "contents": "München"}
```

Documents: `docs.jsonl`
```python
{"id": "12259", "contents": "Minga Aussproch: [ˈmɪŋ(:)ɐ] is d'Haptstod vo Bayern. In da Umgebung (20–30 km) hoaßt ma s'Minga oda oft aa oafach d'Stod. In Minga sogt ma München. Minga is mid mehra wia 1,5 Milliona Eihwohna d'gresste Stod vo Bayern und hinta Berlin und Hamburg d'drittgresste Stod vo Deitschland ..."}
```


Relevance labels: `{train, dev, test, analysis, analysis_variants}.jsonl`
```python
{
  "src_id": "3215",
  "src_query": "München",
  "tgt_results": [
    ["12259", 6], ["3154", 5], ["12198", 4], ["3966", 4], ["20246", 3], ...
  ]
}
```


## Dialect variation dictionaries
You can find our [dialect dictionaries](https://huggingface.co/datasets/rlitschk/wikidir/tree/main/dictionaries) on huggingface 🤗.
```python
{
  "de_id": "3215",
  "de_title": "München",
  "dial_id": "12259",
  "dial_title": "Minga",
  "variants": [
    "Münch'n",
    "Minkcha",
    "Minkn",
    "Minchn",
    "Mingna",
    "Minkhn",
    "Münchn"
  ]
}
```
