# HuCommitmentBank
Anaphora resolution datasets for Hungarian formulated as an inference task

This is the repository for the Hungarian datasets of anaphora resolution, designed as a sentence pair classification task of natural language inference.
As a first version, the repo contains the translation of the Winograd schemata formatted as an inference task. A Winograd schema is a pair of sentences that differ in only one or two words and that contain an ambiguity that is resolved in opposite ways in the two sentences and requires the use of world knowledge and reasoning for its resolution (Levesque et al. 2012). This dataset is also part of the Hungarian Language Understanding Evaluation Benchmark Kit [HuLU](hulu.nlp.nytud.hu). 

The [HuWS corpus](github.com/nytud/HuWSC) was created by translating and manually curating the original English Winograd schemata. The NLI format published here was created by replacing the ambiguous pronoun with each possible referent in the schemata (the method is described in GLUE's paper, Wang et al. 2019). We extended the set of sentence pairs derived from the schemata by the translation of the sentence pairs that - together with the Winograd schema sentences - build up the WNLI dataset of GLUE. 

## Dataset Structure

### Data Instances

For each instance, there is an id, a premise, a hypothesis and a label.

An example:

```
{
  "id": "0",
  "premise": "Ha ezt nem erted akkor teljesen felesleges minden vita.    hogy a valóban meggyőző érveid dacára mégiscsak volt a világban egy olyan kísérlet,kedves Derek, - csak hát az itt a bökkenő, Nagy igazságokat írsz a szocdem mozgalomról, amelyben párszázmillióan vettek részt, és amely kísérlet eredménye közismert ugye. Lehet, hogy neked ez nem tetszik, de képzeld, lehet, hogy nekem se tetszik), de volt.",
  "hypothesis": "A beszélő szerint nem tetszik neki sem.",
  "label": "entailment"
}
```

### Data Fields

- id: unique id of the instances;

- premise: the premise, 

- hypothesis: the hypothesis;  

- label: "entailment" if the hypothesis is entailed by the premise, "contradiction" if the hypothesis contradicts the premise, and "neutral" otherwise.

The data is distributed in three splits: training set (250), development set (103) and test set (250). Only instances of Hatvani's dataset with standard deviation < 1 are included in HuLU.

The test set is distributed without labels.
To evaluate your model, please [contact us](mailto:ligeti-nagy.noemi@nytud.hu), or check [HuLU's website](hulu.nytud.hu) for an automatic evaluation. 
### Licensing Information

HuCommitmentBank is released under the CC-BY-SA-4.0 License.


### Citation Information

If you use this resource or any part of its documentation, please refer to:

Ligeti-Nagy, N., Héja, E., Laki, L. J., Takács, D., Yang, Z. Gy. and Váradi, T. (2023) Hát te mekkorát nőttél! - A HuLU első életéve új adatbázisokkal és webszolgáltatással [Look at how much you have grown! - The first year of HuLU with new databases and with webservice]. In: Berend, G., Gosztolya, G. and Vincze, V. (eds), XIX. Magyar Számítógépes Nyelvészeti Konferencia. Szeged, Szegedi Tudományegyetem, Informatikai Intézet. To appear.
```
@inproceedings{ligetihulu2023,
      author = "Ligeti-Nagy, Noémi and Héja, Enikő and Laki, László János and Takács, Dávid and Yang, Zijian {\relax Gy}őző and Váradi, Tamás",
      title = "Hát te mekkorát nőttél! - A HuLU első életéve új adatbázisokkal és webszolgáltatással [Look at how much you have grown! - The first year of HuLU with new databases and with webservice]",
      booktitle = "XIX. Magyar Számítógépes Nyelvészeti Konferencia",
      year = "2023",
      editor = "Berend, Gábor and Gosztolya, Gábor and Vincze, Veronika",
      address = "Szeged",
      publisher = "Szegedi Tudományegyetem, Informatikai Intézet",
      note = "To appear."
}
```
