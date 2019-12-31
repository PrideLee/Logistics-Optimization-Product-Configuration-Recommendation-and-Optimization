# General map of reliability (The summary of Kang's seminar in CAS)

## 1. The origin of reliability

### 1.1 The reliability in World War 2

&emsp;&emsp;In order to infer the failure probability of rocket launch during the period of World War 2, Robert Lusser[1] provided the probability measure, which is the early development of reliability. Based on the classical probability theory[2], the relevant researches about reliability also keep to the following principles:

- Axiom 1. The probability of an event is a non-negative real number:

$$
P(E)\in \Bbb{R},P(E) \geq 0 \qquad \forall E\in F \tag{1}
$$

&emsp;&emsp;&emsp;where, $F$ is the event space. It follows that $P(E)$ is always finite.

- Axiom 2. The probability that at least one of the elementary events in the entire sample space occur is 1, which obeys the assumption of unit measure:

$$
P(\Omega)=1 \tag{2}
$$

- Axiom 3. Relying on the assumption of $\sigma$-additivity[4], any countable sequence of disjoint sets (synonymous with mutually exclusive events) $E_1, E_2, ...$ statisfies:

$$
P(\bigcup_{i=1}^{\infty}E_i)=\sum_{i=1}^{\infty}P(E_i) \tag{3}
$$

&emsp;&emsp;&emsp;that is to, for the independent events, the probability of either event occurring is the sum of the probability of each event occurring.

&emsp;&emsp;From the Kolmogorov axioms, one can deduce the chain rule[5] (also called the general product rule), which permits the calculation of any member of the joint distribution of a 
set of random variables, and is also useful for Bayesian Networks. 

&emsp;&emsp;Especially for the mutally exclusive events, we will have:

$$
P(\prod_{i=1}^{\infty}E_i)=\prod_{i=1}^{\infty}P(E_i) \tag{4}
$$

&emsp;&emsp;According to the principles mentioned above of probability, the researchers built the theory frame of reliabililty in the early stage, includes:

- Utilize the probability to represent the reliability of each unit or system;
- Unit reliability = 1 - failure probability;
- The failure probability can be acquired by statistical methods;
- The system reliability calculated by the product of each unit (cascade model);

<center>

![The origiaon of reliabiliy](classicial_realibility.png)
<br/>
Fig 1. The origiaon of reliability
</center>

### 1.2 DoD AGREE - The report about reliability

&emsp;&emsp;Based on the excellent works of R.Lusser, DoD published the AGREE report in 1957. From this report, the definition of reliability was elucidated formally and sophisticatedly: 

- Reliability is definied as the probability that a system will perform its intended function for a specified interval within a given time and under specified conditions;
- The reliability can be calculated by the formula: $R(t)=P(T>t)$, noted $t$ is the regular time, and $T$ is the longevity of products;
- Construct the index system, such as, MTBS, failure rate, etc;
- Determine the method of reliability allocation and PFA;
- Design the Reliability Acceptance Test, a statistics test method;

&emsp;&emsp;So as to practical:

- Provide the measures about the reliability design, like damping, heat-dissipated;
- Provide the redundant design for critical parts;
- Indicate that necessary measures should be taken to ensure the reliability requirements of purchasing parts;
- Indicate that enhance the failure feedback to improve the product design to realize the sustained growth of reliability; 

&emsp;&emsp;Above all, the early development of reliability relies on probability, statistics, the law of large numbers as well. And as for the engineering application, it can be concluded that the pattern "index selection-index predication-experimental confirmation-failure analysis-design improvement" has been determined. 

## 2. The development of reliability

&emsp;&emsp;With the technology developed rapidly, the reliability has been attracted more and more attention both in industry, military as well as aerospace field, and the reliability theory also made a great leap, which developed 4 branches: statistics-based, physical-based, logical model and reliability design.

### 2.1 Statistics-based method

&emsp;&emsp;The validity of the statistics-based reliability prediction method is guaranteed by LLB and probability axioms, which applies the frequency to evaluate the probability. Thus, we are allowed to count the failure events and predict the failure probability.

