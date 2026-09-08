
reduces network congestion of small network packets

accumulates small network packets and sends them as one big TCP message

Reduces network overhead as each TCP message has a header of 20 to 60 bytes

Keyboard strokes could benefit from this

Should be turned off in HFT using `TCP_NODELAY`, avoiding latency on packet buffering

Best worked with a sliding window.

https://www.lifewire.com/nagle-algorithm-for-tcp-network-communication-817932

https://github.com/mrafay-dev/LowLevelDev/blob/main/MyntBitChallenges/NaglesAlgo.cpp


