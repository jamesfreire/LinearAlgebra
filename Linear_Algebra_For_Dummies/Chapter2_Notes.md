\documentclass[12pt]{article}
\usepackage[margin=1in]{geometry}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{mathtools}
\usepackage{xcolor}
\usepackage{fancyhdr}
\usepackage{enumerate}

\pagestyle{fancy}
\fancyhf{}
\rhead{Linear Algebra Study Sheet}
\lhead{Chapter 2: Vectors}
\cfoot{\thepage}

\definecolor{conceptcolor}{RGB}{0,102,204}
\definecolor{formulacolor}{RGB}{153,0,102}
\definecolor{examplecolor}{RGB}{0,153,51}

\newcommand{\concept}[1]{\textcolor{conceptcolor}{\textbf{#1}}}
\newcommand{\formula}[1]{\textcolor{formulacolor}{\boxed{#1}}}
\newcommand{\example}[1]{\textcolor{examplecolor}{\textit{#1}}}

\title{\textbf{Linear Algebra Study Sheet} \\ Chapter 2: The Value of Involving Vectors}
\author{}
\date{}

\begin{document}

\maketitle

\section*{Chapter Overview}
Vectors are ordered collections of numbers that can be represented as rays in coordinate systems. They have both magnitude (length) and direction, making them useful for representing quantities like velocity, force, and displacement in physics and engineering.

\section{\concept{Vector Representation}}

\subsection{Standard Position}
A vector in standard position has its endpoint at the origin $(0,0)$ and terminal point at coordinates $(x,y)$.

\formula{\mathbf{v} = \begin{bmatrix} x \\ y \end{bmatrix}}

\example{Real-world example: A displacement vector from your house (origin) to the grocery store 3 blocks east and 2 blocks north would be $\begin{bmatrix} 3 \\ 2 \end{bmatrix}$.}

\section{\concept{Vector Addition and Subtraction}}

\subsection{Vector Addition}
To add vectors, add corresponding components:
\formula{\mathbf{u} + \mathbf{v} = \begin{bmatrix} u_1 \\ u_2 \end{bmatrix} + \begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix} u_1 + v_1 \\ u_2 + v_2 \end{bmatrix}}

\example{Navigation example: If you walk 3 km east and 2 km north, then walk 1 km west and 4 km north, your total displacement is $\begin{bmatrix} 3 \\ 2 \end{bmatrix} + \begin{bmatrix} -1 \\ 4 \end{bmatrix} = \begin{bmatrix} 2 \\ 6 \end{bmatrix}$ (2 km east, 6 km north).}

\subsection{Vector Subtraction}
\formula{\mathbf{u} - \mathbf{v} = \mathbf{u} + (-\mathbf{v}) = \begin{bmatrix} u_1 - v_1 \\ u_2 - v_2 \end{bmatrix}}

\example{Finding relative position: If your friend is at position $\begin{bmatrix} 5 \\ 3 \end{bmatrix}$ and you're at $\begin{bmatrix} 2 \\ 1 \end{bmatrix}$, the vector from you to your friend is $\begin{bmatrix} 5 \\ 3 \end{bmatrix} - \begin{bmatrix} 2 \\ 1 \end{bmatrix} = \begin{bmatrix} 3 \\ 2 \end{bmatrix}$.}

\section{\concept{Scalar Multiplication}}

\subsection{Definition}
Multiply each component by the scalar:
\formula{c\mathbf{v} = c\begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix} cv_1 \\ cv_2 \end{bmatrix}}

\subsection{Effects}
\begin{itemize}
\item If $c > 1$: \textbf{Dilation} (stretches the vector)
\item If $0 < c < 1$: \textbf{Contraction} (shrinks the vector)
\item If $c < 0$: \textbf{Reverses direction}
\item If $c = 0$: Results in zero vector
\end{itemize}

\example{Speed scaling: If a car's velocity vector is $\begin{bmatrix} 60 \\ 0 \end{bmatrix}$ km/h eastward, doubling the speed gives $2\begin{bmatrix} 60 \\ 0 \end{bmatrix} = \begin{bmatrix} 120 \\ 0 \end{bmatrix}$ km/h.}

\section{\concept{Vector Magnitude (Length)}}

\subsection{Formula}
\formula{\|\mathbf{v}\| = \sqrt{v_1^2 + v_2^2}}

For 3D vectors: $\|\mathbf{v}\| = \sqrt{v_1^2 + v_2^2 + v_3^2}$

\example{Distance calculation: If you travel from $(0,0)$ to $(3,4)$, the distance is $\sqrt{3^2 + 4^2} = \sqrt{9 + 16} = 5$ units.}

\subsection{Magnitude Under Scalar Multiplication}
\formula{\|c\mathbf{v}\| = |c| \cdot \|\mathbf{v}\|}

\example{If a force vector has magnitude 10 N and you triple it, the new magnitude is $|3| \times 10 = 30$ N.}

\section{\concept{Triangle Inequality}}

\subsection{Statement}
The magnitude of the sum is less than or equal to the sum of magnitudes:
\formula{\|\mathbf{u} + \mathbf{v}\| \leq \|\mathbf{u}\| + \|\mathbf{v}\|}

\example{Travel time: The direct distance between two cities is always less than or equal to the distance traveled via any intermediate city.}

\subsection{Geometric and Arithmetic Means}
For positive numbers $a$ and $b$:
\begin{align}
\text{Geometric Mean: } &\sqrt{ab} \\
\text{Arithmetic Mean: } &\frac{a + b}{2}
\end{align}

\formula{\sqrt{ab} \leq \frac{a + b}{2}}

\example{If two investment returns are 4\% and 9\%, the geometric mean return is $\sqrt{4 \times 9} = 6\%$, while the arithmetic mean is $\frac{4 + 9}{2} = 6.5\%$.}

\section{\concept{Dot Product (Inner Product)}}

\subsection{Definition}
\formula{\mathbf{u} \cdot \mathbf{v} = u_1v_1 + u_2v_2}

Also written as $\mathbf{u}^T\mathbf{v}$ (transpose notation).

\example{Work calculation: If force $\mathbf{F} = \begin{bmatrix} 10 \\ 5 \end{bmatrix}$ N is applied over displacement $\mathbf{d} = \begin{bmatrix} 3 \\ 2 \end{bmatrix}$ m, the work done is $\mathbf{F} \cdot \mathbf{d} = 10(3) + 5(2) = 40$ J.}

\section{\concept{Orthogonality and Angles}}

\subsection{Orthogonal Vectors}
Two vectors are orthogonal (perpendicular) if:
\formula{\mathbf{u} \cdot \mathbf{v} = 0}

\example{Perpendicular forces: Vectors $\begin{bmatrix} 3 \\ 4 \end{bmatrix}$ and $\begin{bmatrix} 4 \\ -3 \end{bmatrix}$ are orthogonal since $3(4) + 4(-3) = 12 - 12 = 0$.}

\subsection{Angle Between Vectors}
\formula{\cos \theta = \frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{u}\| \|\mathbf{v}\|}}

Therefore: $\theta = \arccos\left(\frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{u}\| \|\mathbf{v}\|}\right)$

\example{Finding viewing angle: If two observation points are at $\begin{bmatrix} 2 \\ 6 \end{bmatrix}$ and $\begin{bmatrix} -1 \\ 5 \end{bmatrix}$ relative to a landmark, the angle between the sight lines can be calculated using this formula.}

\section*{\concept{Key Properties to Remember}}

\begin{enumerate}
\item Vector addition is commutative: $\mathbf{u} + \mathbf{v} = \mathbf{v} + \mathbf{u}$
\item Vector addition is associative: $(\mathbf{u} + \mathbf{v}) + \mathbf{w} = \mathbf{u} + (\mathbf{v} + \mathbf{w})$
\item Zero vector is additive identity: $\mathbf{v} + \mathbf{0} = \mathbf{v}$
\item Scalar multiplication distributes: $c(\mathbf{u} + \mathbf{v}) = c\mathbf{u} + c\mathbf{v}$
\item Dot product is commutative: $\mathbf{u} \cdot \mathbf{v} = \mathbf{v} \cdot \mathbf{u}$
\end{enumerate}

\section*{\concept{Common Applications}}
\begin{itemize}
\item \textbf{Physics}: Force, velocity, acceleration vectors
\item \textbf{Computer Graphics}: 2D/3D transformations, lighting calculations
\item \textbf{Engineering}: Stress analysis, electromagnetic fields
\item \textbf{Economics}: Multi-dimensional optimization problems
\item \textbf{Navigation}: GPS coordinates, flight paths
\end{itemize}

\end{document}
