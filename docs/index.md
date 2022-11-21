## Introduction

This page documents the process of installing and testing an audio transcription demonstration application based on the open-source automatic speech recognition (ASR) system called [Whisper](https://openai.com/blog/whisper/), released on September 21, 2022 by OpenAI.  

Whisper is a deep neural network trained on a large (680,000 hours of recordings) and diverse dataset collected from the web.  It represents a new milestone in speech recognition with "improved robustness to accents, background noise and technical language" among other advertised features.

## Background

The effort to research and investigate an easy to deploy practical ASR application was supported by a grant from the [Institute of Museum and Library Sciences](https://www.imls.gov/) (IMLS) as part of the “Re-Imagining Access” project carried out by the members of faculty, staff and students at the ArtCenter College of Design.

During the summer of 2021, students from the studio course instructed by Elise Co, Robert Dirig, Josh Halstead, & Todd Masilko proposed the "Double Check" prototype concept as part of an answer to a question: "How might we design an archive system that ensures accessibility from beginning to end?"  The term accessibility in this context refers to the need to make archive resources designed for individuals with disabilities in mind.

The students identified a list of potential use cases and corresponding capability requirements, rated according to their priority for the accessibility checker prototype concept.  Automatic transcription of archived audio and video files was identified as one high priority item on this list.  This accessibility feature was subsequently chosen as a focus of an investigation into a potential functional solution that could in principle be integrated as a feature of the archival systems employed by ArtCenter and other institutions.

## Audience

The primary purpose of this document is to provide some context and to outline the practical instructions for how to deploy a sample ASR application, which may be of interest to anyone engaged with archival systems or simply looking for a resource to walk through the process step by step.

There are many other online resources and tutorials covering the specifics of software installation, typically written by and for programmers.  While we also assume a certain level of technical familiarity with software development, such as  the use of command line tools, an attempt is made to provide some of the more basic instructions and contextual explanations that may be helpful for a non-programmer audience.

## Archival Software

As a starting point in identifying the technical platform for a functional feature demonstration we surveyed three popular archival software systems: [Archivematica](https://archivematica.org/), [ArchivesSpace](https://archivesspace.org/), and [Preservica](https://preservica.com/).

Each of these systems offers a full-featured archival and digital preservation solution, used by major institutions and organizations around the world.  As with all technical systems, there are significant differences in approach inherent in each solution, summarized briefly below.

[TODO: summary of archival software options]

## Archivematica Architecture

[TODO: summary of Archivematica as a collection of microservices]

[TODO: explanation of how auto-transcription could work within Archivematica workflow]

## Whisper ASR Demo

[TODO: explanation of the standalone Whisper demo]

### Installation Requirements

Whisper requires Python version 3.7 or above.  Most computers come with Python pre-installed.  To check the version installed on your computer, open the command line (Terminal application on MacOS or Linux, Terminal or PowerShell on Windows) and type:

```
python --version
```

If needed, Python installation can be upgraded using the official installer from [https://www.python.org/downloads/](https://www.python.org/downloads/)

Whisper also requires the audio-processing library [ffmpeg](https://ffmpeg.org/).  In order to install it on the command line, run the command appropriate for your operating system:

```
# Linux
sudo apt update && sudo apt install ffmpeg

# MacOS
brew install ffmpeg

# Windows
choco install ffmpeg
```

### Virtual Environment Setup

Prior to proceeding with the installation of necessary Python libraries, we recommend setting up a virtual environment that will contain project dependencies.  To learn more about Python virtual environments, visit [www.realpython.com/python-virtual-environments-a-primer/](https://realpython.com/python-virtual-environments-a-primer/)

To set up a virtual environment within the current project directory and activate it, type the following on the command line:

```
python -m venv venv

# MacOS or Linux
source venv/bin/activate

# Windows
venv\Scripts\activate
```

If setup was successful, the command line prompt should now display the name of the virtual environment in parentheses - in this case `(venv)`  
