# MAST90051 Mathematics of Risk Problem Sheet 6/2024

## Assignment 1

**Posted on LMS on Tuesday 27 August 2024 (announced via LMS on the same day).**

**Submission deadline**: 23:59 AEST on Friday 13 September 2024.

Your solutions must be submitted via Canvas/Gradescope (see below). Late submissions will receive no mark unless you have a valid reason for extension, in which case you should contact the lecturer prior to the submission deadline.

- Print your name, student ID, the subject name & code in the top right corner on the first page of your solutions. Your solutions must be written on blank A4 size paper.
- There is no need to typeset your solutions, but you may wish to do so. Material on different sized paper will not be marked.
- All problems should be attempted. Working and/or reasoning must be given to obtain full credit. Wherever possible, give final answers with all numerical components thereof (e.g., coefficients) as decimal numbers (using “scientific notation” is OK). The form and neatness of work can be considered in marking.
- Do not include tables of data sets in your solutions! Reasonable data summaries would be enough. Please do not exceed 15 pages, OK?

If you typeset your solutions, produce a single PDF file with your submission. If you wrote them, scan your submission to a single PDF file with a mobile phone or a scanner. Scan from directly above to avoid any excessive keystone effect. Ensure your scans are of good quality. Check that all pages are in correct order, are clearly readable and cropped to the A4 borders of the original page. Poorly scanned submissions may be impossible to mark.

Upload the PDF file via the Canvas Assignments menu. In the process, you will have to submit your PDF to the Gradescope tool by first selecting your PDF file and then clicking on Upload PDF. Gradescope will then ask you to identify on which of the uploaded pages your answers to each question are located. You must do that!

### 1. Let \(L\) be a random loss with an absolutely continuous DF \(F\) and density \(f\).

#### (a) Compute the DF tail \(F(x)\), \(x\geq1.5\), for \(L\) and hence find the values of \(VaR_{\alpha}(F)\) and \(ES_{\alpha}(F)\) at the following four confidence levels: \(\alpha = 0.95; 0.99; 0.995; 0.999\) (with four digits after the decimal point each). Calculate the ratios \(ES_{\alpha}(L)/VaR_{\alpha}(L)\) for the above \(\alpha\)-values. Show your work. Present your results in the form of a nice table. Briefly comment on your findings. [5 marks]

The density function is given as \(f(x) = 4x^{-4}\ln x\) for \(x > 1.5\).

1. Compute the cumulative distribution function \(F(x)\):
   - \(F(x)=\int_{1.5}^{x}f(t)dt=\int_{1.5}^{x}4t^{-4}\ln t dt\).
   - This integral can be evaluated numerically.
2. Find \(VaR_{\alpha}(F)\):
   - \(VaR_{\alpha}(F)\) is the value such that \(F(VaR_{\alpha}(F)) = 1-\alpha\).
   - For each \(\alpha\), solve the equation \(F(VaR_{\alpha}(F)) = 1-\alpha\) numerically.
3. Find \(ES_{\alpha}(F)\):
   - \(ES_{\alpha}(F)=\frac{1}{\alpha}\int_{\alpha}^{1}VaR_{u}(F)du\).
   - After finding \(VaR_{\alpha}(F)\) for each \(\alpha\), compute \(ES_{\alpha}(F)\) numerically.
4. Calculate the ratios \(ES_{\alpha}(L)/VaR_{\alpha}(L)\).

Present the results in a table:
| Confidence Level (\(\alpha\)) | \(VaR_{\alpha}(F)\) | \(ES_{\alpha}(F)\) | \(ES_{\alpha}(L)/VaR_{\alpha}(L)\) |
| ---- | ---- | ---- | ---- |
| 0.95 | [Value here] | [Value here] | [Ratio here] |
| 0.99 | [Value here] | [Value here] | [Ratio here] |
| 0.995 | [Value here] | [Value here] | [Ratio here] |
| 0.999 | [Value here] | [Value here] | [Ratio here] |

Comment: Analyze the values obtained for \(VaR_{\alpha}(F)\) and \(ES_{\alpha}(F)\) and discuss any patterns or trends in the ratios \(ES_{\alpha}(L)/VaR_{\alpha}(L)\).

