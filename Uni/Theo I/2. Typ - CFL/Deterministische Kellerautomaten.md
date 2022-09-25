---
tags: uni theo-1 theoretical-cs automata formal-languages
cards-deck: Uni::Courses::Theo-I
complete: true
aliases:
  - Deterministische Kellerautomaten
  - DPDA
  - DCFL
linter-yaml-title-alias: Deterministische Kellerautomaten
date: 2022-09-21
mod-date: 2022-09-23
---

# Deterministische Kellerautomaten

## Definition:
- Definiert durch das *7-Tupel*:
$$M=(Z,\Sigma,\Gamma,\delta,z_0,\#,F)$$
- Entspricht im Groben einen [[Kellerautomat|PDA]], bei dem die *Überführungsfunktion* $\delta$ als $$\forall a\in\Sigma,z\in Z,A\in\Gamma:\quad|\delta(z,a,A)|+|\delta(z,\varepsilon,A)|\leq1$$ definiert ist und der in einem *Endzustand akzeptiert*: $$N(M):=\{x\in\Sigma^*\mid\exists z\in F,V\in\Gamma^*:(z_0,x,\#)\vdash^*(z,\varepsilon,V)\}$$

## Eigenschaften:
- Definiert die Sprachklasse $\text{DCFL}$ als $L\subseteq\Sigma^*:\exists\text{PDA }N(M)\text{ mit }N(M)=L$
- [[Typ-3|REG]] $\subsetneq\text{DCFL}:$ Ein [[3. Typ - REG/Deterministischer Endlicher Automat|DFA]] ist ein DPDA, der seinen Keller nicht nutzt
$$\text{REG}\subsetneq\text{DCFL}\subseteq\text{CFL}$$
	-> Die Menge der unmarkierten Palindrome ist $\in$ [[Typ-2|CFL]]$\setminus\text{DCFL}$
- Die [[../Formale Sprache|Sprache]] der markierte Palindrome $L=\{w\$w^R\mid w\in\Sigma^*\},\$\notin\Sigma,\$\notin w$ liegen in $\text{DCFL}$
- Beschreibt die Klasse der Sprachen, die sich durch [[LR(k) Grammatik]]en erzeugen lassen
	-> Hier existiert scheinbar ein Algorithmus $\in\mathbfcal{O}(n)$