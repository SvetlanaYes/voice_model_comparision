# voice_model_comparision
 
 model_1: stt_en_quartznet15x5
 
 model_2: stt_en_fastconformer_ctc_large

 Dataset: LibriSpeech mini

 
The stt_en_fastconformer_ctc_large model and the stt_en_quartznet15x5 model are both utilized for Automatic Speech Recognition (ASR) tasks, yet they employ distinct architectures and characteristics. **stt_en_fastconformer_ctc_large** relies on the **Transformer-based FastConformer architecture**, offering robust contextual understanding and capturing long-range dependencies in speech signals, making it suitable for tasks requiring intricate language structures. In contrast, **stt_en_quartznet15x5** employs the lightweight QuartzNet architecture, which has **CNN-based architecture**, prioritizing efficiency and speed while maintaining considerable accuracy, making it well-suited for real-time applications or scenarios with resource constraints. The choice between the two models depends on the specific requirements of the ASR task, considering factors such as computational resources, robustness to noise, and the need for contextual understanding.

As the stt_en_fastconformer_ctc_large model employs a Transformer-based architecture, it excels in capturing long-range dependencies. This characteristic is evident in the comparison where it outperforms the CNN-based stt_en_quartznet15x5 model on audio files longer than 15 seconds, as depicted in the accompanying video, where WER for fastconformer transcriptions are mostly low.

[video] https://drive.google.com/file/d/1Q08v6Ss_QQl3xX6VA28RVvjx6fJ0qtRP/view?usp=drive_link

In this example we can see that Fastconformer understands the context and generates terrorist not terrace.
![image](https://github.com/SvetlanaYes/voice_model_comporision/assets/91842237/f5452cd9-8243-4bde-84e4-e2ca9cbfb517)

In many examples quartznet has problem with separating words in audio, for example
![image](https://github.com/SvetlanaYes/voice_model_comporision/assets/91842237/566d3a00-2079-4d9b-8006-592d417810c0)

In this example, both models perform well, and both spellings are correct. However, the issue with Word Error Rate (WER) is that it doesn't take into account words that can be written in different forms.
![image](https://github.com/SvetlanaYes/voice_model_comporision/assets/91842237/bd7f2ad1-4006-4e84-88ec-91dd6c757c6b)


For words that occur fewer than 5 times in the training dataset, the count of instances where the accuracy of model_1 is less than 90 and the accuracy of model_2 is greater than 90 is 85. Conversely, in the reverse scenario where the accuracy of model_1 is greater than 90 and the accuracy of model_2 is less than 90, the count of instances is 16. This suggests that for rarely occurring words, the FastConformer model performs better.

![image](https://github.com/SvetlanaYes/voice_model_comporision/assets/91842237/e9081fa6-5c34-4033-ac36-ddc10a1321f0)
![image](https://github.com/SvetlanaYes/voice_model_comporision/assets/91842237/b65f27ff-5f1a-4a2c-ae57-9d308bc3a55a)

Same we can see on the dev dataset.

![image](https://github.com/SvetlanaYes/voice_model_comporision/assets/91842237/8562bd05-55b5-4c7e-b3ba-db6c470b79be)
![image](https://github.com/SvetlanaYes/voice_model_comporision/assets/91842237/0f4991f9-fede-4c8e-a54f-b9d6dd83e3e6)
