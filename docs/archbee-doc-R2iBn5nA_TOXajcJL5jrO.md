---
title: Tex
slug: R2iB-tex
docTags: 
createdAt: Tue Dec 16 2025 14:04:16 GMT+0000 (Coordinated Universal Time)
updatedAt: Mon Dec 22 2025 10:09:23 GMT+0000 (Coordinated Universal Time)
---

```tex
m_{\text{yeast}}=\left(\frac{m_{\text{sample,dry}}}{V_{\text{sample}}}\right)\,V_{\text{final}}

```

```tex
Y_{\text{fermenter}}=\frac{m_{\text{yeast}}}{m_{\text{molasses}}}

```

```tex
\eta=\begin{cases}
1, & \text{if } T \ge 30^\circ\text{C}\\
0, & \text{if } T < 30^\circ\text{C}
\end{cases}

```

```tex
c=\frac{m}{V}\ \text{[g/L]}

```

```tex
\begin{aligned}
m_{\text{yeast}} &= \left(\frac{m_{\text{sample,dry}}}{V_{\text{sample}}}\right) V_{\text{final}}\\[4pt]
Y_{\text{fermenter}} &= \frac{m_{\text{yeast}}}{m_{\text{molasses}}}\\[6pt]
\eta(T) &= \begin{cases}
1, & \text{if } 30^\circ\text{C} \le T \le 35^\circ\text{C}\\
0.8, & \text{if } 25^\circ\text{C} \le T < 30^\circ\text{C}\\
0, & \text{if } T < 25^\circ\text{C}
\end{cases}\\[6pt]
c_{\text{yeast}} &= \frac{m_{\text{sample,dry}}}{V_{\text{sample}}}\ \text{[g/L]}
\end{aligned}

```

```tex
\begin{aligned}
\mathbf{x} &= \begin{bmatrix} m_{\text{sample,dry}} \\ V_{\text{sample}} \\ V_{\text{final}} \\ m_{\text{molasses}} \end{bmatrix},
\qquad
\mathbf{f}(\mathbf{x}) =
\begin{bmatrix}
\left(\frac{x_1}{x_2}\right)x_3\\[6pt]
\frac{\left(\frac{x_1}{x_2}\right)x_3}{x_4}
\end{bmatrix}\\[8pt]
m_{\text{yeast}} &= f_1(\mathbf{x}), \qquad
Y_{\text{fermenter}} = f_2(\mathbf{x})
\end{aligned}

```

```tex
\begin{aligned}
m_{\text{yeast}} &= \left(\frac{m_{\text{sample,dry}}}{V_{\text{sample}}}\right)V_{\text{final}}\\[4pt]
\ln(m_{\text{yeast}}) &= \ln(m_{\text{sample,dry}}) - \ln(V_{\text{sample}}) + \ln(V_{\text{final}})\\[6pt]
\left(\frac{\sigma_{m_{\text{yeast}}}}{m_{\text{yeast}}}\right)^2
&=
\left(\frac{\sigma_{m_{\text{sample,dry}}}}{m_{\text{sample,dry}}}\right)^2
+
\left(\frac{\sigma_{V_{\text{sample}}}}{V_{\text{sample}}}\right)^2
+
\left(\frac{\sigma_{V_{\text{final}}}}{V_{\text{final}}}\right)^2\\[6pt]
Y_{\text{fermenter}} &= \frac{m_{\text{yeast}}}{m_{\text{molasses}}}
\end{aligned}

```

