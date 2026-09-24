# SenseVoice small · 中文 日本語 한국어 English

`sense-voice-small`

Chinese, Cantonese, Japanese, Korean and English in one model, and the most accurate English here: 7.4% WER and 3.4% CER on a hundred FLEURS en clips, ahead of every English-only model in this registry. Those figures were blank until somebody ran the benchmark, and a blank is not neutral — Summo scores an unmeasured model as if it got every word wrong, so the best English model here was ranked last for English. Ships as an int8 export and a full-precision one; the app takes full precision wherever it fits and drops to int8 only on a machine without the memory, which is why the size on the card is not a single fixed number. The figures above are the full-precision export, the one most machines get; int8 scores 7.5% and 3.5% on the same clips and runs about a third faster, so the trade is speed rather than accuracy here. No Vietnamese — for a Vietnamese meeting this is the wrong model, however good it is at the five it does cover.

| | |
|---|---|
| Task | speech recognition |
| Mode | live |
| Languages | zh, yue, ja, ko, en |
| Size | 228 MB |
| Licence | FunASR Model Open Source License Agreement v1.1 |
| Runtime | `sherpa-onnx/sense-voice` |

## Where this comes from

Published by FunAudioLLM / Alibaba Tongyi SpeechTeam, ONNX export by csukuangfj.

**Not redistributed by Summo.** The download goes to the original host under that project's own terms. Summo is the software that can load the file; it is not the distributor of it.

## What it costs

