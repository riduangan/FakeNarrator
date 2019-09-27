# FakeNarrator
A FakeNarrator screen reader application to replace the Windows built-in Narrator

Chinese advanced persistent threat (APT) group conducting attacks against technology companies located in south-east Asia. 


The attackers use a modified version of a Chinese open-source backdoor called PcShare as their main foothold on the victim's machine. The backdoor is specifically tailored to the needs of the campaign, with additional command-and- control (C&C) encryption and proxy bypass functionality, and any unused functionality removed from the code. It arrives with a bespoke loader utilizing DLL sideloading technique.

After gaining access to the victim’s machine, the attackers deploy a range of post-exploitation tools, many of them based on publicly available code often found on Chinese programming portals. One of these tools stood out, a bespoke Trojan that abuses Microsoft Accessibility Features to gain SYSTEM-level access on the compromised machine in a way similar to the infamous "Sticky Keys" attack. In this case, instead of replacing the usual sethc.exe or utilman.exe binaries, the attackers chose to Trojanize the Narrator executable - a Windows utility that reads aloud the text on the screen and can be invoked on the login screen with a keyboard shortcut. The use of Fake Narrator to gain SYSTEM-level access to the victim’s machine suggests the attackers are interested in maintaining a long-term foothold.

The campaign is characterized by a fair level of stealthiness as the threat actor made a concerted effort to avoid detection. The use of DLL side-loading technique together with a bespoke loader utilizing memory injection ensures that the main backdoor binary is never dropped to the disk. A simple but effective anti-sandboxing technique of payload encoding based on execution path is also implemented to avoid detection. The C&C infrastructure is protected by a level of indirection. The configuration supplied by the loader is passed as plain text, but the URL it contains is not the real C&C address. It instead points to a remote file that provides the actual details to be used in the C&C communication. This allows the attackers to easily change the preferred C&C address, decide the timing of the communication, and – by applying server-side filtering – restrict revealing the real address to requests coming from specific regions or at specific times.

SHA256 - IOC

c5226bfd53d789a895559e8bcbedc4ecdde543e54a427b1cb4e5d7ef90756daa
1899b3d59a9dc693d45410965c40c464224160bbef596f51d35fda099d609744
bd345155aa4baa392c3469b9893a4751c2372ae4923cf05872bcdc159b9596f8
49b86ae6231d44dfc2ff4ad777ea544ae534eb40bd0209defffec1eb1fe66b34
0022508fd02bb23c3a2c4f5de0906df506a2fcabc3e841365b60ba4dd8920e0c




Credit:
https://threatvector.cylance.com/en_us/home/pcshare-backdoor-attacks-targeting-windows-users-with-fakenarrator-malware.html
