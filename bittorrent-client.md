---
permalink: /bittorrent-client
layout: base
---

# Bittorrent Client

<a href="https://GitHub.com/gsconner/bittorrent-client"><strong>GitHub page</strong></a>

<p>A Python implementation of a BitTorrent client as defined in the <a href="https://www.bittorrent.org/beps/bep_0003.html">official BitTorrent specification</a>. It is capable of HTTP and UDP communication with public BitTorrent trackers, and peer-to-peer
communication with other BitTorrent clients via TCP. For detailed documentation on the protocol, read this <a href="https://wiki.theory.org/BitTorrentSpecification">Wiki page</a>.</p>

<p>Uses a bencode library to read .torrent files and extract the information needed to communicate with the tracker and join the swarm. It does this automatically when given the filename of a torrent file through the command line.</p>

<p>Capable of communicating to the tracker via HTTP or UDP, whichever is appropriate. Once it has the appropriate information, it begins communicating with peers as provided by the tracker. It is able to communicate with any peer following the BitTorrent protocol correctly, including commercial clients like uTorrent and qBittorrent</p>

<p>This project was originally created in collaboration in a team of four. I was solely responsible for implementing TCP communication and managing
    data exchange between clients, and worked on the main bittorrent.py file a lot as well. I've also made additions independently after uploading the project to my GitHub.</p>

## History

<p>Jul 10, 2024: Project uploaded to GitHub</p>

<p>Sep 14, 2024: I wrote a new file that replaces filesystem.py, but with the capability of downloading torrent files with nested folders and multiple files.</p>

<p>Oct 17, 2024: Reworked tracker.py to allow for UDP connections and multiple connections.</p>