Memory: about 300 MB resident, 800 MB at peak. Needs at least 1536 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_4t` | 0.047 |
| `cpu_x86_avx512vnni_8t` | 0.035 |

Accuracy, measured — word error rate, lower is better:

| Benchmark | Score |
|---|---|
| `cer_fleurs_en` | 3.4% |
| `wer_fleurs_en` | 7.4% |

Accelerators: cpu, coreml, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `model.int8.onnx` | 228 MB | `c71f0ce00bec95b07744e116345e33d8cbbe08cef896382cf907bf4b51a2cd51` |
| `tokens.txt` | 308 KB | `f449eb28dc567533d7fa59be34e2abca8784f771850c78a47fb731a31429a1dc` |
| `model.onnx` | 894 MB | `977016bd9c79f9eb343430b5cc305e07ab64d5212dff41b0dcfa1694bee9a8cb` |

## From the publisher

Reproduced verbatim from the project that published these weights. Summo did not write it and has not edited it.

<!-- upstream:begin -->

---
license: other
license_name: model-license
license_link: https://github.com/modelscope/FunASR/blob/main/MODEL_LICENSE
language:
- zh
- en
- ja
- ko
- yue
- multilingual
library_name: funasr
pipeline_tag: automatic-speech-recognition
tags:
- speech-recognition
- asr
- emotion-recognition
- audio-event-detection
- multilingual
- non-autoregressive
- whisper-alternative
- real-time
- voice-ai
---
([简体中文](./README_zh.md)|English|[日本語](./README_ja.md))

<div align="center">

### ⭐ Powered by [FunASR](https://github.com/modelscope/FunASR) — please give us a GitHub Star!

SenseVoice is part of the **FunASR** ecosystem — one industrial-grade open-source toolkit for **ASR · VAD · punctuation · speaker diarization · emotion / event · LLM-ASR**. A Star really helps the project (and keeps you updated):

[**🌟 FunASR**](https://github.com/modelscope/FunASR)  ·  [**🌟 SenseVoice**](https://github.com/FunAudioLLM/SenseVoice)  ·  [**🌟 Fun-ASR**](https://github.com/FunAudioLLM/Fun-ASR)  ·  [**🌟 FunClip**](https://github.com/modelscope/FunClip)

</div>

> ⚡ **CPU / edge — no GPU, no Python:** run SenseVoiceSmall as a single self-contained binary via **llama.cpp / GGUF** (like whisper.cpp), with built-in VAD. Prebuilt binaries + one-command model download → [SenseVoiceSmall-GGUF](https://huggingface.co/FunAudioLLM/SenseVoiceSmall-GGUF) · [runtime](https://github.com/modelscope/FunASR/tree/main/runtime/llama.cpp) · [guide](https://www.funasr.com/en/blog/funasr-llama-cpp-whisper-cpp-alternative.html)



# Introduction

github [repo](https://github.com/FunAudioLLM/SenseVoice) : https://github.com/FunAudioLLM/SenseVoice

SenseVoice is a speech foundation model with multiple speech understanding capabilities, including automatic speech recognition (ASR),  spoken language identification (LID), speech emotion recognition (SER), and audio event detection (AED). 

<img src="image/sensevoice2.png">

[//]: # (<div align="center"><img src="image/sensevoice.png" width="700"/> </div>)

<div align="center">  
<h4>
<a href="https://fun-audio-llm.github.io/"> Homepage </a>
｜<a href="#What's News"> What's News </a>
｜<a href="#Benchmarks"> Benchmarks </a>
｜<a href="#Install"> Install </a>
｜<a href="#Usage"> Usage </a>
｜<a href="#Community"> Community </a>
</h4>

Model Zoo:
[modelscope](https://www.modelscope.cn/models/iic/SenseVoiceSmall), [huggingface](https://huggingface.co/FunAudioLLM/SenseVoiceSmall)

Online Demo:
[modelscope demo](https://www.modelscope.cn/studios/iic/SenseVoice), [huggingface space](https://huggingface.co/spaces/FunAudioLLM/SenseVoice)


</div>


<a name="Highligts"></a>
# Highlights 🎯
**SenseVoice** focuses on high-accuracy multilingual speech recognition, speech emotion recognition, and audio event detection.
- **Multilingual Speech Recognition:** Trained with over 400,000 hours of data, supporting more than 50 languages, the recognition performance surpasses that of the Whisper model.
- **Rich transcribe:** 
  - Possess excellent emotion recognition capabilities, achieving and surpassing the effectiveness of the current best emotion recognition models on test data.
  - Offer sound event detection capabilities, supporting the detection of various common human-computer interaction events such as bgm, applause, laughter, crying, coughing, and sneezing.
- **Efficient Inference:** The SenseVoice-Small model utilizes a non-autoregressive end-to-end framework, leading to exceptionally low inference latency. It requires only 70ms to process 10 seconds of audio, which is 15 times faster than Whisper-Large.
- **Convenient Finetuning:** Provide convenient finetuning scripts and strategies, allowing users to easily address long-tail sample issues according to their business scenarios.
- **Service Deployment:** Offer service deployment pipeline,  supporting multi-concurrent requests, with client-side languages including Python, C++, HTML, Java, and C#, among others.

<a name="What's News"></a>
# What's New 🔥
- 2024/7: Added Export Features for [ONNX](https://github.com/FunAudioLLM/SenseVoice/demo_onnx.py) and [libtorch](https://github.com/FunAudioLLM/SenseVoice/demo_libtorch.py), as well as Python Version Runtimes: [funasr-onnx-0.4.0](https://pypi.org/project/funasr-onnx/), [funasr-torch-0.1.1](https://pypi.org/project/funasr-torch/)
- 2024/7: The [SenseVoice-Small](https://www.modelscope.cn/models/iic/SenseVoiceSmall) voice understanding model is open-sourced, which offers high-precision multilingual speech recognition, emotion recognition, and audio event detection capabilities for Mandarin, Cantonese, English, Japanese, and Korean and leads to exceptionally low inference latency.  
- 2024/7: The CosyVoice for natural speech generation with multi-language, timbre, and emotion control. CosyVoice excels in multi-lingual voice generation, zero-shot voice generation, cross-lingual voice cloning, and instruction-following capabilities. [CosyVoice repo](https://github.com/FunAudioLLM/CosyVoice) and [CosyVoice space](https://www.modelscope.cn/studios/iic/CosyVoice-300M).
- 2024/7: [FunASR](https://github.com/modelscope/FunASR) is a fundamental speech recognition toolkit that offers a variety of features, including speech recognition (ASR), Voice Activity Detection (VAD), Punctuation Restoration, Language Models, Speaker Verification, Speaker Diarization and multi-talker ASR.

<a name="Benchmarks"></a>
# Benchmarks 📝

## Multilingual Speech Recognition
We compared the performance of multilingual speech recognition between SenseVoice and Whisper on open-source benchmark datasets, including AISHELL-1, AISHELL-2, Wenetspeech, LibriSpeech, and Common Voice. In terms of Chinese and Cantonese recognition, the SenseVoice-Small model has advantages.

<div align="center">  
<img src="image/asr_results1.png" width="400" /><img src="image/asr_results2.png" width="400" />
</div>

## Speech Emotion Recognition

Due to the current lack of widely-used benchmarks and methods for speech emotion recognition, we conducted evaluations across various metrics on multiple test sets and performed a comprehensive comparison with numerous results from recent benchmarks. The selected test sets encompass data in both Chinese and English, and include multiple styles such as performances, films, and natural conversations. Without finetuning on the target data, SenseVoice was able to achieve and exceed the performance of the current best speech emotion recognition models.

<div align="center">  
<img src="image/ser_table.png" width="1000" />
</div>

Furthermore, we compared multiple open-source speech emotion recognition models on the test sets, and the results indicate that the SenseVoice-Large model achieved the best performance on nearly all datasets, while the SenseVoice-Small model also surpassed other open-source models on the majority of the datasets.

<div align="center">  
<img src="image/ser_figure.png" width="500" />
</div>

## Audio Event Detection

Although trained exclusively on speech data, SenseVoice can still function as a standalone event detection model. We compared its performance on the environmental sound classification ESC-50 dataset against the widely used industry models BEATS and PANN. The SenseVoice model achieved commendable results on these tasks. However, due to limitations in training data and methodology, its event classification performance has some gaps compared to specialized AED models.

<div align="center">  
<img src="image/aed_figure.png" width="500" />
</div>

## Computational  Efficiency

The SenseVoice-Small model deploys a non-autoregressive end-to-end architecture, resulting in extremely low inference latency. With a similar number of parameters to the Whisper-Small model, it infers more than 5 times faster than Whisper-Small and 15 times faster than Whisper-Large. 

<div align="center">  
<img src="image/inference.png" width="1000" />
</div>


# Requirements

```shell
pip install -r requirements.txt
```

<a name="Usage"></a>
# Usage

## Inference

Supports input of audio in any format and of any duration.

```python
from funasr import AutoModel
from funasr.utils.postprocess_utils import rich_transcription_postprocess

