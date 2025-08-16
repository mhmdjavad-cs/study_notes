

apply: برای شرطی و فور آل استفاده میشه، دیگه خودت بلدی

---

symmetry: تساوی رو می چرخونه. بعضی جاها لازم میشه

----

transitivity
برای اثبات جاهایی که به ترنسینیویتی نیاز داری استفاده میشه.
Example trans_eq_example'' : forall (a b c d e f : nat),
     [a;b] = [c;d] ->
     [c;d] = [e;f] ->
     [a;b] = [e;f].
Proof.
  intros a b c d e f eq1 eq2.
  transitivity [c;d].
  apply eq1. apply eq2.   Qed.


---

injection
برای وقتی که توی تایپ استقراییت یه کانستراکتور داری، مشخصه که همه‌ی این 
کانستراکتورا یک به یک هستن. از این فکت میتونی توی اثباتت استفاده کنی:

Theorem S_injective' : forall (n m : nat),
  S n = S m ->
  n = m.
Proof.
  intros n m H.

(** By writing [injection H as Hmn] at this point, we are asking Coq
    to generate all equations that it can infer from [H] using the
    injectivity of constructors (in the present example, the equation
    [n = m]). Each such equation is added as a hypothesis (called
    [Hmn] in this case) into the context. *)
  injection H as Hnm. apply Hnm.
Qed.

---

discriminate
وقتی دوتا کانستراکتور از یه تایپ استقرایی که با هم فرق دارن، برابر هم قرار داده شدن
این یه تناقضه، و از همین میشه نتیجه گرفت که حکم درسته و تمام. این تاکتیک برای این استفاده میشه.

Theorem discriminate_ex1 : forall (n m : nat),
  false = true ->
  n = m.
Proof.
  intros n m contra. discriminate contra. Qed.

---

f_equal

همون injection عه ولی برای هر تابع دلخواهی میتونی استفادش کنی. روش استفاده اینطوریه که می‌نویسی:
apply f_equal
ولی یه تاکتیک هم به همین اسم هست. پس کافیه خالی خالی بنویسی f_equal

---

specialize
وقتی توی یکی از فرض هات، یه forall داری، میتونی اون forall رو خاصش کنی.
برای یه عنصر خاص در نظر بگیری. اینجاست که از تاکتیک specialize استفاده میشه.
نحوه‌ی کار به شکل زیره:

Theorem specialize_example: forall n,
     (forall m, m*n = 0)
  -> n = 0.
Proof.
  intros n H.
  specialize H with (m := 1).
  simpl in H.
  rewrite add_comm in H.
  simpl in H.
  apply H. Qed.

---

  generalize dependent n.

برای این که یه چیزی که معرفی کردی رو دوباره برگردونی بالا برای استقرا.

---

  destruct (n =? 3) eqn:E1.

یادت باشه دیستراکت این مدلی خیلی خیلی بدرد بخوره.

---




