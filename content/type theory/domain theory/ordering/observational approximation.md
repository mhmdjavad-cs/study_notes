
![[Screenshot 2025-07-09 at 10.51.07 AM.png]]

این یکی میگه هر چیزی که بتونیم درباره‌ی M بگیم رو بتونیم درباره‌ی N هم بگیم. 
نکته‌ی مهم این که از observational approximation میشه applicative approximation رو نتیجه گرفت، ولی برعکس رو جلوتر میگه.

یعنی:
$$
M \lesssim N \; \Rightarrow \; M \sqsubseteq' N 
$$

but also we have from the milner's context lemma:
$$
M \sqsubseteq' N \; \Rightarrow \; M \lesssim N
$$

so at the end we have that $M \sqsubseteq' N$ iff $M \lesssim N$ .


