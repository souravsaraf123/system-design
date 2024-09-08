# Features a Web Hosting Provider Should Provide

1. **Availability**
2. **SFTP instead of FTP**
   - Use SFTP to ensure username/password traffic is encrypted.
3. **Geographical Accessibility**
   - Ensure the provider is not blocked in certain countries (e.g., if a country like China blocks GoDaddy, then the website can't be accessed by users in China).
4. **Avoid Shared Web Hosting**
   - Shared hosting means you don't have access to the machine. Opt for VPS (Virtual Private Server). For example, EC2 is a VPS.

## VPS (Virtual Private Server)

- You get a copy of the OS with more controls. It is a slice of a large machine, which is divided into multiple virtual computers via software like Hypervisor.
- **Difference from Shared Web Hosting:**
  - With VPS, you have access to a machine where no other users have accounts.

## Vertical Scaling

### CPU

- **Single Core, Dual Core, Quad Core, Hyperthreading**

  - Number of instructions that can be performed at once:
    - Quad Core means 4 instructions.
    - Hyperthreading means one core can be split into 4 or more threads and can perform multiple instructions simultaneously.

- **L1, L2, L3 Cache**
  - Cache memory acts as a buffer between the CPU and the main memory (RAM), speeding up data access.
    - **L1 Cache**: Closest to the CPU, hence the fastest.
    - **L2 Cache**: Larger than L1 but slower.
    - **L3 Cache**: Largest cache, usually slower than L1 and L2.

### Disk

- **PATA, SATA, SAS**
  - Mechanical hard drives: SATA is common for desktops (3.5 inch) and laptops (2.5 inch) and spins at 7200 RPM. SAS spins at 15000 RPM.
- **SSD**
  - Electronic hard drive, faster than mechanical drives as it has no moving parts. Costly.
- **RAID** : Redundant Array of Independent Disks – is a type of storage that writes data across multiple drives within the same system. So that one or more hard drives can fail and still there wont be any data loss. Later we can replace the faulty one with a new hard drive and then we can have redundance again (it will automatically create a redundant copy). [Video from 35:37](https://youtu.be/-W9F__D3oY4?t=2137)

### RAM

## Horizontal Scaling

- Instead of buying top-notch expensive machines, buy more cheaper machines and distribute the load among them.

<p align="center">
  <img src="../images/load balancer.png" width="480">
  <br/>
</p>

- #### Advantages of a load balancer :

  - only the load balancer's IP need to be public, the server1, server2 etc IP addresses can be private.

  - This helps since IPv4 are exhausting.

  - Also, more secure since now people cant get direct access to server1.

  - We can decide on how to distribute load between our servers. Few strategies to do load balancing are :
    - Round robin (based on luck , a single server can get bombarded , not good)
    - Based on load
    - Other user related heuristics
