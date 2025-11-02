# LaTeX টিউটোরিয়াল (বাংলা)

এই টিউটোরিয়ালটি নতুনদের জন্য LaTeX শেখার একটি সম্পূর্ণ গাইড। এখানে প্রদত্ত উদাহরণগুলো অনুসরণ করে আপনি সহজেই LaTeX ডকুমেন্ট তৈরি করা, ছবি যোগ করা, টেবিল বানানো, গাণিতিক সমীকরণ এবং অ্যালগরিদম লেখা শিখতে পারবেন।

## সূচীপত্র

১. [প্রাথমিক ডকুমেন্ট তৈরি](#1-প্রাথমিক-ডকুমেন্ট-তৈরি)
২. [ছবি যোগ করা](#2-ছবি-যোগ-করা)
৩. [টেবিল এবং টেক্সট ফরম্যাটিং](#3-টেবিল-এবং-টেক্সট-ফরম্যাটিং)
৪. [গাণিতিক সমীকরণ লেখা](#4-গাণিতিক-সমীকরণ-লেখা)
৫. [অ্যালগরিদম লেখা](#5-অ্যালগরিদম-লেখা)

---

### 1. প্রাথমিক ডকুমেন্ট তৈরি

একটি LaTeX ডকুমেন্ট তৈরি করার জন্য কিছু মৌলিক কাঠামো অনুসরণ করতে হয়। নিচে একটি সাধারণ রিসার্চ পেপারের আউটলাইন দেওয়া হলো।

**কোড উদাহরণ (`01_doc.tex`):**

```latex
\documentclass[12pt, a4paper]{article}
\title{Research Paper Outline}
\begin{document}
\maketitle

\section*{Abstract}
This is abstract section...

\section*{Introduction}
\begin{itemize}
\item Background
\item Thesis Statement
\end{itemize}

\section*{Body}
\begin{itemize}
\item Methods
\item Results
\item Discussion
\item Conclusion
\end{itemize}

\section*{Acknowledgments}
\section*{Declaration of Competing Interests}
\section*{References}

\end{document}
```

**ব্যাখ্যা:**

-   `\documentclass[12pt, a4paper]{article}`: এটি দিয়ে ডকুমেন্টের ধরন (article), ফন্ট সাইজ (12pt) এবং কাগজের আকার (a4paper) নির্ধারণ করা হয়।
-   `\title{}`: ডকুমেন্টের শিরোনাম লেখার জন্য ব্যবহৃত হয়।
-   `\begin{document}` এবং `\end{document}`: এর মধ্যে ডকুমেন্টের মূল বিষয়বস্তু লেখা হয়।
-   `\maketitle`: শিরোনামটি প্রদর্শনের জন্য এই কমান্ড ব্যবহার করা হয়।
-   `\section*{}`: এটি একটি সেকশন বা বিভাগ তৈরি করে। `*` চিহ্ন থাকায় সেকশনের কোনো নম্বর হয় না।
-   `\begin{itemize}` এবং `\end{itemize}`: বুলেট পয়েন্টসহ তালিকা তৈরির জন্য ব্যবহৃত হয়। প্রতিটি আইটেমের জন্য `\item` কমান্ড ব্যবহার করা হয়।

---

### 2. ছবি যোগ করা

ডকুমেন্টে ছবি যোগ করার জন্য `graphicx` প্যাকেজটি অত্যন্ত প্রয়োজনীয়। ছবি ডানে, বামে বা মাঝে রাখার জন্য `figure` এনভায়রনমেন্ট ব্যবহার করা হয়।

**কোড উদাহরণ (`02_image.tex`):**

```latex
\documentclass[12pt, a4paper]{article}
\usepackage{graphicx}
\usepackage{float}
\usepackage{tikz}
\graphicspath{{./images/}}
\begin{document}

My image \ref{img} is here...

\begin{figure}[H]
\centering
\includegraphics[width=0.5\textwidth]{img.jpg}
\caption{SRHridoy}
\label{img}
\end{figure}

\begin{figure}[H]
  \centering
  \begin{tikzpicture}
    \clip (0,0) circle (2cm);
    \node at (0,0) {\includegraphics[width=4cm]{img.jpg}};
    \draw (0,0) circle (2cm);
  \end{tikzpicture}
  \caption{Circle image}
\end{figure}

\end{document}
```

**ব্যাখ্যা:**

-   `\usepackage{graphicx}`: ছবি যোগ করার জন্য এই প্যাকেজটি অপরিহার্য।
-   `\usepackage{float}`: `[H]` অপশন ব্যবহার করে ছবিকে নির্দিষ্ট স্থানে রাখতে সাহায্য করে।
-   `\graphicspath{{./images/}}`: ছবিগুলো কোন ফোল্ডারে আছে তা নির্ধারণ করে।
-   `\begin{figure}[H]`: ছবি যোগ করার জন্য একটি এনভায়রনমেন্ট। `[H]` মানে ছবিটি ঠিক এখানেই (here) দেখানো হবে।
-   `\centering`: ছবিটি পৃষ্ঠার মাঝে দেখানোর জন্য।
-   `\includegraphics[width=0.5\textwidth]{img.jpg}`: `img.jpg` নামের ছবিটি যোগ করে, যার প্রস্থ পৃষ্ঠার অর্ধেক।
-   `\caption{}`: ছবির নিচে ক্যাপশন বা বর্ণনা যোগ করে।
-   `\label{}` এবং `\ref{}`: ডকুমেন্টের যেকোনো স্থান থেকে ছবিকে রেফারেন্স করার জন্য ব্যবহৃত হয়।
-   `tikz` প্যাকেজ ব্যবহার করে गोलाকার ছবির মতো কাস্টম গ্রাফিক্স তৈরি করা যায়।

---

### 3. টেবিল এবং টেক্সট ফরম্যাটিং

LaTeX-এ টেবিল তৈরি করার জন্য `tabular` এনভায়রনমেন্ট ব্যবহার করা হয়। এছাড়া টেক্সটকে বিভিন্নভাবে ফরম্যাট করা যায়, যেমন ইটালিক, আন্ডারলাইন ইত্যাদি।

**কোড উদাহরণ (`03_table.tex`):**

```latex
\documentclass[12pt, a4paper]{article}
\usepackage{float}
\usepackage{array}
\usepackage{ulem}
\normalem

\begin{document}

\section{Datasets of Colonoscopy}
The table \ref{datasetsTable} illustrates the state-of-the-art datasets of Colonoscopy.

\begin{table}[H]
\centering
\begin{tabular}{|p{0.15\textwidth}|p{0.15\textwidth}|p{0.15\textwidth}|}
\hline
{\bf Dataset} & {\bf Metric}& {\bf ImageNet Supervised model} \\
\hline
{\bf GRAIDS }& AUC & 99\% \\
\hline
\end{tabular}
\caption{Datasets of Colonoscopy}
\label{datasetsTable}
\end{table}

\section {Italic-Underline-StrikeThrough}
This is \textit{italic} text.\\
This is \underline{underlined} text.\\
This \emph{important} text.\\
This is \sout{striked out} text...\\

\end{document}
```

**ব্যাখ্যা:**

-   `\begin{table}[H]` ও `\end{table}`: টেবিল তৈরির এনভায়রনমেন্ট।
-   `\begin{tabular}{|...|}`: টেবিলের কলাম নির্ধারণ করে। `|` দিয়ে বর্ডার এবং `p{width}` দিয়ে কলামের প্রস্থ নির্ধারণ করা হয়।
-   `\hline`: টেবিলের মধ্যে আনুভূমিক রেখা (horizontal line) আঁকার জন্য।
-   `&`: একটি সেল থেকে অন্য সেলে যাওয়ার জন্য।
-   `\\`: নতুন সারি (row) শুরু করার জন্য।
-   `\textit{}`: টেক্সটকে ইটালিক করে।
-   `\underline{}`: টেক্সটকে আন্ডারলাইন করে।
-   `\emph{}`: গুরুত্বপূর্ণ টেক্সটকে হাইলাইট করে (সাধারণত ইটালিক হয়)।
-   `\sout{}`: টেক্সটের মাঝখান দিয়ে দাগ (strikethrough) দেওয়ার জন্য `ulem` প্যাকেজ লাগে।

---

### 4. গাণিতিক সমীকরণ লেখা

LaTeX গাণিতিক সমীকরণ লেখার জন্য খুবই শক্তিশালী। সমীকরণ দুইভাবে লেখা যায়: ইনলাইন (লাইনের মধ্যে) এবং ডিসপ্লে (আলাদা লাইনে)।

**কোড উদাহরণ (`04_equation.tex`):**

```latex
\documentclass[12pt, a4paper] {article}
\begin{document}
The following equation in \ref{square} is:
\begin{equation}
\label{square}
(a+b)^2 = a^2 + 2ab + b^2
\end{equation}

Water = H$_2$O \\
$(a+b)^2$ = $a^2+2ab+b^2$
\end{document}
```

**ব্যাখ্যা:**

-   `\begin{equation}` ও `\end{equation}`: নম্বরসহ সমীকরণ লেখার জন্য এই এনভায়রনমেন্ট ব্যবহৃত হয়।
-   `$...$`: লাইনের মধ্যে ছোট সমীকরণ (inline equation) লেখার জন্য ডলার চিহ্ন ব্যবহার করা হয়। যেমন: `H$_2$O` লিখলে 2 নিচে (subscript) দেখাবে।
-   `^`: পাওয়ার বা সুপারস্ক্রিপ্ট (superscript) লেখার জন্য ব্যবহৃত হয়। যেমন: `a^2`।
-   `_`: সাবস্ক্রিপ্ট (subscript) লেখার জন্য ব্যবহৃত হয়। যেমন: `H_2`।

---

### 5. অ্যালগরিদম লেখা

রিসার্চ পেপার বা টেকনিক্যাল ডকুমেন্টে অ্যালগরিদম লেখার জন্য `algorithm` এবং `algpseudocode` প্যাকেজ দুটি খুব দরকারি।

**কোড উদাহরণ (`05_algorithm.tex`):**

```latex
\documentclass[a4paper,12pt]{article}
\usepackage{algorithm}
\usepackage{algpseudocode}

\begin{document}
\begin{algorithm}
  \caption{Algorithm to find the largest number}
  \begin{algorithmic}[1]
    \Procedure{Largest}{$a, b$}
      \State Input $a$ and $b$
      \If{$a > b$}
        \State $max \gets a$
      \Else
        \State $max \gets b$
      \EndIf
      \State Display $max$
    \EndProcedure
  \end{algorithmic}
\end{algorithm}
\end{document}
```

**ব্যাখ্যা:**

-   `\usepackage{algorithm}`: অ্যালগরিদমের জন্য একটি ফ্লোটিং এনভায়রনমেন্ট তৈরি করে, যা দিয়ে ক্যাপশন ও নম্বর দেওয়া যায়।
-   `\usepackage{algpseudocode}`: সিউডো কোড (pseudo code) লেখার জন্য বিভিন্ন কমান্ড (`\Procedure`, `\State`, `\If`, `\For` ইত্যাদি) সরবরাহ করে।
-   `\begin{algorithm}` ও `\end{algorithm}`: অ্যালগরিদম লেখার মূল এনভায়রনমেন্ট।
-   `\begin{algorithmic}[1]` ও `\end{algorithmic}`: অ্যালগরিদমের কোড লেখার জন্য ব্যবহৃত হয়। `[1]` দিলে প্রতিটি লাইনে নম্বর দেখাবে।
-   `\Procedure{...}{...}`: একটি প্রসিডিউর বা ফাংশন ডিফাইন করে।
-   `\State`: অ্যালগরিদমের একটি ধাপ বা স্টেটমেন্ট।
-   `\If{...} \Else \EndIf`: শর্ত (conditional statement) লেখার জন্য ব্যবহৃত হয়।

আশা করি এই টিউটোরিয়ালটি আপনাকে LaTeX শিখতে এবং ব্যবহার করতে সাহায্য করবে। শুভকামনা!
