# My Cocotb Journey

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

**Simulation Example**
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







</details>	

## References 
[Docs.cocotb](https://docs.cocotb.org/en/stable/quickstart.html)
