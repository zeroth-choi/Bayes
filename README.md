# Bayes 정리

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

## 승산 형태의 Bayes 정리  
$A$를 $A^{\textrm{C}}$로 바꾸어 얻어지는  
$P(A^{\textrm{C}}|B)=\frac{P(B|A^{\textrm{C}})}{P(B)}P(A^{\textrm{C}})$에서  
$P(A^{\textrm{C}}|B)=1-P(A|B)$, $P(A^{\textrm{C}})=1-P(A)$이므로  
$1-P(A|B)=\frac{P(B|A^{\textrm{C}})}{P(B)}(1-P(A))$  
두 식의 비를 구하면  
$\frac{P(A|B)}{1-P(A|B)}=\frac{P(B|A)}{P(B|A^{\textrm{C}})}\frac{P(A)}{1-P(A)}$  
승산(odds) $O(A)\equiv \frac{P(A)}{1-P(A)}=\frac{P(A)}{P(A^{\textrm{C}})}$을 정의하면 승산 형태의 Bayes 정리   
$$O(A|B)=\Lambda(A|B)O(A), \quad (단, P(A)\neq 0, P(A^{\textrm{C}})\neq 0, P(B)\neq 0, P(B|A^{\textrm{C}})\neq 0)$$  
> $\Lambda(A|B) \equiv P(B|A)/P(B|A^{\textrm{C}})$ : Bayes 인자. 유병률에 무관
 
## 확장형 Bayes 정리  
$A$, $A^{\textrm{C}}$를 $A_1$,...,$A_n$으로 일반화하면 (단, $A_i\cap A_j\neq 0 (i\neq j)$, $A_1\cup\cdots\cup A_n=U$), 확장형 Bayes 정리  
$$P(A_i|B)=\frac{P(B|A_i)}{P(B|A_1)P(A_1)+\cdots+P(B|A_n)P(A_n)}P(A_i), \quad (단, P(A_k)\neq 0, P(B)\neq 0)$$  
비를 구하면, 승산 형태의 확장형 Bayes 정리  
$$\frac{P(A_i|B)}{P(A_j|B)}=\frac{P(B|A_i)}{P(B|A_j)}\frac{P(A_i)}{P(A_j)}, \quad (단, P(A_k)\neq 0, P(B)\neq 0)$$  

## 예    

.    | $B$ (검사결과 양성) | $B^{\textrm{C}}$ (검사결과 음성)   
:---:|:---:|:---:   
$A$ (감염) | 참양성  | 거짓음성   
$A^{\textrm{C}}$ (미감염) | 거짓양성  | 참음성   

검사 대상: 1000명  
유병률 $P(A)$ : 2%  
민감도(sensitivity, 참양성률, true positive rate) $P(B|A)$ : 80%   
특이도(specificity, 참음성률, true negative rate) $P(B^{\textrm{C}}|A^{\textrm{C}})$ : 95%     

.    | $B$ (검사결과 양성) | $B^{\textrm{C}}$ (검사결과 음성) | 소계  
:---:|:---:|:---:|:---:   
$A$ (감염) | 16  | 4 | 20  
$A^{\textrm{C}}$ (미감염) | 49  | 931 | 980   
소계 |  65  |  935   |  1000  

$P(A|B)=\frac{P(B|A)}{P(B)}P(A)=\frac{0.8}{65/1000} 0.02=0.246$   
$O(A|B)=\frac{P(B|A)}{P(B|A^{\textrm{C}})}O(A)=\frac{0.8}{1-0.95} \frac{0.02}{1-0.02}=\frac{16}{49}=0.3265$ 
