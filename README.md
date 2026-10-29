# Colorfish Test — Experimental Platform

This repository contains the source code for the web-based experimental platform used to
collect data for **"The Grue Divide: When Cognitive Accuracy Doesn't Predict Affective
Alignment,"** a large-scale (N=9,534) cross-cultural study of color perception, cognition,
and affective language, focusing on the Korean "Grue" (blue-green) spectrum.

The platform combines two tasks administered in a single session:

- **Study 1 — Cognitive Perception**: a block-counting numerosity-estimation task across
  color gradients (`ExperimentPanel`, `GradientBar`).
- **Study 2 — Affective Emotion**: an open-ended keyword-elicitation task in response to
  AI-generated contextual color stimuli, later scored via the Sentiment-Formality-
  Friendliness (SFF) framework (`ColorEmotionTest`, `ColorVocabularyTest`).

Live deployments used during data collection (retained for reference; no longer
actively collecting data):

- Korean: <https://colorfish-kr.lovable.app>
- English: <https://color-vision-spark-en.lovable.app>
- FAQ: <https://bakeyeon.github.io/colorfish/>

## Data and analysis

- The released, anonymized dataset (`anonymized_df.json`, N=9,534 trial-level rows across
  1,159 unique participants) is hosted on OSF: <https://osf.io/xub35/>.
- The SFF scoring pipeline (LLM-based keyword scoring) and all statistical analysis code
  are documented in the paper's appendices and are not part of this repository, which
  covers only the participant-facing data-collection platform.

## Tech stack

React + TypeScript + Vite, with [shadcn/ui](https://ui.shadcn.com/) components and
Tailwind CSS. Originally scaffolded and iteratively developed with
[Lovable](https://lovable.dev).

## Running locally

```sh
npm install
cp .env.example .env   # then fill in your own Google Apps Script web app URLs
npm run dev
```

`.env` requires two endpoints (each a deployed Google Apps Script web app URL used as a
lightweight submission backend):

```
VITE_QUESTIONNAIRE_SCRIPT_URL=
VITE_COLOR_EMOTION_SCRIPT_URL=
```

Other scripts: `npm run build` (production build), `npm run lint`, `npm run preview`.

## Status

This platform is shared for research-reproducibility purposes. It reflects the version
used during the study's data collection period and is not actively maintained.

## Citation

If you use this code or the associated dataset, please cite the paper.

```
@inproceedings{park-2026-grue,
    title = "The Grue Divide: When Cognitive Accuracy Doesn{'}t Predict Affective Alignment",
    author = "Park, Kai",
    editor = "Xu, Shanshan  and
      T.Y.S.S., Santosh  and
      Kurniawan, Kemal  and
      Peng, Siyao  and
      Wallbridge, Sarenne  and
      Koto, Fajri  and
      Dziri, Nouha  and
      Plank, Barbara",
    booktitle = "Proceedings of the First Workshop on Pluralistic {AI} {NLP}: Diversity-aware, Sociotechnical, Responsible Alignment ({PANDORA} 2026)",
    month = oct,
    year = "2026",
    address = "Budapest, Hungary",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2026.pandora-1.2/",
    pages = "35--68",
    ISBN = "979-8-89176-484-2",
    abstract = "This study presents a large-scale, exploratory investigation (9,534 trials from 1,159 participants) of color perception, cognition, and emotion in the Korean ``Grue'' spectrum, finding results consistent with a cognitive advantage for Korean speakers over English-speaking cohorts, particularly in Grue transitions. One illustrative case{---}the ``Australia Divergence''{---}shows comparable cognitive accuracy between Korean and Australian cohorts in a preliminary, small-sample comparison (132 trials) that nonetheless appears to diverge affectively under the Sentiment-Formality-Friendliness (SFF) framework, consistent with a cognitive-affective decoupling in which perceptual precision may be shared across cultures while affective mapping remains culturally distinct. As a correlational, hypothesis-generating study, we offer these findings as a basis for future confirmatory research rather than as definitive claims, positioning SFF as a promising exploratory tool for capturing culturally mediated ``emotional fingerprints'' that traditional cognitive metrics may miss, though further validation against human ratings remains needed."
}
```


## License

Code released under the [MIT License](LICENSE). The associated dataset is released
separately under CC BY 4.0 on OSF.
