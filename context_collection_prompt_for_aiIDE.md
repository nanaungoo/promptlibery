အလုပ်လုပ်နေတဲ့ program တစ်ခုကို AI IDE (ဥပမာ- Cursor, Windsurf, သို့မဟုတ် GitHub Copilot) က သေချာနားလည်ပြီး အမှားအယွင်းမရှိ ဆက်လက်တည်ဆောက်နိုင်ဖို့အတွက် **"Context" (နောက်ခံအကြောင်းအရာ)** ပေးဖို့က အရေးကြီးဆုံးပါ။

AI ကို သင့်ရဲ့ codebase အကြောင်း သင်ကြားပေးဖို့ အထိရောက်ဆုံး နည်းလမ်းတွေကို အောက်မှာ ဖော်ပြပေးလိုက်ပါတယ်။

---

## ၁။ `Instructions` သို့မဟုတ် `.cursorrules` ဖိုင်တစ်ခု ဖန်တီးပါ

အခုခေတ် AI IDE တော်တော်များများမှာ project-specific rules တွေကို မှတ်ထားပေးတဲ့ ဖိုင်တွေ ထည့်လို့ရပါတယ်။ ဒီဖိုင်ထဲမှာ အောက်ပါအချက်တွေကို အတိအကျ ရေးပေးထားသင့်ပါတယ်-

* **Project Overview:** ဒီ program က ဘာအတွက်လဲ၊ ဘယ်လို ပြဿနာကို ဖြေရှင်းတာလဲ။
* **Tech Stack:** အသုံးပြုထားတဲ့ Language (ဥပမာ- Rust, Python), Frameworks နဲ့ Version တွေ။
* **Coding Standards:** သင်နှစ်သက်တဲ့ naming convention (ဥပမာ- camelCase သို့မဟုတ် snake_case) နဲ့ memory management ပုံစံများ။
* **Key Libraries:** အရေးကြီးတဲ့ external libraries တွေနဲ့ ၎င်းတို့ကို ဘယ်နေရာမှာ သုံးထားလဲဆိုတာ။

## ၂။ Architecture Overview ကို ရှင်းပြပါ

AI ကို program ရဲ့ တည်ဆောက်ပုံ (Structure) ကို အရင် "Index" လုပ်ခိုင်းပါ။ ပြီးရင် အောက်ပါအတိုင်း ညွှန်ကြားချက်ပေးနိုင်ပါတယ်-

> "ဒီ codebase ရဲ့ folder structure ကို လေ့လာပါ။ `src/` ထဲမှာ core logic ရှိပြီး `api/` ထဲမှာ interface တွေရှိတယ်။ Data flow က A ကနေ B ကိုသွားပြီး C မှာ save လုပ်တယ်ဆိုတာကို မှတ်ထားပေးပါ။"

## ၃။ "Source of Truth" ဖိုင်များကို သတ်မှတ်ပေးပါ

Program ထဲမှာ အရေးအကြီးဆုံး logic တွေ ရှိတဲ့ ဖိုင်တွေကို AI ကို အထူးဂရုစိုက်ခိုင်းပါ။

* **Entry Points:** Program ဘယ်က စပွင့်သလဲ (ဥပမာ- `main.rs`, `app.py`)။
* **Data Models:** Database schema သို့မဟုတ် type definitions တွေ ရှိတဲ့ ဖိုင်တွေ။
* **Core Modules:** အဓိက အလုပ်လုပ်တဲ့ function တွေ ရှိတဲ့ နေရာ။

## ၄။ Documentation ကို Code ထဲမှာတင် ထည့်ထားပါ

AI က code comment တွေကို ဖတ်ရတာ အရမ်းကြိုက်ပါတယ်။

* Function တစ်ခုချင်းစီရဲ့ အပေါ်မှာ `///` (Rust) သို့မဟုတ် Docstrings (Python) သုံးပြီး **Input, Output နဲ့ Purpose** ကို ရေးထားပါ။
* Complex ဖြစ်တဲ့ logic တွေမှာ "ဘာကြောင့် ဒီလိုရေးရသလဲ" (The 'Why') ကို comment ရေးထားရင် AI က နောက်ပိုင်း code ပြင်တဲ့အခါ logic မမှားအောင် ထိန်းပေးနိုင်ပါတယ်။

