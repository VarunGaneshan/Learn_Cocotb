![image](https://github.com/user-attachments/assets/7e897c61-3694-4d33-8ef4-a6839922faf7)![image](https://github.com/user-attachments/assets/3f92fb17-912c-4375-9468-2f05b03653f4)# My Cocotb Journey
COroutine based COsimulation TestBench environment for python verification of RTL design.
![image](https://github.com/user-attachments/assets/c8d9c7c0-cc9d-4828-ab0d-ab31fa73da6c)
   
<details>
 <summary> Environment Set Up  </summary>
  
**Installing prerequisites & iverilog:**

>[Installation](https://docs.cocotb.org/en/stable/install.html)

![Screenshot from 2024-09-05 17-14-05](https://github.com/user-attachments/assets/ed9de94d-3182-42af-839b-d7b8bcde244c)
```bash
sudo apt-get install make python3 python3-pip libpython3-dev
sudo apt-get install iverilog
```

**Possible Error & Fix:**

![Screenshot from 2024-09-05 18-59-17](https://github.com/user-attachments/assets/d5aa1638-c72b-4ca9-85e6-fdcfec9693f0)
```bash
python3 -m venv venv
```
![image](https://github.com/user-attachments/assets/2d4dafc3-2e0f-42fb-abf3-3311c0837016)
```bash
sudo apt-get install python3-venv
python3 -m venv venv
```

**Creating Virtual Environment:**

>This makes sure that the global Python installation isn't corrupted.

![image](https://github.com/user-attachments/assets/5f0eafe0-bb71-47ce-9072-2bceffbd13c1)
```bash
which python3
source venv/bin/activate
```

**Installing necessary packages:**

**Possible Error & Fix: Install missing package**
![image](https://github.com/user-attachments/assets/8633862b-9204-486b-930b-fc3bc513fc1b)
![image](https://github.com/user-attachments/assets/c9ae8d95-a292-487c-9a90-6471b1d133b4)
```bash
pip3 install pytest cocotb cocotb-bus cocotb-coverage
```

![image](https://github.com/user-attachments/assets/c917a725-3593-4227-bccd-9e4691d9e4f9)
```bash
pip3 install wheel
pip3 install pytest cocotb cocotb-bus cocotb-coverage
```

![image](https://github.com/user-attachments/assets/0f928a1f-a1d5-40fa-b6eb-b40ef5bfb9f1)
```bash
ls venv/lib/python3.6/site-packages/
```
> packages sucessfully installed

</details>	

<details>
 <summary> Simulation Example  </summary>

**Using Local Simulation:**

![image](https://github.com/user-attachments/assets/cf7b3c1c-6452-4ed7-a666-bd870b994cad)
```bash
make or
```

**Makefile Structure:**
![image](https://github.com/user-attachments/assets/9f66979d-dbed-441a-b7bb-8525d66a24ef)
```bash
vi Makefile
```
>To exit vim editor - : -> q! enter , for more type vimtutor on terminal

**Using Github actions:**
![image](https://github.com/user-attachments/assets/00572a2b-1709-4e64-92a0-aad3b95ba03e)

>Run or target

![image](https://github.com/user-attachments/assets/fbe83226-1ee7-4470-89ad-4f3cb81d44f3)
```bash
name: learning-cocotb
run-name: ${{ github.actor }} is learning Cocotb
on: [push]
jobs:
  verify:
    runs-on: ubuntu-latest
    timeout-minutes: 3
    steps:
      - uses: actions/checkout@v3
      - run: sudo apt install -y --no-install-recommends iverilog
      - run: pip3 install cocotb cocotb-bus
      - run: make -C tests or
      - uses: actions/upload-artifact@v3
        with:
          name: waveform
          path: tests/*.vcd
      - name: Publish Test Report
        uses: mikepenz/action-junit-report@v3
        if: always() # always run even if the previous step fails
        with:
          report_paths: '**/tests/results.xml'
```
![image](https://github.com/user-attachments/assets/1291efdd-2850-4b49-9b1a-e3eb8fe52e07)

**OR-Waveform**:
![image](https://github.com/user-attachments/assets/6fa8b9ed-51c0-4926-a3dc-9e51af3787c2)
</details>	

<details>
 <summary> Xor Verification  </summary>
 
**Clone the repo locally**:
![image](https://github.com/user-attachments/assets/635dd656-adcd-4fcf-adaa-8f64e8696810)
```bash
git clone https://github.com/learn-cocotb/assignment-xor.git
cd assignment-xor/
cd tests
```
![image](https://github.com/user-attachments/assets/0340622a-2150-4be0-890b-ff2f330469e0)
```bash
vi dut_test.py
```
![image](https://github.com/user-attachments/assets/605f985f-f168-40ba-8565-156b01f3ef4c)
```bash
make
```
</details>	

<details>
 <summary> Or Verification  </summary>
 
 ![image](https://github.com/user-attachments/assets/e67df17f-c3fd-4c21-9f73-22d43ddf2671)

![image](https://github.com/user-attachments/assets/2855e13d-69aa-4ac7-86d9-fc87d23e3fb7)

![image](https://github.com/user-attachments/assets/91efa683-a501-48de-b0d8-a81468314e18)

![image](https://github.com/user-attachments/assets/c572d1e2-482e-46b2-835a-21012d57697c)

![image](https://github.com/user-attachments/assets/c2a77aaf-6252-415e-ad15-8e9fd8190bfe)

![image](https://github.com/user-attachments/assets/b167d14e-82b7-4dc6-be69-a928c52a3369)

![image](https://github.com/user-attachments/assets/3a0c657a-6b1a-40b0-89b3-f396bef4ec1b)

![image](https://github.com/user-attachments/assets/c114b2c6-3bdc-401d-ac03-7941aa691394)

```bash

```

</details>	

## References 
[Docs.cocotb](https://docs.cocotb.org/en/stable/quickstart.html)
