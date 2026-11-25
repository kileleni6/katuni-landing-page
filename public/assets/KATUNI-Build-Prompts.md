# KATUNI app build prompt

Build an Android-first app called KATUNI: Voice Recorder with the tagline “Pick up where you left off.”

Make Record → Pause → Replay → Continue the main workflow. While paused, offer replay of the last 10, 20 or 30 seconds and full playback. Continue stops playback and appends audio at the end of the same recording. Preserve all previous audio. Save drafts locally as recording progresses and let users reopen and continue them.

Use three tabs — Record, Library and Write — with Settings in the header. The Library supports search, rename, bookmark navigation, WAV export, sharing, Trash, restore and confirmed permanent deletion. Write offers a manually scrolling script with adjustable text size and phrase-based dictation through the phone’s speech provider. Explain when that provider may require the internet. Basic recording, replay and draft saving work offline without an account.

For saved-audio transcription, send audio through KATUNI’s HTTPS backend after the user confirms the upload. The backend calls a configurable speech-to-text API. Provide a working integration for one selected provider and a stable mobile-facing API so that other providers can be added later.

Provide optional text actions for punctuation cleanup, filler removal, summarization and script drafting. Run these through a separately configurable LLM API. Send only the transcript text needed for the chosen action. Preserve original audio, original recognition output and user edits. Let the user review a generated result before saving it.

Keep real API credentials in the backend’s local .env file for development and the hosting provider’s secret environment settings in production. Include an .env.example with placeholder fields for STT_PROVIDER, STT_API_KEY, STT_MODEL, LLM_PROVIDER, LLM_API_KEY and LLM_MODEL. The mobile app uses only the backend URL. Exclude real .env files from source control and redact credentials from logs.

Handle microphone permission denial, provider errors, offline requests, upload limits, interrupted calls, storage exhaustion and failed exports while preserving completed local audio. Show upload and processing status and support retries. Publish the selected processors, retention and deletion behavior in the privacy information before enabling hosted processing.

Use warm ivory #F8F6EF, forest green #17583D, ink #1C251E and pale lime #E3EDC7. Follow the supplied KATUNI mockups and use clear text controls and large touch targets.

Deliver editable Android and backend source, setup instructions, an .env.example and an installable Android preview. Preserve the existing application ID and saved recordings when updating an existing KATUNI build.

Acceptance test — record “Part one,” pause, replay it and continue with “Part two.” Reopened playback and the exported WAV must contain both parts in order without duplicated replay audio. Transcription and a text-editing action must preserve the original transcript.

This prompt describes requested development. The bundled APK is the earlier Android preview, which accepts a configured transcription endpoint. Implement and verify any new provider integrations before advertising them as available.