#### (b) Model assumptions are never perfect. Suppose that the true loss DF \(F_L\) is within 0.007 of the assumed DF: \(|F_L(x)−F(x)|≤0.007\), \(x\in R\). Under that assumption, in what range can the true value of \(VaR_{\alpha}(F_L)\) be for the confidence levels \(\alpha = 0.95; 0.99; 0.995\)? Comment on your findings. [3 marks]

For each confidence level \(\alpha\):
1. Find the range of \(F_L(x)\) based on the given assumption.
   - Since \(|F_L(x)−F(x)|≤0.007\), then \(F(x)-0.007\leq F_L(x)\leq F(x)+0.007\).
2. Determine the range of \(VaR_{\alpha}(F_L)\):
   - Recall that \(VaR_{\alpha}(F_L)\) is the value such that \(F_L(VaR_{\alpha}(F_L)) = 1-\alpha\).
   - Use the range of \(F_L(x)\) to find the possible values of \(VaR_{\alpha}(F_L)\).

Comment: Discuss the implications of the range of possible true values of \(VaR_{\alpha}(F_L)\) and how it reflects the uncertainty due to the imperfect model assumption.

### 2. On 4 January 2022, one of our former MSc students (we will refer to her as Ms X) purchased shares.

#### (a) What risk factors \(Z_t=(Z_{t,1},...,Z_{t,d})'\) are appropriate for this portfolio? Suggest and specify them. Map the risks by representing the day \(t = 0,1,...,T\) portfolio value \(V_t\) (in AUD) as a function of \(Z_t\) and hence give representations for (i) the loss values \(L_{t + 1}\) (in terms of the day \(t\) risk factors’ values and their next day changes \(X_{t + 1}:=Z_{t + 1}-Z_t\)), (ii) the loss operator \(l^{[t]}(x)\) and (iii) the linearised loss operator \(l^{\Delta}[t](x)\) of the portfolio. [6 marks]

Risk factors could include stock prices of the different shares (in their respective currencies), currency exchange rates, and market volatility indicators.

1. Represent \(V_t\) as a function of \(Z_t\):
   - Express the portfolio value in terms of the risk factors. For example, if the portfolio consists of shares with prices in different currencies, \(V_t\) could be a function of stock prices and exchange rates.
2. Represent \(L_{t + 1}\):
   - \(L_{t + 1}\) can be defined in terms of the change in portfolio value from day \(t\) to \(t + 1\). This can be expressed in terms of the risk factors and their changes.
   - \(L_{t + 1}=V_t-V_{t + 1}\), where \(V_{t + 1}\) is a function of \(Z_{t + 1}\) and \(V_t\) is a function of \(Z_t\). So \(L_{t + 1}\) can be expressed in terms of \(Z_t\), \(Z_{t + 1}\), and \(X_{t + 1}\).
3. Define the loss operator \(l^{[t]}(x)\):
   - The loss operator can be defined based on the loss values \(L_{t + 1}\). For example, \(l^{[t]}(x)=L_{t + 1}\) if some condition on \(x\) is met.
4. Define the linearised loss operator \(l^{\Delta}[t](x)\):
   - The linearised loss operator is an approximation of the loss operator. It can be derived by linearising the relationship between the loss and the risk factors.

#### (b) Calculate the maximum difference \(max_{1\leq t\leq T}|L_t-L^{\Delta}_t|\) between the true losses and the linearised losses of the portfolio during the indicated time period. On what day was it observed? What risk factors you think were mostly responsible for that largest discrepancy? Explain. [2 marks]

1. Calculate \(|L_t-L^{\Delta}_t|\) for each \(t\).
2. Find the maximum value and the corresponding day.
3. Analyze the risk factors and explain which ones might be responsible for the largest discrepancy. For example, if a particular stock had a large price fluctuation or an exchange rate had a significant change on that day, these could be the responsible factors.

