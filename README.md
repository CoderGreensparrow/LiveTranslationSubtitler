# LiveWhisperSubtitler
Combining technologies from here and there, this project is about semi-live (actually, live with a delay) translated subtitles over live content.

---

## (The) idea(s):

1. Use some way to know when to start and end a chunk for Whisper.
2. Use Whisper by OpenAI in a way where it transcribes semi-live (live with a delay/delays).
   These first two parts could be governed by this: https://github.com/collabora/WhisperLive (also check out https://github.com/alesaccoia/VoiceStreamAI and https://github.com/davabase/whisper_real_time)
3. The transcription from Whisper is translated with an API translation service.
4. Using the time information from Whisper, subtitles are crafted with the translations. If a subtitle would be too long to look good, it may be cut in half, to thirds, possibly fourths, depending on the length.
5. Since there is a delay involved, the live video and audio content could be delayed so that the user in the end recieves subtitles seemingly "live". This means that, in realty, all the content the user recieves is delayed: the video and audio content and the subtitles. The system used here would shift everything by a set, fixed time, like a few minutes. This way, Whisper and other systems can have enough time to do their job and the viewer should have a smooth experience, even if delayed.

If a user wouldn't want to delay the original content, here's another system:

1. See step 1 above
2. See step 2 above
3. See step 3 above
4. The subtitles are placed over the content regardless of time information from Whisper. As new translations are created, the subtitles change. The video and audio content is not delayed on purpose. The subtitles will be delayed due to the system working the way it does.

These two could be implemented as two modes of the same software.

---

Check out https://patrikzudel.me/ai-subtitles
