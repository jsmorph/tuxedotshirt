# <img src="https://github.com/jsmorph/tuxedotshirt/blob/main/doc/shirt.png?raw=true" width="40"> `tuxedotshirt.co`

# Summary

Provide an API that completes (verified) proofs.

More specifically: provide an API that returns statements that formally prove 
a given statement and hypotheses using a proof assistant like [Lean 4](https://github.com/leanprover/lean4) or [Coq](https://coq.inria.fr/).

# Description

The service is an assistant for the proof assistant [Lean 4](https://github.com/leanprover/lean4) and possibly [Coq](https://coq.inria.fr/).  This service is mostly provided via APIs.

Lean 4 and Coq are programming languages and [proof assistants](https://en.wikipedia.org/wiki/Proof_assistant).  A user of these systems
can prove statements using a wide range of [tactics](https://coq.inria.fr/refman/proof-engine/tactics.html), and
these proofs are verified by the system.  Since Lean 4 and Coq are programming languages, these systems can be used to prove
statements about program correctness and other behavior. Coq in particular has been used to verify serious, production-grade [software](https://en.wikipedia.org/wiki/CompCert), and both systems are also used for [serious](https://xenaproject.wordpress.com/2020/12/05/liquid-tensor-experiment/) [math](https://github.com/leanprover-community/mathlib4).  [Here's an example](https://github.com/leanprover-community/mathlib4/blob/master/Mathlib/LinearAlgebra/Matrix/Nondegenerate.lean#L49-L67) statement and its proof in Lean 4.

The proposed service attempts to provide proofs of statements expressed and verified by these proof assistants.  **The focus is on proving routine, day-to-day statements (lemmas, routine goals, subgoals) to reduce some of the tedium in constructing larger, non-trivial proofs.**  This sort of task is similar in spirit to automating software boilerplate and glue code.  Generating breakthrough mathematics is _not_ a (current) goal.

Training effective models will presumably be challenging. Existing corpora are relatively small, and he data itself is of course relatively abstract.  Lots of pronouns in spirit.  However, we've seen excellent results from code-trained models.  The data is high quality (actually verified), and it might be possible to generate additional high quality data (perhaps requiring major computational resources).

Note that the available data is typically licensed [conveniently](https://github.com/leanprover-community/mathlib4/blob/master/LICENSE).

Though completing proofs is the primary goal here, eventually this service could provide a range of capabilities like:

1. Formalizing statements (natural language text to format statements)
2. Unformalizing statements (natural language descriptions of formal statements)
3. LaTeX to statement and statement to LaTeX
4. Informal proofs to formal proofs and the other direction

To be clear, we will likely _not_ pursue any of those additional capabilities initially.
   
# Work breakdown

1. Obtain and extend corpora
2. Train tokenizers (maybe)
3. Contemplate models
4. Train models
5. Fine-tune models
6. Consider augmented retrieval using a proof database indexed with embeddings
7. Prompting
8. Evaluate (test)
9. Define and implement APIs (including feedback)
10. Operate

# Founder background

I've been building and operating software for a long time.  Recently I was the creator of a state-machine-based event processor with  pattern matching that's been in large-scale production for several years.  Most of my projects relate to data engineering, analytics, data modeling and knowledge representation, and ML.  My academic background is math and philosophy.
   
# References


## Papers
6. Gunasekar, et al., 2023, ["Textbooks Are All You Need"](https://arxiv.org/abs/2306.11644)
7. Han, et al., 2021, ["Proof Artifact Co-training for Theorem Proving with Language Models"](https://arxiv.org/abs/2102.06203)
8. Jiang, et al., 2023, ["Guiding Formal Theorem Provers with Informal Proofs"](https://arxiv.org/pdf/2210.12283.pdf)
9. Polu, et al., 2022, ["Formal Mathematics Statement Curriculum Learning"](https://arxiv.org/pdf/2202.01344)
10. Yang, et al., 2019, ["(CogGym) Learning to Prove Theorems via Interacting with Proof Assistants"](https://arxiv.org/abs/1905.09381)
9. Yang, et al., 2023, ["LeanDojo: Theorem Proving with Retrieval-Augmented Language Models"](https://arxiv.org/abs//2306.15626)

## Misc 
1. [Wikipedia: Proof assistant](https://en.wikipedia.org/wiki/Proof_assistant)
1. [Lean 4](https://github.com/leanprover/lean4) proof assistant
2. [Coq](https://coq.inria.fr/) proof assistant
3. [`mathlib4`](https://github.com/leanprover-community/mathlib4)
4. [Alectryon](https://github.com/cpitclaudel/alectryon)
5. Verified software
    1. [Software Foundations](https://softwarefoundations.cis.upenn.edu/)
    2. [Verified Software Toolchain](https://vst.cs.princeton.edu/)
    3. [Verifiable C](https://softwarefoundations.cis.upenn.edu/current/vc-current/Verif_sumarray.html)
    4. [Introduction to the Coq proof-assistant for practical software verification](https://www.lri.fr/~paulin/LASER/course-notes.pdf)
11. [AI to Assist Mathematical Reasoning: A Workshop](https://www.nationalacademies.org/event/06-12-2023/ai-to-assist-mathematical-reasoning-a-workshop), National Academies, 2023
12. Naughton, Jr., 2006, ["I want to be formal, but I'm here to party"](https://youtu.be/XW9_V9O3L1A)

