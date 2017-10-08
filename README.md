# graycode

This is an HTML/JS [Gray Code](https://en.wikipedia.org/wiki/Gray_code) generator. It is intended to be opened in a browser even from a local hard drive and moved around as a single file. It uses jQuery and jQuery Mobile for presentation.

The intent (other than the mental exercise of determining the gray code sequence) is to demonstrate offloading of the logic to the client machine. This is a case where generating the sequence on a webserver and sending it to the browser with every setting change would be highly problematic. In informal testing using Firefox 56.0 on a Macbook Pro the calculation took roughly eight seconds and the browser rendering took about forty.

This calculation could certainly be done more rapidly on a server, perhaps even by generating the sequence with a compiled C program. However, if that server were to get multiple concurrent requests the CPU load could become prohibitive. Having the client's machine run the math is good "division of labor".

Furthermore, the binary sequence of the 22-bit gray code sequences is around 100MB of text. Sending that across a WAN especially on residential DSL bandwidth would be prohibitive even if the server was not bottlenecked. Even gzip compression (which does an excellent job of compressing this data) reduces the amount that would be transferred to about 10MB of text.