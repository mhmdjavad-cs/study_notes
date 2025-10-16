
### judgements:

there are four kinds of judgments in martin lof type theory:
1 - A is a Type:
$$
\Gamma \vdash A \; \; Type
$$
2 - A and B are two judgmentally equal types:
$$
\Gamma \vdash A \; \dot{=} \; B  \; \;Type
$$
3 - a is an element of Type A:
$$
\Gamma \vdash a : A
$$
4 - a and b are judgmentally equal elements of Type A:
$$
\Gamma \vdash a \; \dot{=} \; b : A
$$

### dependent types:
when we write:
$$
\Gamma, x:A,\Delta\vdash B(x)\;\;Type
$$
it means that B is a type, dependent on A.

### rules:

#### basic rules:

##### basic types and elements rules:
1 - $$
\frac{\Gamma, x:A \vdash B(x) \;\; Type}{\Gamma \vdash A \;\; Type}
$$
2 - $$
\frac{\Gamma \vdash A \; \dot{=}\; B \;\; Type}{\Gamma \vdash A \;\; Type}
$$
3 - $$
\frac{\Gamma \vdash A \; \dot{=}\; B \;\; Type}{\Gamma \vdash B \;\; Type}
$$
4 - $$
\frac{\Gamma \vdash a : A}{\Gamma \vdash A \;\; Type}
$$
5 - $$
\frac{\Gamma \vdash a \; \dot{=}\; b : A}{\Gamma \vdash a : A}
$$
6 - $$
\frac{\Gamma \vdash a \; \dot{=}\; b : A}{\Gamma \vdash b : A}
$$

##### equality is an equivalence relation:

###### reflexivity:
1 - reflexivity for types:
$$
\frac{\Gamma \vdash A \; Type}{\Gamma \vdash A \; \dot{=} \; A \; Type}
$$
2 - reflexivity for elements: 
$$
\frac{\Gamma \vdash a : A}{\Gamma \vdash a \; \dot{=} \; a \; : A }
$$

###### symmetry:
3 - symmetry for types:
$$
\frac{\Gamma \vdash A \; \dot{=} \; B \;\; Type}{\Gamma \vdash B \; \dot{=} \; A \;\; Type}
$$
4 - symmetry for elements:
$$
\frac{\Gamma \vdash a \; \dot{=} \; b : A}{\Gamma \vdash b \; \dot{=} \; a : A}
$$

###### transitivity:
5 - transitivity for types:
$$
\frac{\Gamma \vdash A \; \dot{=} \; B \;\; Type \quad \quad \Gamma \vdash B \; \dot{=} \; C \;\; Type}{\Gamma \vdash A \; \dot{=} \; C \;\; Type}
$$
6 - transitivity for elements:
$$
\frac{\Gamma \vdash a \; \dot{=} \; b : A \quad \quad \Gamma \vdash b \; \dot{=} \; c : A}{\Gamma \vdash a \; \dot{=} \; c : A}
$$

##### substitution:
1 - substitution for types:
$$
\frac{\Gamma \vdash a \; \dot{=} \; b : A \quad \quad \quad \Gamma,x:A,\Delta \vdash B(x) \;\; Type}{\Gamma,\Delta[x:=a] \vdash B(a) \; \dot{=} \; B(b) \;\; Type}
$$
2 - substitution for elements:
$$
\frac{\Gamma \vdash a \; \dot{=} \; a' : A \quad \quad \quad \Gamma,x:A,\Delta \vdash b(x):B(x)}{\Gamma,\Delta[x:=a] \vdash b(a) \; \dot{=} \; b(a') :B(a)}
$$




oh there is just too many rules here!
