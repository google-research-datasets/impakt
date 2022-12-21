# ImPaKT: A Dataset for Open-Schema Knowledge Base Construction

This dataset contains semantic parsing annotations for 2489 sentences from
shopping web pages in the C4 corpus, corresponding to annotations of 3719
expressed implication relationships and 6117 typed and summarized attributes.

The data is released under the
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.

More details can be found in an upcoming paper.

The dataset is in [JSON Lines](https://jsonlines.org/) format, where each line
is a json object with the following schema:

```
{
  "snippet": "",
  "provenance": {
    "url": "https://pleasanthearthfireplacedoors.com/gas-logs/vented-vs-vent-free-gas-logs-which-one-to-get/",
    "timestamp": "2019-04-22T20:53:43Z",
    "span_start": 360,
    "span_end": 435
  },
  "category": "Home & Garden > Fireplaces",
  "classification": "Yes",
  "attributes": [
    {
      "attribute": "ambiance",
      "summary": "ambiance"
    },
    {
      "attribute": "flickering fire",
      "summary": "flickering fire"
    }
  ],
  "atomic_attributes": {
    "ambiance": [
      {
        "attribute": "ambiance",
        "summary": "ambiance",
        "attribute_type": "use case"
      }
    ],
    "flickering fire": [
      {
        "attribute": "flickering fire",
        "summary": "flickering fire",
        "attribute_type": "features"
      }
    ]
  },
  "implications": [
    {
      "antecedent": "flickering fire",
      "consequent": "ambiance"
    }
  ]
}
```

The provenance information lets users join onto the
[C4 corpus](https://www.tensorflow.org/datasets/catalog/c4) to find the snippet
that was annotated. The C4 corpus can be constructed using the scripts at the
[original dataset listing](https://www.tensorflow.org/datasets/catalog/c4), or a
pre-constructed version can be used, such as
[the one created by AI2](https://github.com/allenai/allennlp/discussions/5056)
and
[hosted by HuggingFace](https://huggingface.co/datasets/allenai/c4/tree/main).
