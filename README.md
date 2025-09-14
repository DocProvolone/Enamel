# ⚡ [Enamel] – MetaTrader 5 Expert Advisor

[![Made with MQL5](https://img.shields.io/badge/Made%20with-MQL5-blue.svg)](https://www.mql5.com/en/docs)   
[![GitHub stars](https://img.shields.io/github/stars/DocProvolone/Enamel.svg?style=social)](https://github.com/DocProvolone/Enamel/stargazers)

---

## 🚀 Introduction
**Enamel** is a free, open-source Expert Advisor for **MetaTrader 5 (MT5)**.  
It is designed to **trade selected USD pairs, using a "Trend Pullback" strategy, giving users full customization over its parameters both in trading logic and risk management**.

✅ Free to use  
✅ Open-source and fully customizable  
✅ Live-tested  
✅ Robust & full of security features  
✅ Plug & play with MT5  

---

## 📦 Installation

You can either compile your own version of the Enamel Expert Advisor, giving you the choice to select how to compile it and modify everything in its logic (using the ` .mq5 ` file in the repository),
or install the pre-compiled `.ex5` Expert Advisors using the instructions below.

### 📦 Installing using the precompiled EA


1. Clone this repository or download the `.zip`:  
   ```bash
   git clone https://github.com/DocProvolone/Enamel
2. Select a version compatible with your CPU:  
      The EA is compiled for both AVX2 capable processors (a more optimized, faster and more energy hungry version)  
      and non-comptabile X64 processors.  
      You can check your producer supported instructions set using free tools such as CPU-Z from CPUID (link to official website: https://www.cpuid.com/softwares/cpu-z.html)  
      If in doubt, or don't want to check your producer compatibility, use the X64 version.  
3. Copy the selected EA file (either AVX2 or X64) into your MT5 Experts folder:  
   ` MQL5/Exeprts/ `  
4. Restart MetaTrader 5 (or right-click Navigator → Refresh).  
5. The EA will appear under Navigator → Expert Advisors.  
✅ You now have succesfully installed the Expert Advisor! You can check below how to use and optimize it.

### 💻 Compiling your own EA  
1. Clone this repository or download the `.zip`:  
   ```bash
   git clone https://github.com/DocProvolone/Enamel  
2. Open MetaEditor 5 and locate your ` .mq5 ` file using the navigator menu.  
3. Feel free to customize and apply any sorts of modifications you'd like!  
4. In the upper menu, select "compile".  
5. You will be asked if you' d like or not to "Optimize" before compiling, you can find out more about MQL5 on-IDE optimization here: https://www.metatrader5.com/en/metaeditor/help/mql5storage/projects#properties  
6. You should now choose which instruction set to use for compiling.  
   MQL5 offers 3 different Intel Advanced Vector Extensions (AVX) instruction sets or a X64 regular one. You can find out more on Intel's official website  
   If wondering about your producer instructions sets compatibility, you can use free tools such as CPU-Z (link: https://www.cpuid.com/softwares/cpu-z.html)  
7. After compiling successfully, you can now use and optimize the EA!  