model_dir = "FunAudioLLM/SenseVoiceSmall"


model = AutoModel(
    model=model_dir,
    vad_model="fsmn-vad",
    vad_kwargs={"max_single_segment_time": 30000},
    device="cuda:0",
    hub="hf",
)

# en
res = model.generate(
    input=f"{model.model_path}/example/en.mp3",
    cache={},
    language="auto",  # "zn", "en", "yue", "ja", "ko", "nospeech"
    use_itn=True,
    batch_size_s=60,
    merge_vad=True,  #
    merge_length_s=15,
)
text = rich_transcription_postprocess(res[0]["text"])
print(text)
```

Parameter Description:
- `model_dir`: The name of the model, or the path to the model on the local disk.
- `vad_model`: This indicates the activation of VAD (Voice Activity Detection). The purpose of VAD is to split long audio into shorter clips. In this case, the inference time includes both VAD and SenseVoice total consumption, and represents the end-to-end latency. If you wish to test the SenseVoice model's inference time separately, the VAD model can be disabled.
- `vad_kwargs`: Specifies the configurations for the VAD model. `max_single_segment_time`: denotes the maximum duration for audio segmentation by the `vad_model`, with the unit being milliseconds (ms).
- `use_itn`: Whether the output result includes punctuation and inverse text normalization.
- `batch_size_s`: Indicates the use of dynamic batching, where the total duration of audio in the batch is measured in seconds (s).
- `merge_vad`: Whether to merge short audio fragments segmented by the VAD model, with the merged length being `merge_length_s`, in seconds (s).

If all inputs are short audios (<30s), and batch inference is needed to speed up inference efficiency, the VAD model can be removed, and `batch_size` can be set accordingly.
```python
model = AutoModel(model=model_dir, device="cuda:0", hub="hf")

res = model.generate(
    input=f"{model.model_path}/example/en.mp3",
    cache={},
    language="zh", # "zn", "en", "yue", "ja", "ko", "nospeech"
    use_itn=False,
    batch_size=64, 
    hub="hf",
)
```

For more usage, please refer to [docs](https://github.com/modelscope/FunASR/blob/main/docs/tutorial/README.md)

### Inference directly

Supports input of audio in any format, with an input duration limit of 30 seconds or less.

```python
from model import SenseVoiceSmall
from funasr.utils.postprocess_utils import rich_transcription_postprocess

model_dir = "FunAudioLLM/SenseVoiceSmall"
m, kwargs = SenseVoiceSmall.from_pretrained(model=model_dir, device="cuda:0", hub="hf")
m.eval()

res = m.inference(
    data_in=f"{kwargs['model_path']}/example/en.mp3",
    language="auto", # "zn", "en", "yue", "ja", "ko", "nospeech"
    use_itn=False,
    **kwargs,
)

text = rich_transcription_postprocess(res[0][0]["text"])
print(text)
```

### Export and Test (*On going*)
Ref to [SenseVoice](https://github.com/FunAudioLLM/SenseVoice)
## Service

Ref to [SenseVoice](https://github.com/FunAudioLLM/SenseVoice)

## Finetune

Ref to [SenseVoice](https://github.com/FunAudioLLM/SenseVoice)

## WebUI

```shell
python webui.py
```

<div align="center"><img src="image/webui.png" width="700"/> </div>

<a name="Community"></a>
# Community
If you encounter problems in use, you can directly raise Issues on the github page.

You can also scan the following DingTalk group QR code to join the community group for communication and discussion.

|                           FunAudioLLM                            |                          FunASR                          |
|:----------------------------------------------------------------:|:--------------------------------------------------------:|
| <div align="left"><img src="image/dingding_sv.png" width="250"/> | <img src="image/dingding_funasr.png" width="250"/></div> |

<!-- upstream:end -->
