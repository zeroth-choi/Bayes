# Bayes' theorem

## 조건부 확률
$P(B|A)=\frac{P(A\cap B)}{P(A)}$, (단, $P(A)\neq 0$)  
$P(A|B)=\frac{P(A\cap B)}{P(B)}$, (단, $P(B)\neq 0$)  
그러므로  
$P(A\cap B)=P(B|A)P(A)=P(A|B)P(B)$  

## Bayes 정리  
$P(A|B)$에 대해 풀면 Bayes 정리   
$$P(A|B)=\frac{P(B|A)}{P(B)}P(A), \quad (단, P(A)\neq 0, P(B)\neq 0)$$  

> $P(A)$ : 사전 확률(prior probability)  
$P(A|B)$ : 사후 확률(posterior probability)  

분모가 $P(B)=P(A\cap B)+P(A^{\textrm{C}}\cap B)=P(B|A)P(A)+P(B|A^{\textrm{C}})P(A^{\textrm{C}})$이므로  
$$P(A|B)=\frac{P(B|A)}{P(B|A)P(A)+P(B|A^{\textrm{C}})P(A^{\textrm{C}})}P(A), \quad (단, P(A)\neq 0, P(A^{\textrm{C}})\neq 0, P(B)\neq 0)$$  

$A$를 $A^{\textrm{C}}$로 바꾸어 얻어지는  
$P(A^{\textrm{C}}|B)=\frac{P(B|A^{\textrm{C}})}{P(B)}P(A^{\textrm{C}})$에서  
$P(A^{\textrm{C}}|B)=1-P(A|B)$, $P(A^{\textrm{C}})=1-P(A)$이므로  
$1-P(A|B)=\frac{P(B|A^{\textrm{C}})}{P(B)}(1-P(A))$  
두 식의 비를 구하면  
$\frac{P(A|B)}{1-P(A|B)}=\frac{P(B|A)}{P(B|A^{\textrm{C}})}\frac{P(A)}{1-P(A)}$  
승산(odds) $O(A)\equiv \frac{P(A)}{1-P(A)}=\frac{P(A)}{P(A^{\textrm{C}})}$을 정의하면 Turing 형태의 Bayes 정리   
$$O(A|B)=\Lambda(A|B)O(A), \quad (단, P(A)\neq 0, P(A^{\textrm{C}})\neq 0, P(B)\neq 0, P(B|A^{\textrm{C}})\neq 0)$$  
> $\Lambda(A|B) \equiv P(B|A)/P(B|A^{\textrm{C}})$ : Bayes 인자
 
$A$, $A^{\textrm{C}}$를 $A_1$,...,$A_n$으로 일반화하면 (단, $A_i\cap A_j\neq 0 (i\neq j)$, $A_1\cup\cdots\cup A_n=U$) 확장형  
$$P(A_k|B)=\frac{P(B|A_k)}{P(B|A_1)P(A_1)+\cdots+P(B|A_n)P(A_n)}P(A_k), \quad (단, P(A_i)\neq 0, P(B)\neq 0)$$  