<center>

![Statistical](statistical.jpg)
<br/>
Fig 2. Statistical Analysis of Failure Data - Failures Percentage of Product Components
</center>

&emsp;&emsp;In addition, the researchers also defined various indexes to represent the reliability:

- Failure rate ($\lambda$)[7]: the frequency with which an engineered system or component fails, expressed in failures per unit of time;
- Mean time between faiures (MTBR, $1/\lambda$): the predicted elapsed time between inherent failures of a mechanical or electronic system, during normal system operation. While about the non-repairable system, we apply mean time of failure (MTTF) to measurement;
- Mean time to repair (MTTR): represents the average time required to repair a failed component or device[8]. As far as i'm concerned, it is the total corrective maintenance time for failures divided by the total number of corrective maintenance actions for failures during a given period[9];
- Reliable Life: the life for which the unit/item will be functioning successfully with the reliability of $R$;
- The time between overhauls (TBO or TBOH): the manufacturer's recommended number of running hours or calendar time before an aircraft engine or other component requires overhaul[10];
- Availability[11]: The degree to which a system or equipment is in a specified operable and committable state at the start of a mission, when the mission is called for at an unknown, i.e, a random, time. Simply put, availability is the proportion of time a system is in a functioning condition. This is often described as a mission capable rate. Mathematically, this is expressed as 100% minus unavailability. And it also can be explained as the ratio of the total time a functional unit is capable of being used during a given interval to the length of the interval;

&emsp;&emsp;In order to shed the lights on the product failure, the researchers also design numerous statistical test methods for the design and manufacturing process, such as Environmental Stress Screening (ESS)[12] Reliability Acceptance Test, Reliability Growth Test[13], Accelerated Life Test (ALT) [14], Accelerated Degradation Test (ADT), etc. And according to a huge amount of repeat experiment results, researchers are able to design empirical formulas to represent the failure rate distinctly: 

<center>

![faiure model](failure_mode.jpg)
<br/>
Fig 3. Failure model of electronic components
</center>

&emsp;&emsp;While, about the statistical method to predict the failure probability has four essential defects: 

1) In real engineering applications, the failure happens is rare, which is small sample events, thus it doesn't meet the requirements of LLB, and the prediction accuracy will be affected dramatically; 
   
2) Contribute to the statistics requirement, only when the failure happens can we collect the data. Thus, beforehand reliability prediction is not allowed;
   
3) The statistical models only give us a number about the failure probability, which can not provide any clue about the improvement direction. In consequence, it is useless for engineering practice; 

4) Boil down to the cascade model and probability production principle, the product failure rate will be extremely small. However, it is not consistent with the fact;

&emsp;&emsp;By the way, about the small sample estimation is always a difficulty in statistics and machine learning, which is not satisfied the LLB (While, about the massive data statistics, the sampling strategy will be an art, how can we take sample resample to reflect the overall distribution and realize unbiased estimate). The valid solve strategies are to introduce more external information and merge abundant Priori knowledge. For instance, the Bayes method relies on the posterior probability to amend the prior probability continuously, so the estimation will be better and better. As for other methods are the same idea. About the dilemma that probability tends to zero caused by a continued product, which is similar to the Vanishing Gradient Problem in Back Propagation algorithm. Hence, whether we can referent the ResNet idea, using skip product method to alleviate this problem. Or can we apply the attention mechanism provided in the machine translation, select the core parts to calculate the relibility? Besides, although it seems reasonable for the cascade model to calculate the continued product, in the real situation, it is impossible. Tracing to its root, the assumption of independence for each unit is quite strictly. It means the failure probability of a model is not equal to the failure probability product of each part. Therefore, we can not usage this formula simply, especially for the parts level. Or we have to design a more rational formula for the failure probability calculation, at least aiming the weak link and taking the maximum value for all the units is a feasible strategy.

### 2.2 Physical method