```tex
\begin{aligned}
&\textbf{Given:}\quad
m_{\text{sample,dry}},\ V_{\text{sample}},\ V_{\text{final}},\ m_{\text{molasses}},\ T,\ t,\ t_f\\[4pt]
&\textbf{Concentration:}\quad
c_{\text{yeast}}=\frac{m_{\text{sample,dry}}}{V_{\text{sample}}}\ \text{[g/L]}\\[6pt]
&\textbf{Total yeast:}\quad
m_{\text{yeast}}=c_{\text{yeast}}\,V_{\text{final}}\\[6pt]
&\textbf{Fermenter yield:}\quad
Y_{\text{fermenter}}=\frac{m_{\text{yeast}}}{m_{\text{molasses}}}\\[10pt]
&\textbf{Temperature factor:}\quad
\eta(T)=
\begin{cases}
0, & T<25^\circ\text{C}\\
0.8+0.04\,(T-25^\circ\text{C}), & 25^\circ\text{C}\le T<30^\circ\text{C}\\
1, & 30^\circ\text{C}\le T\le 35^\circ\text{C}\\
\exp\!\left(-0.2\,(T-35^\circ\text{C})\right), & T>35^\circ\text{C}
\end{cases}\\[12pt]
&\textbf{A simple growth profile:}\quad
m_{\text{yeast}}(t)=
\frac{m_{\max}}{1+\exp\!\left(-k\,\eta(T)\,(t-t_0)\right)}\\[6pt]
&\textbf{Net production (from 0 to }t_f\textbf{):}\quad
\Delta m_{\text{yeast}}=m_{\text{yeast}}(t_f)-m_{\text{yeast}}(0)\\[10pt]
&\textbf{Mass balance check:}\quad
\epsilon=\frac{\Delta m_{\text{yeast}}}{m_{\text{molasses}}}-Y_{\text{target}}\\[6pt]
&\textbf{Decision:}\quad
\text{pass if }|\epsilon|\le 0.02,\ \text{fail otherwise}\\[12pt]
&\textbf{Uncertainty propagation (relative):}\quad
\left(\frac{\sigma_{m_{\text{yeast}}}}{m_{\text{yeast}}}\right)^2=
\left(\frac{\sigma_{m_{\text{sample,dry}}}}{m_{\text{sample,dry}}}\right)^2+
\left(\frac{\sigma_{V_{\text{sample}}}}{V_{\text{sample}}}\right)^2+
\left(\frac{\sigma_{V_{\text{final}}}}{V_{\text{final}}}\right)^2\\[8pt]
&\textbf{And for yield:}\quad
\left(\frac{\sigma_{Y_{\text{fermenter}}}}{Y_{\text{fermenter}}}\right)^2=
\left(\frac{\sigma_{m_{\text{yeast}}}}{m_{\text{yeast}}}\right)^2+
\left(\frac{\sigma_{m_{\text{molasses}}}}{m_{\text{molasses}}}\right)^2
\end{aligned}

```

```tex
\begin{aligned}
\textbf{Inputs:}\quad
& m_{\text{sample,dry}}=1.25\ \text{g},\ 
V_{\text{sample}}=25\ \text{mL},\ 
V_{\text{final}}=18{,}000\ \text{L},\ 
m_{\text{molasses}}=9{,}500\ \text{kg}\\[6pt]
\textbf{Unit conversions:}\quad
& V_{\text{sample}}=25\times 10^{-3}\ \text{L},\qquad
m_{\text{molasses}}=9.5\times 10^{6}\ \text{g}\\[8pt]
\textbf{Step 1 (conc.):}\quad
& c_{\text{yeast}}=\frac{1.25}{25\times 10^{-3}}=50\ \text{g/L}\\[6pt]
\textbf{Step 2 (total):}\quad
& m_{\text{yeast}}=50\times 18{,}000=9.0\times 10^{5}\ \text{g}\\[6pt]
\textbf{Step 3 (yield):}\quad
& Y_{\text{fermenter}}=\frac{9.0\times 10^{5}}{9.5\times 10^{6}}=0.0947\\[10pt]
\textbf{Constraint checks:}\quad
& 0<Y_{\text{fermenter}}<0.2,\qquad
V_{\text{final}}>0,\qquad
V_{\text{sample}}>0\\[10pt]
\textbf{Vector form:}\quad
& \mathbf{x}=
\begin{bmatrix}
m_{\text{sample,dry}}\\
V_{\text{sample}}\\
V_{\text{final}}\\
m_{\text{molasses}}
\end{bmatrix},
\qquad
\mathbf{g}(\mathbf{x})=
\begin{bmatrix}
\left(\frac{x_1}{x_2}\right)x_3\\[6pt]
\frac{\left(\frac{x_1}{x_2}\right)x_3}{x_4}
\end{bmatrix}\\[10pt]
\textbf{Outputs:}\quad
& \begin{bmatrix} m_{\text{yeast}}\\ Y_{\text{fermenter}} \end{bmatrix}
=\mathbf{g}(\mathbf{x})
\end{aligned}

```

