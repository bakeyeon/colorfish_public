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

If you use this code or the associated dataset, please cite the paper (citation details
to be added upon publication).

## License

Code released under the [MIT License](LICENSE). The associated dataset is released
separately under CC BY 4.0 on OSF.