&emsp;&emsp;To overcome the above challenges, researchers attempt to figure out the mechanism of failures, to research the physical model of parts, material, process, etc. 

&emsp;&emsp;Therefore, the failure time model has been proposed, which also named the causality model: 

<center>

![physicial](physicial.jpg)
<br/>
Fig 4. Failure time model
</center>

&emsp;&emsp;Furthermore, the working state of products can not be the same in the whole life, consider the performance degradation of the product lifecycle, experts further provided the performance degradation model: 

<center>

![physicial](performance_degradation.jpg)
<br/>
Fig 5. Performance degradation model
</center>

&emsp;&emsp;The physical model could analysis the essential reason for failures, and stimulate to acquire the reliability index through the parameter randomization. Thus, the drawbacks of the statistical model, such as a small sample, hard to improve, can be relieved effectively. 

&emsp;&emsp;Nevertheless：

1) How can we construct the physical model, it's difficult to figure out the intrinsic mechanism and determine the key factors which affect the item most. 
2) In addition, it is a common method to specify parameters obey the Gaussian distribution, while how can we ensure the correctness of this precondition. Whether can we utilize the mixture gaussian to build the model?

### 2.3 Logic model

&emsp;&emsp;Through decompose the system or module into the independent item/unit to rebuild it, and determine the logic relation between each part, then analysis the failure probability. The typical logic model includes a failure tree model and probability graph model, showing as follow:

<center>

![types of reliability models](reliability_types.jpg)
<br/>
Fig 6. Reliability frameworks
</center>

&emsp;&emsp;FTA (Fault tree analysis)[15] is a valid method for reliability evaluation. FTA is a top-down, deductive failure analysis in which an undesired state of a system is analyzed using Boolean logic to combine a series of lower-level events. By understanding how systems can fail, to identify the best ways to reduce risk or to determine (or get a feeling for) event rates of a safety accident or a particular system level (functional) failure.  

<center>

![FTA](FTA.png)
<br/>
Fig 7. Fault tree analysis
</center>

&emsp;&emsp;Logic model considers units work cause system work and units failure cause system failure, so that we can calculate the failure probability relying on the logic relation. While, since it also assumes the item/unit independent, the logic model faces probability ebbs quickly too. 

### 2.4 Reliability design

&emsp;&emsp;In spite of we can not bring the failure mechanism to the light, we are allowed to enhance the reliability in the design stage, such as derating design, protective design (thermal design, electromagnetic compatibility design, damping, anti-radiation design) for electronic products, safety factor design, and stress intensity design for mechanical products. This strategy can ensure the products' reliability effectively, especially for engineering applications.   

<center>

![reliability design](design.jpg)
<br/>
Fig 8. reliability design
</center>

&emsp;&emsp;All in all, whether the products can work properly and achieve the specific function or not, it is determined by the task requirements as well as user definition, which is reflected in the specific performance indexes. Hence, comparing to the performance parameter margins, we can adjust the system status. And the environment test and reliability enhanced test is just to confirm the performance margins. That is the positive thinking to solve the problem, rather than count the failure times and give the failure probability. 

&emsp;&emsp;But:

1) It is also obscure and arbitrary for experts to determine the value of margin; 

2) The performance margin can not be reflected the reliability measurement easily, which only reflect whether the failure will arise, and how likely it will arise; 

3) As for stress-intensity design, the distribution of stress and intensity are also be denoted as Gaussian distribution, which has not solide theoretical supports, and may have some problems in practice.  

## 3. Some solutions about the above challenges

&emsp;&emsp;Generally speaking, owing much to the inherent uncertain and cognition uncertain[16] that lead the aforementioned challenges. In order to overcome these problems and to make the prediction more accuracy, two major classes of methods have been proposed:    

- Inaccuracy probability reliability measurements: Bayes theory, Evidence theory, Interval analysis theory;
- Fuzzy reliability;

### 3.1 Bayes reliability

&emsp;&emsp; Based on Bayes theory, the posterior distribution can be represented like this:

