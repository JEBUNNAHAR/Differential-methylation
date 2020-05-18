# Differential-methylation : Why the bumphunter function chooses only one cluster from my datasets?

Hi everyone,
I am using bumphunter function from minfi package for patients (Healthy donors and treatments ) dataset to find DMRs. Where i design contrasts based on the individual patient's methylation level at different time points and got the table, you could see below.  I don't understand why the bumphunter function chooses only one cluster from my dataset?

If anyone has a suggestion, that will also help me.
Thanks

HD2_0vs22h_0ng <- as.factor( c("HD2.0h.0ng", "HD2.22h.0ng"))

Mm_HD2_0vs22h_0ng <- model.matrix(~HD2_0vs22h_0ng) # The design matrix

Bumps1 <- minfi::bumphunter(NTFlt[ ,c(30,34)], design = Mm_HD2_0vs22h_0ng, cutoff = c(-3,3), cluster= Clus_chr_table, B=100,type="M")

head(bumpsTable1, n=10)

 X   chr     start       end     value     area   cluster indexStart indexEnd L clusterL     p.value fwer p.valueArea fwerArea
1 88 chrX 9433103 9433103 Inf Inf chrX109 580719 580719 1 24 0.003787879 1 0.003787879 1

2 262 chrX 18710913 18710913 -9.960673 9.960673 chrX315 581913 581913 1 24 0.007575758 1 0.007575758 1

3 69 chr6 28832727 28832727 8.684412 8.684412 chr61606 200437 200437 1 80 0.011363636 1 0.011363636 1

4 236 chr7 73039066 73039066 -8.394728 8.394728 chr73120 244901 244901 1 12 0.015151515 1 0.015151515 1

5 44 chr2 233323935 233323935 8.253298 8.253298 chr29629 97745 97745 1 18 0.018939394 1 0.018939394 1

6 80 chr7 87105216 87105216 8.114027 8.114027 chr73692 246992 246992 1 17 0.022727273 1 0.022727273 1

7 136 chr14 23504247 23504247 -7.774084 7.774084 chr14203 415120 415120 1 20 0.026515152 1 0.026515152 1

8 26 chr17 41132655 41132655 7.622053 7.622053 chr173062 493947 493947 1 14 0.030303030 1 0.030303030 1

9 243 chr7 149420655 149420655 -7.207667 7.207667 chr76407 258182 258182 1 19 0.034090909 1 0.034090909 1

10 180 chr22 21305099 21305099 -7.159384 7.159384 chr22362 569434 569434 1 3 0.037878788 1 0.037878788 1