---

### AI ကို ညွှန်ကြားတဲ့အခါ သုံးရမည့် Prompt ပုံစံ (Template)

အကယ်၍ သင်က code အသစ်ထပ်တိုးခိုင်းတော့မယ်ဆိုရင် အခုလိုမျိုး အစပြုပြီး ပြောပါ-

> "ငါ့ရဲ့ codebase ကို အခြေခံပြီး [Feature အသစ်] ကို ထည့်ပေးပါ။ ဒါပေမဲ့ code မရေးခင် လက်ရှိ ရှိနေတဲ့ `Auth Module` နဲ့ `Database Schema` ကို အရင်ဖတ်ပါ။ ငါတို့ သုံးနေကျ `Error Handling` pattern အတိုင်းပဲ ရေးပေးပါ။ လက်ရှိ အလုပ်လုပ်နေတဲ့ functional logic တွေကို မထိခိုက်ပါစေနဲ့။"

## ၅။ README.md ကို အမြဲ Update လုပ်ပါ

လူတင်မကဘဲ AI အတွက်ပါ ရည်ရွယ်ပြီး `README.md` မှာ project setup, configuration နဲ့ architecture အကျဉ်းချုပ်ကို ရေးထားပါ။ AI IDE တွေက project ကို စဖွင့်တာနဲ့ ဒီဖိုင်ကို အရင်ဖတ်ပြီး context ယူလေ့ရှိပါတယ်။

ဒီလိုမျိုး စနစ်တကျ ပြင်ဆင်ထားရင် AI က သင့်ရဲ့ program ကို သူ့ကိုယ်ပိုင် ရေးထားသလိုမျိုး သိရှိသွားပြီး အမှားအယွင်းမရှိ ဆက်လက် တည်ဆောက်ပေးနိုင်မှာပါ။

လက်ရှိ တည်ဆောက်ထားတဲ့ program က ဘယ် language နဲ့ ဘာအတွက် သုံးတာလဲဆိုတာ ပြောပြပေးနိုင်မလား? ဒါဆိုရင် ပိုပြီး တိကျတဲ့ instruction ပုံစံကို ကျွန်တော် အကြံပေးနိုင်ပါတယ်။

အခုလိုမျိုး ကိုယ်တိုင်မလုပ်ချင်ဘဲ AI Agent (Claude, Cursor Agent, သို့မဟုတ် Windsurf) ကိုပဲ "အစအဆုံး လေ့လာပြီး မှတ်တမ်းတင်ခိုင်းဖို့" အတွက် အဆင့်ဆင့် ခိုင်းစေနိုင်တဲ့ Prompt တွေကို အောက်မှာ ဖော်ပြပေးလိုက်ပါတယ်။

ဒါကို **"Codebase Reverse Engineering"** လို့ ခေါ်ပါတယ်။ AI ကို သင့်ရဲ့ code တွေကို ပြန်ဖတ်ခိုင်းပြီး logic တွေကို ပြန်ထုတ်ခိုင်းတာပါ။

---

## ၁။ တစ်အုပ်စုလုံးကို ခြုံငုံလေ့လာခိုင်းခြင်း (Initial Audit)

အရင်ဆုံး AI ကို code တွေအကုန်လုံးကို ဖတ်ပြီး သူဘာတွေ နားလည်သလဲဆိုတာကို အစစ်ဆေးခံရပါမယ်။

> **Prompt:**
> "ငါ့ရဲ့ လက်ရှိ codebase တစ်ခုလုံးကို scan ဖတ်ပေးပါ။ ဒီ project က ဘာလုပ်တာလဲ၊ folder structure က ဘယ်လိုရှိသလဲ၊ ဘယ် language နဲ့ library တွေကို အဓိက သုံးထားသလဲဆိုတာကို နားလည်အောင် အရင်လေ့လာပါ။ ပြီးရင် မင်းနားလည်သလောက်ကို summary တစ်ခု ပြန်ပေးပါ။"