$$
p(\theta | y)=\frac{f(y|\theta)p(\theta)}{m(y)} \tag{5}
$$

&emsp;&emsp;where, $p(\theta|y)$ denotes as posterior probability distribution, $f(y|\theta)$ denotes as likelihood function, $p(\theta)$ denotes as prior distribution, and $m(y)$ denotes as sample density function. Thus, we can adjust the prior distribution and rely on a small amount of failure data to estimate the reliability [17].

<center>

![bayes](bayes.png)
<br/>
Fig 9. Bayes Theory
</center>

### 3.2 Evidence theory 

&emsp;&emsp;Proposed by A.Dempster and G.Shafer, evidence theory calculates the Belief and Plausibility to determine the probability interval[18]. To be specific, according to the weighted sum of failure assignment function for the variable interval to determine the failure probability interval[19]. 

<center>

![evidence](evidence.jpg)
<br/>
Fig 10. Evidence Theory
</center>

&emsp;&emsp;Through introduce more expert knowledge or additional information to improve the prediction accuracy, while how to merge and utilize this supplementary information effectively, it is a question. What's more, transfer the point estimation to interval estimation, it seems more reliable for reliability evaluation, while how to balance the interval size, precision, and confidence is also a challenge.   

### 3.3 Interval analysis

&emsp;&emsp;The thought of interval analysis is quite plain, that is considering apply interval to represent the uncertainty[20]. Briefly speaking, this method realizes the transfer from input parameters interval to output failure probability interval based on interval algorithm or optimization algorithm.

<center>

![interval](interval.png)
<br/>
Fig 11. Interval analysis Theory
</center>

&emsp;&emsp;While, the evidence method is still calculate the probability based on the cascade model. Thus, the problem of probability vanishes, and expansion is existing yet[22].

### 3.4 Fuzzy reliability

&emsp;&emsp;In the realistic world, almost everything is not blake or white, there is a middle area of gray. That's to say anything has a sort of uncertainty. We can not rely on the probability of measurement of this status. For instance, about the age, the stature, what's the age can be considered as younger or elder exactly, it is challenging to offer a standard answer. And the fuzzy theory is able to represent this uncertainty based on membership functions[23].       

&emsp;&emsp;About the reliability, fuzzy reliability points out that the system only has two states, work, and failure, in the meantime, consider the failure time $T$ is a fuzzy variable and define the possibility of $t>T$ to represent the reliability:

$$
R(t)=\Pi (T\geq t)\tag{6}
$$

&emsp;&emsp;While, there is a nature paradox between axiom 1 and axiom 2 of possibility theory.

$$
\begin{aligned}
    \because & \, \begin{cases}
                            axiom2:\Pi(\Gamma)=\Pi(\Lambda_1,\Lambda_2)=1\\
                            axiom3: \Pi(\Gamma)=max(\Pi(\Lambda_1), \Pi(\Lambda_2))=1\tag{7}
                         \end{cases}\\
    \therefore & \, \exists \; \Lambda_i=1, (i=1,2)\\
    \because & \, \Lambda_1,\Lambda_2 \; \text{are exclusive events}\\
    \therefore & \, 
    \begin{cases}
        \Lambda_1<1 \implies \Lambda_2=1\\
        \Lambda_2<1 \implies \Lambda_1=1
    \end{cases}
\end{aligned}
$$

&emsp;&emsp;Hence, possibility theory does not meet the normative, and it will not be suitable for reliability calculation[24].

### 3.5 Brief summary

&emsp;&emsp; Totally speaking, the early development of reliability is closed to the probability theory. It is applying the failure probability to measure the system reliability. While the fundamental of probability is a statistic, and in a realistic world, the failure happened are small sample events. Thus, it's difficult for us to acquire an accurate prediction, and only when the failures arise can we perform statistical analysis. In addition, the probability calculation of the cascade model faces the probability of vanishing problems. What's more, the failure probability is merely a number, which can not provide any suggestions about the improvement of the system. Attribute to the above defects. Researchers struggle to construct the physical model to analysis the cause of failures and based on the experiments as well as stimulation to predict the reliability and improve the system at the same time. While limited to cognitive uncertainty and inherent uncertainty, it is hard to determine the core factors and build comprehensive models. As for the logic model, it is a sophisticated method to analysis failure pattern and failure reasons, but about the reliability prediction, it is also powerless. In engineering practice, the technicists apply reliability design ( derating design, protective design, safety factor design, and stress intensity design) to ensure the reliability of the products, it is safe to say that it is a compelling work for tasks, but the problem still exists.

