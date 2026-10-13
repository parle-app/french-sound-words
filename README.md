
# Parle French Sound Words

The 37 sounds of French, each with up to 30 everyday example words and their IPA transcription: 1,088 words in total. This is the word list behind the sound lessons in [Parle](https://www.parleapp.fr/), the French pronunciation app, where learners practise each sound with packs of these words, hearing them and recording themselves.

- 12 oral vowels: i y u e ø o ɛ œ ɔ ə a ɑ
- 4 nasal vowels: ɛ̃ œ̃ ɑ̃ ɔ̃
- 18 consonants: p b t d k ɡ f v s z ʃ ʒ m n ɲ ŋ l ʁ
- 3 semi-vowels: j ɥ w

Also on Hugging Face: [huggingface.co/datasets/Parle-App/french-sound-words](https://huggingface.co/datasets/Parle-App/french-sound-words)

## The 37 sounds

| Sound | Type | Words | Examples |
|---|---|---|---|
| `i` | oral vowel | 30 | suis, oui, ils, ici, dit |
| `y` | oral vowel | 30 | tu, suis, plus, sur, lui |
| `u` | oral vowel | 30 | vous, pour, nous, tout, pourquoi |
| `e` | oral vowel | 30 | était, avez, été, allez, aller |
| `ø` | oral vowel | 30 | veux, peux, peut, deux, peu |
| `o` | oral vowel | 30 | votre, aussi, autre, notre, faut |
| `ɛ` | oral vowel | 30 | mais, elle, avec, fait, était |
| `œ` | oral vowel | 30 | leur, seul, peur, seule, heure |
| `ɔ` | oral vowel | 30 | comme, alors, chose, encore, accord |
| `ə` | oral vowel | 30 | quelque, besoin, depuis, sera, petit |
| `a` | oral vowel | 30 | pas, avec, moi, quoi, toi |
| `ɑ` | oral vowel | 30 | grâce, âge, âme, lâche, gâteau |
| `ɛ̃` | nasal vowel | 30 | bien, rien, maintenant, besoin, viens |
| `œ̃` | nasal vowel | 15 | aucun, chacun, commun, lundi, parfum |
| `ɑ̃` | nasal vowel | 30 | dans, quand, comment, vraiment, maintenant |
| `ɔ̃` | nasal vowel | 30 | non, sont, bon, donc, monde |
| `p` | consonant | 30 | pas, pour, plus, pourquoi, peux |
| `b` | consonant | 30 | bien, bon, besoin, beaucoup, bonne |
| `t` | consonant | 30 | tu, tout, était, être, toi |
| `d` | consonant | 30 | dans, dit, dire, deux, dois |
| `k` | consonant | 30 | avec, quoi, comme, pourquoi, quand |
| `ɡ` | consonant | 30 | regarde, gars, grand, gros, guerre |
| `f` | consonant | 30 | fait, faire, fais, faut, fois |
| `v` | consonant | 30 | vous, avec, veux, votre, avez |
| `s` | consonant | 30 | suis, sur, sais, ici, cette |
| `z` | consonant | 30 | chose, besoin, désolé, maison, raison |
| `ʃ` | consonant | 30 | chose, chez, chance, chercher, chaque |
| `ʒ` | consonant | 30 | juste, jamais, toujours, déjà, gens |
| `m` | consonant | 30 | mais, moi, comme, merci, jamais |
| `n` | consonant | 30 | nous, non, maintenant, notre, personne |
| `ɲ` | consonant | 30 | ligne, magnifique, signifie, signe, gagne |
| `ŋ` | consonant | 23 | parking, camping, shopping, jogging, smoking |
| `l` | consonant | 30 | elle, plus, ils, lui, alors |
| `ʁ` | consonant | 30 | pour, faire, sur, être, votre |
| `j` | semi-vowel | 30 | bien, dieu, viens, mieux, fille |
| `ɥ` | semi-vowel | 30 | suis, lui, depuis, nuit, tuer |
| `w` | semi-vowel | 30 | moi, oui, quoi, toi, pourquoi |

## Files

- `sound_words.csv` / `sound_words.jsonl`: one row per word
- `sounds.csv` / `sounds.jsonl`: one row per sound

## Fields

**`sound_words`** has 1,088 rows:

| Field | Description | Example |
|---|---|---|
| `sound` | target French sound (IPA) | `y` |
| `sound_type` | `oral vowel`, `nasal vowel`, `consonant` or `semi-vowel` | `oral vowel` |
| `word` | French word containing the sound | `tu` |
| `word_ipa` | full IPA transcription of the word | `ty` |
| `position` | order of the word in Parle's list for that sound | `1` |

**`sounds`** has 37 rows, one per sound: `sound`, `sound_type`, `word_count`, `examples` (first 5 words).

Most sounds have 30 words; the rare sounds œ̃ (15) and ŋ (23) have fewer.

```python
from datasets import load_dataset

words = load_dataset("Parle-App/french-sound-words", split="train")
nasal = words.filter(lambda r: r["sound"] == "ɑ̃")
print(nasal[:5]["word"], nasal[:5]["word_ipa"])
```

## Notes

- Transcriptions follow standard European French. Canadian French differs for some vowels.
- No audio is included. You can hear and practise every word in the Parle app.

## Related

- [Parle French Sounds](https://huggingface.co/datasets/Parle-App/parle-french-sounds): vowel mouth chart, common mistakes and fixes in 4 languages
- [Parle French Phoneme Recognizer](https://huggingface.co/Parle-App/parle-french-phoneme-recognizer): on-device model that recognises these sounds in recordings
- [How to pronounce the French R, U and nasal vowels](https://www.parleapp.fr/french-pronunciation-app/)

## License

[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) (non-commercial). Free for learning, teaching and research, with credit to "Parle — parleapp.fr" and a link to https://www.parleapp.fr/. Commercial use, including in other language-learning apps or for training AI in commercial products, is not permitted without written permission from Parle (support@parleapp.fr).

Practise every sound with your own voice in [Parle](https://www.parleapp.fr/) for [iPhone](https://apps.apple.com/app/id6447072574) and [Android](https://play.google.com/store/apps/details?id=io.parle.parleapp).
