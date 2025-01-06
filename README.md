# PRODIGY_TrackCode_1
The Caesar Cipher,  one of the earliest known encryption techniques, exemplifies the foundations  of cryptography with its straightforward substitution approach. 
\documentclass[a4paper,12pt]{report}
\usepackage{listings}
\usepackage{xcolor}
\usepackage{amsmath}
\usepackage{hyperref}
\usepackage{graphicx}
\usepackage{float} % To fix figure placement issues

% Hyperref setup
\hypersetup{
    colorlinks=true,
    linkcolor=blue,
    filecolor=magenta,  
    urlcolor=cyan,
    pdftitle={Project Report},
    pdfpagemode=FullScreen,
}

% Listings setup
\lstset{
    language=Python,
    basicstyle=\ttfamily\footnotesize,
    keywordstyle=\color{blue},
    stringstyle=\color{red},
    commentstyle=\color{green},
    numbers=left,
    numberstyle=\tiny\color{gray},
    stepnumber=1,
    numbersep=5pt,
    showspaces=false,
    showstringspaces=false,
    showtabs=false,
    frame=single,
    tabsize=4,
    captionpos=b,
    breaklines=true,
    breakatwhitespace=false,
    title=\lstname,
    escapeinside={\%*}{*)}
}

\begin{document}

\title{\textbf{Project Report on Caesar Cipher Implementation Using Python}}
\author{Shameel \\ MSc Cyber Security, RGNIYD, Chennai}
\date{\today}
\maketitle

\tableofcontents

\chapter{Introduction}
Cryptography is a cornerstone of cybersecurity, providing mechanisms to secure communication and safeguard sensitive information. The Caesar Cipher, one of the earliest known encryption techniques, exemplifies the foundations of cryptography with its straightforward substitution approach. This project demonstrates the implementation of the Caesar Cipher in Python, featuring a graphical user interface (GUI) designed with Tkinter to enable intuitive encryption and decryption. By bridging theoretical principles with practical application, the project underscores the educational value of classical cryptography while showcasing Python's versatility in developing interactive tools for secure communication.

\chapter{Objective}
The objective of this project is to:
\begin{itemize}
    \item Implement a Caesar Cipher encryption and decryption algorithm.
    \item Create a user-friendly GUI for encryption and decryption.
\end{itemize}

\chapter{Code Implementation}
This section presents the Python code used for the project. The code implements functions for letter-to-number conversion, encryption, decryption, and a Tkinter-based GUI for interaction.

\section{Full Code}
\lstinputlisting[language=Python, caption={Caesar Cipher Implementation in Python}]{enc_dec.py}

\chapter{Explanation of Code}
\section{Algorithm}
\subsection{Letter to Number (ltn) Function}
This function converts a character to its corresponding number based on its position in the alphabet.
\begin{lstlisting}[language=Python]
def ltn(l):
    if(ord(l) <= 90):
        pn = ord(l) - 65
    else:
        pn = ord(l) - 97
    return pn
\end{lstlisting}

\subsection{Number to Letter (ntl) Function}
This function converts a number back to its corresponding letter, considering case sensitivity.
\begin{lstlisting}[language=Python]
def ntl(n, isup):
    if isup:
        l = n % 26 + 65
    else:
        l = n % 26 + 97
    return chr(l)
\end{lstlisting}

\subsection{Encrypt and Decrypt Functions}
\textbf{Encryption:}
Adds the key to the plaintext number to generate the ciphertext number.
\begin{lstlisting}[language=Python]
def enc(pt, key):
    ct = ""
    for i in pt:
        pn = ltn(i)
        cn = pn + key
        isup = i.isupper()
        ct += ntl(cn, isup)
    return ct
\end{lstlisting}

\textbf{Decryption:}
Subtracts the key from the ciphertext number to retrieve the plaintext number.
\begin{lstlisting}[language=Python]
def dec(ct, key):
    pt = ""
    for i in ct:
        cn = ltn(i)
        pn = cn - key
        isup = i.isupper()
        pt += ntl(pn, isup)
    return pt
\end{lstlisting}

\section{Graphical User Interface}
The Tkinter library is used to create an interactive GUI with input fields for plaintext, ciphertext, and key. Buttons allow users to encrypt or decrypt the input text.

\chapter{Results}
\section{Input and Output}
\begin{itemize}
    \item \textbf{Input:} Plaintext = "Hello", Key = 3
    \item \textbf{Output:} Ciphertext = "Khoor"
\end{itemize}

\section{Screenshots of the Program Output}

The following are the screenshots of the output generated by the Caesar Cipher program:

\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{enc.png} % Encryption screenshot
    \caption{GUI Output Showing Encryption in Caesar Cipher Program}
    \label{fig:encryption_screenshot}
\end{figure}

\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{dec.png} % Decryption screenshot
    \caption{GUI Output Showing Decryption in Caesar Cipher Program}
    \label{fig:decryption_screenshot}
\end{figure}

\chapter{Conclusion}
This project highlights the implementation of the Caesar Cipher algorithm and its practical integration with a user-friendly graphical interface, reinforcing the significance of classical cryptographic techniques in understanding modern cybersecurity. While simplistic, the Caesar Cipher serves as a foundational concept for grasping the principles of encryption. By leveraging Python and Tkinter, the project bridges theoretical concepts with hands-on programming, creating an interactive platform that not only educates users about substitution ciphers but also lays the groundwork for exploring advanced cryptographic solutions in today's digital landscape.

\chapter{References}
\begin{enumerate}
    \item Tkinter Documentation: \url{https://docs.python.org/3/library/tkinter.html}
    \item Caesar Cipher: \url{https://en.wikipedia.org/wiki/Caesar_cipher}
    \item Caesar Cipher: \url{https://www.geeksforgeeks.org/caesar-cipher-in-cryptography/}
\end{enumerate}

\end{document}