## ၂။ `.cursorrules` သို့မဟုတ် Project Rules ထုတ်ခိုင်းခြင်း

သူက project အကြောင်း နားလည်သွားပြီဆိုရင် ဒါကို ဖိုင်အဖြစ် ပြောင်းခိုင်းပါမယ်။

> **Prompt:**
> "အခု မင်းလေ့လာထားတဲ့ codebase ရဲ့ coding style, naming conventions နဲ့ architecture ပုံစံတွေကို အခြေခံပြီး `.cursorrules` (သို့မဟုတ် `instructions.md`) ဖိုင်တစ်ခု ထုတ်ပေးပါ။ အဲဒီဖိုင်ထဲမှာ နောက်နောင် ငါတို့ code အသစ်တွေ ထပ်တိုးတဲ့အခါ မင်းလိုက်နာရမယ့် စည်းကမ်းတွေကို အတိအကျ ထည့်ရေးပေးပါ။ အထူးသဖြင့် error handling pattern နဲ့ memory management ပုံစံတွေကို သေချာ ထည့်ပေးပါ။"

## ၃။ Architecture နဲ့ Data Flow ကို ရှင်းပြခိုင်းခြင်း

ဒါက နောက်ပိုင်းမှာ logic တွေ မမှားစေဖို့အတွက် အရေးကြီးပါတယ်။

> **Prompt:**
> "ဒီ program ရဲ့ **Data Flow** ကို ရှင်းပြပေးပါ။ User ဆီက input က ဘယ်ကနေဝင်လဲ၊ ဘယ် module တွေက ဖြတ်သန်းသွားလဲ၊ နောက်ဆုံး result က ဘယ်မှာ သိမ်းသလဲဆိုတာကို အဆင့်ဆင့် ရေးပေးပါ။ ဒါ့အပြင် project ရဲ့ 'Source of Truth' ဖြစ်တဲ့ အရေးကြီးဆုံး core logic ဖိုင် ၅ ဖိုင်ကိုလည်း စာရင်းပြုစုပေးပါ။"

## ၄။ Code ထဲမှာ Documentation လိုက်ထည့်ခိုင်းခြင်း

Code တွေကို တစ်ဖိုင်ချင်းစီ အလိုက် docstrings တွေ လိုက်ထည့်ခိုင်းတာပါ။

