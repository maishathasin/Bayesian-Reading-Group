Presentation notes 


## Very incoherent, presentation notes, most of these notes will not make sense alone, so proceed with caution !



We read another paper to get the feel of the other objections to bayesian methods. 
This article presents a series of objections to Bayesian inference, written in the voice of a hypothetical anti-Bayesian statistician. The article is intended to elicit elaborations and extensions of these and other arguments from non-Bayesians and responses from Bayesians who might have different perspectives on these issues.

It was written in the perspective of someone who’s very anti bayesian, and the main points he talks about is that usually bayesysts say that their bayesian model is a one size fits all kind of approach, which is. Bayesians promote the idea that a multiplicity of parameters can be handled via hierarchical, typically exchangeable, models, but it seems implausible that this could really work automatically. In contrast, much of the work in modern non-Bayesian statistics is focused on developing methods that give reasonable answers using minimal assumptions.

: the idea that prior and posterior distributions represent subjective states of knowledge. Which is pretty problematic and he argues , that in most Bayes models the the its either beta, gamma , 


Beyond these objections is a general impression of the shoddiness of some Bayesian analyses, combined with a feeling that Bayesian methods are being oversold as an allpurpose statistical solution to genuinely hard problems. Compared to classical inference, which focuses on how to extract the information available in data, Bayesian methods seem to quickly move to elaborate computation. It does not seem like a good thing for a generation of statistics to be ignorant of experimental design and analysis of variance, instead becoming experts on the convergence of the Gibbs sampler. 



And then he goes on to say his torrent of objections, like that there is abosolutely no reasoning that a user should belie your prior distribution, from our previous article 
We can say that little changes in the prior distribution can change our results. 

like unbiased estimates and I like confidence intervals that really have their advertised confidence coverage. I know that these aren’t always going to be possible, but I think the right way forward is to get as close to these goals as possible and to develop robust methods that work with minimal assumptions. The Bayesian approach—to give up even trying to approximate unbiasedness and to instead rely on stronger and stronger assumptions


Also a lot of bayests seem to believe do not really have 




Bayesianism assumes: (a) Either a weak or uniform prior, in which case why bother?, (b) Or a strong prior, in which case why collect new data?, (c) Or more realistically, something in between, in which case Bayesianism always seems to duck the issue.



The mathematics of Bayesian decision theory lead inexorably to the idea that random sampling and random treatment allocation are inefficient, that the best designs are deterministic



there’s no good objective principle for choosing a noninformative prior (even if that concept were mathematically defined, which it’s not). Where do prior distributions come from, anyway? I don’t trust them and I see no reason to recommend that other people do, just so that I can have the warm feeling of philosophical coherence



I’d rather start with tried and true methods, and then generalize using something I can trust, such as statistical theory and minimax principles, that don’t depend on your subjective beliefs.



What a coincidence that, of all the infinite variety of priors that could be chosen, it always seems to be the normal, gamma, beta, etc., that turn out to be the right choices?


Either a weak or uniform prior, in which case why bother?, (b) Or a strong prior, in which case why collect new data?,




. The mathematics of Bayesian decision theory lead inexorably to the idea that random sampling and random treatment allocation are inefficient, that the best designs are deterministic


Bayesians also believe in the irrelevance of stopping times—that, if you stop an experiment based on the data, it doesn’t change your inference. Unfortunately for the Bayesian theory, the p-value does change when you alter the stopping rule, and no amount of philosophical reasoning will get you around that point.



There are a lot of assumptions that 


* Each student's test score is influenced by their individual ability and other factors unique to them. You can model this variability with a distribution, which captures the student-to-student differences in performance.
* Level 2 (School Level): Each school's average test score is influenced by the collective abilities of its students, as well as other school-specific factors. This variability can be modeled using a distribution that captures differences in school performance.
* Level 3 (Population Level): At the highest level, you might have a distribution that captures population-level trends, such as the overall average test score and how it varies across different regions.






Gelman's approach to statistical inference emphasizes studying variation and the associations between data, rather than searching for statistical significance.[8]
Gelman says his approach to hypothesis testing is "(nearly) the opposite of the conventional view"[9] of what is typical for statistical inference.


even if the study is done perfectly, even if measurements are unbiased and your sample is representative of your population, etc.



Introduction:
* The authors introduce the capture-recapture methodology, which involves sampling a population multiple times and identifying individuals that appear more than once.
* The paper focuses on the use of Gibbs sampling to calculate Bayesian estimates in this context, overcoming challenges posed by analytical and numerical difficulties.
* This approach enhances the scope of capture-recapture models, making formulations that were previously avoided due to complexity now practically applicable.
Gibbs Sampling for Bayesian Estimation:
* Gibbs sampling is presented as an alternative to analytical calculation and numerical approximation for Bayesian calculations in capture-recapture models.
* The method involves simulating from conditional distributions to approximate the posterior distribution of parameters of interest.


