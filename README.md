![image](https://github.com/user-attachments/assets/a43d63db-3b2b-47a2-9f2f-bafaf029fce4)![image](https://github.com/user-attachments/assets/afa7e09b-3bcd-4547-8c46-3b6517c84305)# My Cocotb Journey

<details>
 <summary> Local Environment Set Up  </summary>
  
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

**Possible Error & Fix:**
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

Waveform:
![image](https://github.com/user-attachments/assets/6fa8b9ed-51c0-4926-a3dc-9e51af3787c2)
</details>	

<details>
 <summary> Xor Verification  </summary>
 
![image](https://github.com/user-attachments/assets/635dd656-adcd-4fcf-adaa-8f64e8696810)

![image](https://github.com/user-attachments/assets/0340622a-2150-4be0-890b-ff2f330469e0)

![image](https://github.com/user-attachments/assets/605f985f-f168-40ba-8565-156b01f3ef4c)

</details>	

## References 
[Docs.cocotb](https://docs.cocotb.org/en/stable/quickstart.html)
