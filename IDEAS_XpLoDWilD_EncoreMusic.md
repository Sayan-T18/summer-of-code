# Idea

Rebuild and expand Encore Music, the open-source centralized music playback app, which noticeably allows people to:

* Listen from any audio source they want through separate plugins with a public API
* Process their audio (bass boost, equalizer, psychoacoustic bass enhancement, ...) through plugins with a public API
* Build unified playlists from all these providers
* Offline playback from compatible providers
* Have a car-compliant UI (drive mode)
* Recognize what's currently playing directly within the app, and search for it
* Cast your music to any computer or Chromecast device

## Background

The Encore Music app is currently available on the Play Store. However, the original plug-ins model and inner workings
of the app have proven to be limited and bug-prone (either due to Android system limitations, since plug-ins are services,
or due to some architectural issues of the app's core). Regardless of that, the app has over 30k installs, and an average
rating of 3.7/5.0.

The goal of the rewrite would be to showcase the potential of the Android OS with a new way to handle plug-ins, and
demonstrate the usefulness of unit tests and instrumented tests on Android.

## Expected Results

The process would go in multiple steps:

1. Rewrite the core of the Encore Music app and plug-ins framework using DEX and resources injection instead of depending
on the Android Services framework, AIDL communication and UNIX sockets to transmit audio data. This rewrite would include
proper testing and a robust architecture that would be useful for other projects to inspire from.

2. Rewrite the Spotify plugin using a port of librespot to either Golang or C++. The current official Spotify SDK is very
limited, and the otherwise libspotify is deprecated and crashes often.

3. Bring up Encore Music to the level it is today in regards to feature, such as Drive mode, voice control, TV support, etc.
while revamping the user interface to be more modern and to take into account the user feedback from the past year.

4. Add new features and/or new providers, depending on how much time remains. There has been a great interest for a SoundCloud
plugin, as well as more choice for sound processing plugins. Collaborative playback is also a feature with great interest, and
Automix would be revamped to use GraceNote's Rythm API, which allows customized results based on the user's library, and not
limited to specific providers.

## More Information

More information on Encore Music can be found here :

https://www.encoremusic.io/
https://github.com/fastbootmobile/encore


## Required Skills

This project will require a deep understanding of the following:

* Android Java development
* Deep knowledge of Java classes injection, Android resources injection
* C++ and/or Go development
* Testing theory, robust application architecture
* Android sound playback pipeline, and general music theory

## Optinal skills (You will learn during the project)

* Use of GIT base source management systems
* Code reviewing practice
* Java <-> C(++)/Go bindings via JNI


## Mentor(s)

* XpLoDWilD
* Jerdog


## Difficulty Level

Medium / Moderate


## XDA Handle

* XpLoDWilD