While the Gibbs sampler relies on conditional distributions, the Metropolis-Hastings sampler uses a full joint density distribution to generate a candidate draws


The primary reason why Gibbs sampling was introduced was to break the curse of dimensionality (which impacts both rejection and importance sampling) by producing a sequence of low dimension simulations that still converge to the right target




But first, what is Gibbs Sampling?
Gibbs Sampling is a Markov Chain Monte Carlo (MCMC) technique used in Bayesian statistics and computational statistics. It involves iteratively sampling from conditional distributions of each parameter in a Bayesian model while keeping other parameters fixed, allowing for estimation of complex probability distributions and posterior probabilities.

* Initial values assigned to all variables.
* Iterative process: Each variable updated based on conditional distribution given current other variable values.
* Repetition over iterations: Converges toward representative sample of desired joint distribution.
* Increasing iterations: Samples progressively approximate true distribution.
* Facilitates statistical inferences and estimation of quantities of interest.








* The authors highlight that the multinomial structure of capture-recapture models simplifies the Gibbs sampling process.
* The Gibbs sequence, obtained through iterations, can be used to approximate the marginal posterior distribution of the population size.
Hierarchical Bayesian Extensions:
* The paper discusses extending the capture-recapture models into a hierarchical framework, where parameters such as capture probabilities and prior hyperparameters can be modeled.
* Hierarchical models offer more flexibility in incorporating prior information and varying data characteristics.
* Different choices of prior distributions can be used to express varying degrees of prior knowledge or uncertainty.
* The Gibbs sampling technique remains applicable in the hierarchical context, allowing for estimation of both population size and model parameters.




The likelihood function for this is shown above. 

This is combined with priors of the form $\pi(N,p) = \pi(N) \pi(p)$ so N and p are priori independent. 



In the context of the sunfish example, the Beta distribution (Be(a, b)) is used as a prior distribution to represent our uncertainty about the true proportion of marked fish in the population. The parameters 'a' and 'b' of the Beta distribution are chosen to reflect our prior beliefs about the proportion. As data is collected through the capture-recapture process, the Beta distribution is updated using Gibbs Sampling to incorporate the observed information and refine our estimation of the proportion of marked fish.
By iteratively applying Gibbs Sampling and updating the Beta distribution, the technique allows us to refine our estimates of population size, capture history, and related parameters, providing a Bayesian framework for capturing uncertainties and making robust inferences about the sunfish population size based on the available data.




Illustration with a Real Example:
* The authors provide an example using the Gordy Lake sunfish data to demonstrate the application of Gibbs sampling for Bayesian estimation.
* Different hierarchical priors are considered for the model parameters, showcasing the sensitivity of posterior characteristics to the choice of prior distributions.
* Posterior means, standard deviations, and credible intervals for population size and model parameters are computed using the Gibbs sampler.
Conclusion:
* The paper concludes by highlighting the importance of Gibbs sampling in overcoming computational challenges in Bayesian capture-recapture estimation.
* Gibbs sampling provides a versatile tool for researchers to explore a wider range of prior distributions and model complexities.
* This method enhances our ability to estimate population sizes accurately, even in situations with limited prior information.
* 




A hierarchical framework, also known as a hierarchical model or hierarchical structure, is a statistical modeling approach that incorporates multiple levels of variability or uncertainty. It's a way of organizing and modeling complex data by assuming that the data are generated from a series of interconnected levels, where each level represents different sources of variability or information. This approach is particularly useful when dealing with data that exhibit hierarchical or nested structures, such as data collected from multiple individuals within different groups, repeated measurements over time, or data with various levels of aggregation.
In a hierarchical framework, you have different levels of parameters, and each level represents a different layer of the data generating process. These levels are connected through prior distributions, which express how information flows between them. The idea is that parameters at a higher level are influenced by parameters at a lower level, capturing dependencies and patterns in the data.






* 		Analytical Intractability: When the likelihood or prior distributions are analytically intractable, Gibbs sampling can provide a way to obtain samples from the joint posterior distribution without requiring explicit closed-form expressions. It breaks down the joint posterior into a sequence of conditional distributions, which might be easier to work with.
* 		Numerical Integration: Gibbs sampling avoids the need for explicit numerical integration. Instead, it involves drawing samples from the conditional distributions, which might be more feasible to compute.

High Dimensionality: Even in high-dimensional spaces, Gibbs sampling can be more efficient because it updates one parameter at a time, reducing the complexity of exploring the entire parameter space simultaneously.

Model Comparison: Gibbs sampling can be used to estimate Bayes factors by simulating samples from different models and comparing their posterior distributions. This enables you to compare models without needing to compute exact evidence