&emsp;&emsp;How to increase the reliability accuracy, there are three main strategies, include Bayes theory, interval estimation, and fuzzy theory. Must say the Bayes method is a powerful theoretical framework through introduce the posteriori information and external data to amend the prior knowledge and improve the accuracy. Fuzzy theory is also a genius thought, but it still has a little nibs. Well, belief reliability seems to provide a reasonable solution very recently.

## 4. Belief reliability





## Reference

[1] Lusser's Law, Wikipedia, https://en.wikipedia.org/wiki/Lusser%27s_law.

[2] Kolmogorov, Wikipedia, https://en.wikipedia.org/wiki/Andrey_Kolmogorov.

[3] Probability axioms, Wikipedia, https://en.wikipedia.org/wiki/Probability_axioms.

[4] Hájek, Alan (August 28, 2019). "Interpretations of Probability". Stanford Encyclopedia of Philosophy. Retrieved November 17, 2019.

[5] Chain rule (probability), Wikipedia, https://en.wikipedia.org/wiki/Chain_rule_(probability).

[6] Law of large numbers, Wikipedia, https://en.wikipedia.org/wiki/Law_of_large_numbers.

[7] Failure rate, Wikipedia, https://en.wikipedia.org/wiki/Failure_rate.

[8] BusinessDictionary.com, Mean Time To Repair definition.
 
[9] Institute for Telecommunications Sciences, Mean Time To Repair definition Archived 2008-09-25 at the Wayback Machine.

[10] Teledyne Continental Motors (17 November 1998). "Time Between Overhaul Periods" (PDF). Retrieved 3 January 2015.

[11] Acailability, Wikipedia, https://en.wikipedia.org/wiki/Availability.

[12] Environmental stress screening (ESS), Wikipedia, https://en.wikipedia.org/wiki/Environmental_stress_screening.

[13] Reliability Growth Planning, Reliawiki, http://reliawiki.org/index.php/Reliability_Growth_Planning.

[14] Accelerated life testing, Wikipedia, https://en.wikipedia.org/wiki/Accelerated_life_testing.

[15] Fault tree analysis, Wikipedia, https://en.wikipedia.org/wiki/Fault_tree_analysis.

[16] Kiureghian, Armen Der, and O. Ditlevsen. Aleatory or epistemic? Does it matter?. Structural Safety 31.2(2009): 105-112.

[17] MS. Hamada, AG. Wilson, CS. Reese and HG. Martz, Bayesian Reliability, Spinger, 2008.

[18] G. Shafer, A mathematical theory of evidence, Princeton: Princeton University Press, 1976.

[19] ZP. Mourelatos and J. Zhou, A design optimization method using evidence theory, Journal of Mechanical Design, 2006, 128(4): 901-908.

[20] RE. Moore, Methods and applications of interval analysis. Philadelphia: Siam, 1979.

[21] DR. Karanki, HS. Kushwaha, AK. Verma et al. , Uncertainty analysis based on probability bounds (P-Box) approach in probabilistic safety assessment, Risk Analysis, 2009, 29(5): 662-675.

[22] Rui Kang, Qingyuan Zhang, Zhiguo Zeng, Enrico Zio, Xiaoyang Li. “Measuring reliability under epistemic uncertainty: Review on non-probabilistic reliability metrics ”. Chinese Journal of Aeronautics 29(3):571-579, 2016.

[23] L.A. Zadeh, Fuzzy sets, Information and Control, 1965, 8: 338-353.