#### (c) Compute the average relative discrepancy between the true and linearised losses and the average absolute relative loss/gain of the portfolio, i.e. the values \(\frac{1}{T}\sum_{t = 0}^{T - 1}\frac{|L_{t + 1}-L^{\Delta}_{t + 1}|}{V_t}\) and \(\frac{1}{T}\sum_{t = 0}^{T - 1}\frac{|L_{t + 1}|}{V_t}\). Compare the former with the latter and comment on your findings. [2 marks]

1. Calculate the average relative discrepancy:
   - Compute \(\frac{|L_{t + 1}-L^{\Delta}_{t + 1}|}{V_t}\) for each \(t\) and then take the average over all \(t\).
2. Calculate the average absolute relative loss/gain:
   - Compute \(\frac{|L_{t + 1}|}{V_t}\) for each \(t\) and then take the average over all \(t\).
3. Compare the two values and comment on the findings. For example, if the average relative discrepancy is much smaller than the average absolute relative loss/gain, it indicates that the linearisation is relatively accurate.

#### (d) Calculate the numerical values of the coefficients appearing in the expression for the linearised loss operator \(l^{\Delta}[t_0]\) on day \(t_0 := 500\), i.e., 05 Dec 2023. [1 mark]

Use the appropriate linearisation method to determine the coefficients for the linearised loss operator on the specified day.

#### (e) Compute the method-of-moments estimates of the mean vector and covariance matrix for the vector \(X_t\) of the risk factor changes, basing on the whole data set (from 04 Jan 2022 to 28 Dec 2023). [2 marks]

1. Calculate the sample mean vector:
   - For each component of \(X_t\), compute the mean over the entire data set.
2. Calculate the sample covariance matrix:
   - Use the formula for the sample covariance matrix based on the data for \(X_t\).

#### (f) Use the Variance–Covariance Method and your results from parts (d) and (e) to calculate \(VaR_{0.95}(L_{t_0 + 1})\) and \(ES_{0.95}(L_{t_0 + 1})\). [This means you will be using “future data” (relative to time \(t_0\)), cf. (e). That’s OK, just do that.][3 marks]

1. Use the Variance–Covariance Method formula:
   - \(VaR_{0.95}(L_{t_0 + 1})=\mu+\sigma z_{\alpha}\), where \(\mu\) is the mean of \(L_{t_0 + 1}\), \(\sigma\) is the standard deviation of \(L_{t_0 + 1}\), and \(z_{\alpha}\) is the quantile of the standard normal distribution for the confidence level \(0.95\).
   - \(ES_{0.95}(L_{t_0 + 1})\) can be computed using an appropriate formula based on \(VaR_{0.95}(L_{t_0 + 1})\) and the distribution of \(L_{t_0 + 1}\).
2. Use the results from parts (d) and (e) to determine the mean and covariance matrix for \(L_{t_0 + 1}\) and then calculate \(VaR_{0.95}(L_{t_0 + 1})\) and \(ES_{0.95}(L_{t_0 + 1})\).

#### (g) Use the historical simulation method to produce a sample of simulated losses \(eL_u=l^{[t_0]}(X_u)\), \(u = t_0 - n + 1, t_0 - n + 2,..., t_0\), for \(n = 400\) and plot a histogram for it. Use the sample to give a quantile estimator for \(VaR_{0.95}(L_{t_0 + 1})\) and an estimator for \(ES_{0.95}(L_{t_0 + 1})\). Compare your estimates with the results of part (f) and comment. [4 marks]

1. Generate the sample of simulated losses:
   - Use the historical data to simulate losses based on the loss operator \(l^{[t_0]}\) and the values of \(X_u\) for \(u = t_0 - n + 1, t_0 - n + 2,..., t_0\).
2. Plot a histogram of the simulated losses.
3. Estimate \(VaR_{0.95}(L_{t_0 + 1})\) and \(ES_{0.95}(L_{t_0 + 1})\):
   - Use quantile estimation methods for \(VaR_{0.95}(L_{t_0 + 1})\) and an appropriate estimator for \(ES_{0.95}(L_{t_0 + 1})\) based on the simulated losses.
