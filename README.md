# HuCommitmentBank
HuCommitmentBank is a corpus of naturally occurring discourses whose final sentence contains a clause-embedding predicate under an entailment canceling operator. This dataset is also part of the Hungarian Language Understanding Evaluation Benchmark Kit [HuLU](hulu.nytud.hu). 

It was designed based on the CommitmentBank Corpus (de Marneffe et al., 2019). The data collection and annotation process was done in the master thesis of Péter Hatvani (_A Corpus to Investigate Projection Methods: The Hungarian Commitment Bank_. Szakdolgozat, Pázmány Péter Katolikus Egyetem, Bölcsészet- és Társadalomtudományi Kar, Angol-Amerikai Intézet, Elméleti Nyelvészet Tanszék). 4 annotators collected a total of 1100 valid text fragments from MNSZ2 (Oravecz et al., 2014). The 1100 examples were labelled by 5-5 annotators on a 7-point Likert scale (from -3 to 3, where 0 meant that the speaker could not decide whether the speaker thinks the subordinate clause to be true or false). A total of 9 native Hungarian annotators worked on the corpus. 

As in SuperGLUE, HuLU also integrates this corpus as an inference task. The 7-degree label has been replaced by a three-way classification: the original labels -1, 0 and 1 are "neutral", -3 and -2 are "contradiction", and 2 and 3 were compressed into the "entailment" category.

## Dataset Structure

### Data Instances

For each instance, there is an id, a premise, a hypothesis and a label.

An example:

```
{
  "id": "0",
  "premise": "Ha ezt nem erted akkor teljesen felesleges minden vita. hogy a valóban meggyőző érveid dacára mégiscsak volt a világban egy olyan kísérlet,kedves Derek, - csak hát az itt a bökkenő, Nagy igazságokat írsz a szocdem mozgalomról, amelyben párszázmillióan vettek részt, és amely kísérlet eredménye közismert ugye. Lehet, hogy neked ez nem tetszik, de képzeld, lehet, hogy nekem se tetszik), de volt.",
  "hypothesis": "A beszélő szerint nem tetszik neki sem.",
  "label": "entailment"
}
```

### Data Fields

- id: unique id of the instances;

- premise: the premise, containing one embedded clause under an entailment-cancelling operator

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