> **Prompt:**
> "ငါ့ရဲ့ code တွေမှာ documentation အားနည်းနေတယ်။ အရေးကြီးတဲ့ function တွေ၊ class တွေနဲ့ modules တွေအားလုံးကို language-specific docstrings (ဥပမာ- Rust အတွက် `///`, Python အတွက် `"""`) တွေ လိုက်ထည့်ပေးပါ။ အဲဒီ comment ထဲမှာ function ရဲ့ input/output တွေတင်မကဘဲ အဲဒီ logic ကို ဘာကြောင့် ဒီလို ရေးထားရသလဲဆိုတဲ့ 'Rationale' ကိုပါ ထည့်ရေးပေးပါ။ လက်ရှိ အလုပ်လုပ်နေတဲ့ code logic တွေကိုတော့ လုံးဝ မပြင်ပါနဲ့။"

## ၅။ README.md ကို အလိုအလျောက် ရေးခိုင်းခြင်း

နောက်ဆုံးအဆင့်အနေနဲ့ လူရော AI ပါ ဖတ်လို့ရမယ့် summary ဖန်တီးခိုင်းတာပါ။

> **Prompt:**
> "အခု မင်းသိထားတဲ့ အချက်အလက်တွေ အားလုံးကို စုပေါင်းပြီး Professional ကျတဲ့ `README.md` ဖိုင်တစ်ခု ရေးပေးပါ။ အဲဒီထဲမှာ Project Overview, Setup Instructions, Architecture Diagram (Mermaid code နဲ့) နဲ့ ဘယ်လို extend လုပ်ရမလဲဆိုတဲ့ အချက်အလက်တွေ ပါဝင်ပါစေ။"

---

### အကြံပြုချက် (Tip):

AI Agent ကို ခိုင်းတဲ့အခါ **"Don't change the logic, only add documentation"** (အလုပ်လုပ်ပုံကို မပြင်ပါနဲ့၊ မှတ်တမ်းပဲ ထည့်ပါ) ဆိုတဲ့ စကားလုံးကို ထည့်သုံးဖို့ မမေ့ပါနဲ့။ ဒါမှ လက်ရှိ အလုပ်လုပ်နေတဲ့ program ကို မတော်တဆ သွားပြင်မိတာမျိုး မဖြစ်မှာပါ။

ဒီ Prompt တွေကို သုံးပြီးတဲ့နောက်မှာ သင့်ရဲ့ AI IDE က သင့် project အကြောင်းကို သင့်ထက်တောင် ပိုသိသွားပါလိမ့်မယ်။ အခြား ဘာများ ကူညီပေးရဦးမလဲ?

Here are the English prompts you can use to command an AI Agent (like Claude, Cursor Agent, or Windsurf) to "reverse engineer" and document your project. These instructions ensure the AI understands exactly how your program works before it attempts to write any new code.

---

## 1. The Initial Codebase Audit

Use this prompt first to make the AI "read" and understand your existing work.

> **Prompt:**
> "Please perform a comprehensive scan of my current codebase. I want you to analyze the project's purpose, the folder structure, the programming languages used, and the primary libraries involved. Once you have a clear understanding, provide a high-level summary of what the project does and how it is organized."

## 2. Generating Project Rules (`.cursorrules`)

This creates a "brain" for the AI IDE so it follows your specific coding style in the future.

> **Prompt:**
> "Based on your analysis of my coding style, naming conventions, and architecture, please generate a `.cursorrules` file (or a `project-instructions.md`). Include specific rules for:
> * **Coding Standards:** (e.g., naming conventions, functional vs. OOP approach).
> * **Memory Management:** Specific patterns used in this project.
> * **Error Handling:** How errors are currently caught and logged.
> These rules should act as your 'guardrails' for any future code generation."
> 
> 

## 3. Architecture & Data Flow Mapping

This helps the AI understand the logic path so it doesn't break things later.

> **Prompt:**
> "Explain the **Data Flow** of this program to me. Map out how a user input enters the system, which modules it passes through, and where the final state is stored. Additionally, identify the top 5 'Source of Truth' files that contain the most critical core logic of the application."

## 4. Automated In-Code Documentation

Use this to make the AI add comments to your code for better long-term maintenance.

> **Prompt:**
> "I want to improve the documentation within the code itself. Please go through the files and add language-specific docstrings (e.g., `///` for Rust or `"""` for Python) to all major functions and classes.
> **Important:** Do not just describe *what* the code does; explain the **'Why'** (the rationale) behind complex logic. **Strictly avoid changing any functional logic.** Just add the documentation."

## 5. Generating a Professional README

This creates a final overview for both you and any other AI/Human who looks at the project.

> **Prompt:**
> "Generate a comprehensive `README.md` for this project. It should include:
> * **Project Overview:** A clear explanation of the program's utility.
> * **Setup Instructions:** How to configure and run the environment.
> * **Architecture Diagram:** Use **Mermaid.js** syntax to visualize the system components.
> * **Contribution Guide:** Brief instructions on how to extend the codebase while keeping the current architecture intact."
> 
> 

---

### Pro-Tips for AI Collaboration:

* **The "Logic Guard":** Whenever you ask an AI to document or refactor, always include the phrase: *"Do not modify the functional logic; only improve clarity and documentation."*
* **Context Pinning:** If you are using an IDE like Cursor, you can use `@Codebase` in your chat to force the AI to look at every file before answering.
* **Incremental Feedback:** If the AI's summary in Step 1 is slightly off, correct it immediately before moving to Step 2. This ensures the "Rules" it generates are 100% accurate.

Since you've already built the program and it's working perfectly, these steps will essentially "onboard" the AI as your junior developer who finally understands the boss's vision!

What kind of project are you currently mapping out? I can help refine the prompts if it's specifically a systems-level tool or a mobile app.