4. Compare with the results from part (f):
   - Analyze the differences between the estimates obtained from the historical simulation method and the Variance–Covariance Method. Comment on the advantages and disadvantages of each method.

### 3. (a) Show that \(Σ=\begin{pmatrix}3&-2&1\\-2&3&-1\\1&-1&1\end{pmatrix}\) is a covariance matrix. [1 mark]

A matrix is a covariance matrix if it is symmetric and positive semi-definite.
1. Check symmetry:
   - The transpose of \(Σ\) is equal to itself, so it is symmetric.
2. Check positive semi-definiteness:
   - For any vector \(x=(x_1,x_2,x_3)'\), \(x'Σx\geq0\).
   - Compute \(x'Σx\) and show that it is non-negative.

### (b) Compute (by hand!) the (lower triangular) Cholesky factor for the matrix \(Σ\). Give the final answer in matrix form, with matrix entries being decimal numbers with four digits after the decimal point. Show your work. [2 marks]

The Cholesky decomposition of a symmetric positive definite matrix \(A\) is \(A = LL'\), where \(L\) is a lower triangular matrix.
1. Let \(Σ=\begin{pmatrix}3&-2&1\\-2&3&-1\\1&-1&1\end{pmatrix}=LL'\).
2. Assume \(L=\begin{pmatrix}a&0&0\\b&c&0\\d&e&f\end{pmatrix}\).
3. Compute \(LL'\) and equate it to \(Σ\):
   - \(LL'=\begin{pmatrix}a&0&0\\b&c&0\\d&e&f\end{pmatrix}\begin{pmatrix}a&b&d\\0&c&e\\0&0&f\end{pmatrix}=\begin{pmatrix}a^2&ab&ad\\ab&b^2 + c^2&bd + ce\\ad&bd + ce&d^2 + e^2 + f^2\end{pmatrix}\).
4. Equate the corresponding entries:
   - \(a^2 = 3\), so \(a=\sqrt{3}\).
   - \(ab = -2\), so \(b=\frac{-2}{\sqrt{3}}\).
   - \(b^2 + c^2 = 3\), substituting \(b=\frac{-2}{\sqrt{3}}\), solve for \(c\).
   - \(ad = 1\), so \(d=\frac{1}{\sqrt{3}}\).
   - \(bd + ce = -1\), substituting \(b=\frac{-2}{\sqrt{3}}\), \(d=\frac{1}{\sqrt{3}}\), and the value of \(c\), solve for \(e\).
   - \(d^2 + e^2 + f^2 = 1\), substituting \(d=\frac{1}{\sqrt{3}}\), and the value of \(e\), solve for \(f\).

The Cholesky factor \(L=\begin{pmatrix}\sqrt{3}&0&0\\\frac{-2}{\sqrt{3}}&c&0\\\frac{1}{\sqrt{3}}&e&f\end{pmatrix}\) with the values of \(c\


# 《MAST90051 Mathematics of Risk Problem Sheet 6/2024 Assignment 1》

## 一、问题描述
1. 已知随机损失\(L\)具有绝对连续的分布函数\(F\)和密度函数\(f\)，其中\(f(x)=4x^{-4}\ln x\)，\(x>1.5\)。
   - （a）计算分布函数尾部\(F(x)\)，并求出在置信水平\(\alpha = 0.95\)、\(0.99\)、\(0.995\)、\(0.999\)下的风险价值\(VaR_{\alpha}(F)\)和预期损失\(ES_{\alpha}(F)\)，同时计算\(ES_{\alpha}(L)/VaR_{\alpha}(L)\)的比值，以表格形式呈现结果并简要评论。
   - （b）假设真实损失分布函数\(F_L\)与假设分布函数\(F\)之差在\(0.007\)以内，求在置信水平\(\alpha = 0.95\)、\(0.99\)、\(0.995\)下真实风险价值\(VaR_{\alpha}(F_L)\)的范围，并评论结果。
2. 2022 年 1 月 4 日，一位学生（Ms X）购买了一定数量的不同公司股票，其组合在 2023 年 12 月 28 日前保持不变。
   - （a）确定该投资组合的风险因素\(Z_t=(Z_{t,1},\ldots,Z_{t,d})'\)，并以风险因素表示投资组合在\(t\)时刻的价值\(V_t\)、损失值\(L_{t + 1}\)、损失算子\(l^{[t]}(x)\)和线性化损失算子\(l^{\Delta[t]}(x)\)。
   - （b）计算投资组合在给定时间段内真实损失与线性化损失的最大差值\(\max_{1\leq t\leq T}|L_t - L^{\Delta}_t|\)，并指出在哪一天出现以及哪些风险因素可能对此负责。
   - （c）计算投资组合真实损失与线性化损失的平均相对差异以及平均绝对相对损失/收益，并比较两者结果进行评论。
   - （d）计算在特定日期\(t_0 = 500\)（即 2023 年 12 月 5 日）线性化损失算子\(l^{\Delta[t_0]}\)中的系数数值。
   - （e）基于整个数据集计算风险因素变化向量\(X_t\)的均值向量和协方差矩阵的矩估计。
   - （f）使用方差 - 协方差方法和（d）、（e）的结果计算\(VaR_{0.95}(L_{t_0 + 1})\)和\(ES_{0.95}(L_{t_0 + 1})\)。
   - （g）使用历史模拟方法生成模拟损失样本，绘制直方图，给出\(VaR_{0.95}(L_{t_0 + 1})\)和\(ES_{0.95}(L_{t_0 + 1})\)的估计值，并与（f）的结果进行比较和评论。
3. （a）证明矩阵\(\Sigma=\begin{pmatrix}3&-2&1\\-2&3&-1\\1&-1&1\end{pmatrix}\)是协方差矩阵。
   - （b）手动计算矩阵\(\Sigma\)的（下三角）Cholesky 因子，以矩阵形式给出结果，保留四位小数并展示计算过程。
   - （c）设\(X=(X_1,X_2,X_3)'\)是均值为\((1,2,3)'\)、协方差矩阵为\(\Sigma\)的正态随机向量，计算并绘制子向量\((X_1,X_2)'\)、\((X_1,X_3)'\)和\((X_2,X_3)'\)的密度，分别制作 3D 曲面图和等高线图，并在\([-3,5]^2\)区间上进行，简要评论结果。
   - （d）制作混合密度\(0.7f_{(X_1,X_2)'}(x_1,x_2)+0.3f_{(X_2,X_3)'}(x_1 - 1,x_2 - 1)\)在\([-3,5]^2\)区间上的 3D 曲面图和等高线图，可以调整混合权重和参数以观察不同形状的二元正态密度。

## 二、具体问题分析

### 问题 1
1. **(a) 计算分布函数尾部、风险价值和预期损失**
   - 首先计算分布函数\(F(x)\)，对于密度函数\(f(x)=4x^{-4}\ln x\)，\(x>1.5\)，分布函数\(F(x)=\int_{1.5}^{x}f(t)dt\)。
   - 然后计算风险价值\(VaR_{\alpha}(F)\)，即分布函数的逆函数\(F^{-1}(1-\alpha)\)。
   - 预期损失\(ES_{\alpha}(F)\)是在损失超过\(VaR_{\alpha}(F)\)的条件下的平均损失，计算公式为\(ES_{\alpha}(F)=\frac{1}{\alpha}\int_{\alpha}^{1}VaR_{u}(F)du\)。
   - 最后计算比值\(ES_{\alpha}(L)/VaR_{\alpha}(L)\)。将结果以表格形式呈现，并对结果进行简要评论，比如分析不同置信水平下风险价值和预期损失的变化趋势。
2. **(b) 确定真实风险价值范围**
   - 已知\(\vert F_L(x)-F(x)\vert\leq0.007\)，根据这个条件和已求出的风险价值\(VaR_{\alpha}(F)\)，确定在不同置信水平下真实风险价值\(VaR_{\alpha}(F_L)\)的范围。对结果进行评论，例如讨论模型假设的不确定性对风险价值估计的影响。

### 问题 2
1. **(a) 确定风险因素和表示投资组合价值与损失**
   - 确定适用于该投资组合的风险因素\(Z_t\)，并通过风险因素表示投资组合在\(t\)时刻的价值\(V_t\)。
   - 进一步表示损失值\(L_{t + 1}\)、损失算子\(l^{[t]}(x)\)和线性化损失算子\(l^{\Delta[t]}(x)\)，这需要考虑投资组合的构成和风险因素的变化。
2. **(b) 计算最大差值和确定主要风险因素**
   - 计算真实损失与线性化损失的最大差值\(\max_{1\leq t\leq T}|L_t - L^{\Delta}_t|\)，并确定在哪一天出现这个最大差值。
   - 分析可能导致最大差值的风险因素，这需要考虑不同风险因素在特定时间段内的变化情况。
3. **(c) 计算平均相对差异和平均绝对相对损失/收益**
   - 计算投资组合真实损失与线性化损失的平均相对差异\(\frac{1}{T}\sum_{t=0}^{T-1}\frac{\vert L_{t + 1}-L^{\Delta}_{t + 1}\vert}{V_t}\)。
   - 计算平均绝对相对损失/收益\(\frac{1}{T}\sum_{t=0}^{T-1}\frac{\vert L_{t + 1}\vert}{V_t}\)。
   - 比较这两个值并进行评论，例如讨论线性化方法对损失估计的准确性。
4. **(d) 计算特定日期的系数数值**
   - 在特定日期\(t_0 = 500\)（即 2023 年 12 月 5 日），计算线性化损失算子\(l^{\Delta[t_0]}\)中的系数数值。
5. **(e) 计算均值向量和协方差矩阵的矩估计**
   - 基于整个数据集，计算风险因素变化向量\(X_t\)的均值向量和协方差矩阵的矩估计。
6. **(f) 计算风险价值和预期损失**
   - 使用方差 - 协方差方法和前面计算的结果，计算\(VaR_{0.95}(L_{t_0 + 1})\)和\(ES_{0.95}(L_{t_0 + 1})\)。
7. **(g) 使用历史模拟方法进行估计和比较**
   - 使用历史模拟方法生成模拟损失样本\(eL_u = l^{[t_0]}(X_u)\)，其中\(u = t_0 - n + 1,t_0 - n + 2,\ldots,t_0\)，\(n = 400\)。
   - 绘制模拟损失的直方图，并给出\(VaR_{0.95}(L_{t_0 + 1})\)和\(ES_{0.95}(L_{t_0 + 1})\)的估计值。
   - 将这些估计值与（f）的结果进行比较和评论，例如讨论不同方法对风险价值和预期损失估计的准确性和稳定性。

### 问题 3
1. **(a) 证明矩阵是协方差矩阵**
   - 协方差矩阵是对称半正定矩阵，需要验证给定矩阵\(\Sigma\)是否满足这些性质。
2. **(b) 计算 Cholesky 因子**
   - Cholesky 分解是将一个对称正定矩阵分解为下三角矩阵与其转置的乘积。手动计算矩阵\(\Sigma\)的 Cholesky 因子，展示计算过程并以矩阵形式给出结果。
3. **(c) 计算和绘制子向量密度**
   - 对于给定的正态随机向量\(X=(X_1,X_2,X_3)'\)，计算子向量\((X_1,X_2)'\)、\((X_1,X_3)'\)和\((X_2,X_3)'\)的密度。
   - 分别制作 3D 曲面图和等高线图，并在\([-3,5]^2\)区间上进行。
   - 对结果进行简要评论，例如观察不同子向量的密度分布特点。
4. **(d) 制作混合密度的图形**
   - 制作混合密度\(0.7f_{(X_1,X_2)'}(x_1,x_2)+0.3f_{(X_2,X_3)'}(x_1 - 1,x_2 - 1)\)在\([-3,5]^2\)区间上的 3D 曲面图和等高线图。
   - 可以调整混合权重和参数以观察不同形状的二元正态密度。

# MAST90051 Assignment 1

# CS Tutor | 计算机编程辅导 | Code Help | Programming Help

# WeChat: cstutorcs

# Email: tutorcs@163.com

# QQ: 749389476

# 非中介, 直接联系程序员本人
