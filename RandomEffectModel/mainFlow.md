# Definition 

데이터의 모델링에 대해서 먼저 생각해보면 모델링은 이러이러 모양으로 데이터의 요인들이 서로 영향을 줄것이다. 
라고 생각한 모델을 의미하며 주로 방정식으로 표현한다.  

모델을 표현한 방정식에 
랜덤효과모델에 대해서 알려면 먼저 고정효과에 대해 알아야 한다. 

$Y_{ij}$ 를 $i$라는 처리를 한 sample들의 j번째 관찰값이라고하면    

고정효과 모델에서는    
$Y_{ij} = c+\alpha_i + e_{ij}$  
라고 모델을 쓸수 있다. 식을 생각해보면   
먼저 전체적인 평균 $c$ 값이 존재하고   
거기에 $i$라는 처리에 따라 달라지는 $\alpha_i$ 이라는 고정효과와  
 random noise로 생각 할 수 있는 $e_{ij}$  이 추가 되어 관찰값으로 관측 되는 것이다.   
이때 $\alpha_i$은 상수로써 
위의 model이 고정효과 모델이다. 

> 이제 random effect model 이전에 다음과같은 Centralize technique를 짚고 넘어가자   
처리가 1,2 두개가 있다고하면 $Y_{1j} = c+\alpha_1 + e_{1j}$ 와 $Y_{2j} = c+\alpha_2 + e_{2j}$ 두개가 있다고하고 $c=3$ 이라고 하고 $\alpha_1=1 , \alpha_2=-1$ 이라고 하자  이떄 이러한 Model은 다음과 완전히 동치이다 $c=0 , \alpha_1=4,\alpha_2=2$ 같은 model에 parameter가 이것도 되고 저것도 될수 있다는 것은 좀 부자연스럽다. 이러한 점이 생기는 이유는 아무런 parameter들에 제약조건이 없기 때문에 $c+\alpha_1=\alpha_1$으로 생각해도 되기 때문이다.   
따라서 그냥 $c$가 없는 model : $Y_{1j} = \alpha_1 + e_{1j}$ 와 $Y_{2j} =\alpha_2 + e_{2j}$ 에서 $Y_{1j} = 4+ e_{1j}$ , $Y_{2j} = 2 + e_{2j}$ 이라고 해도된다. 평균 $c$값이 필요없는것이다. 그러나 효과들을 평균값을 일부러 상수로 빼서 $c=3$으로 빼고 $\sum_i\alpha_i=0$으로 Centralize하는 technique이 존재한다. 그리고 이러한 방법은 필수적인것은 아니지만 효과들의 상수 값은 차이만 중요하다는 걸로 인식해도된다. 상수차이는 어떻게든 뺄수있다는 것이다. 



random effect model은 fixed effect model에 $\alpha_i$들이 상수가 아니라는 가정을 한다.     
예를들면 $\alpha_i$~$N(c_i,\sigma_i)$ 라는 것이다.    
이러한 모델이 나오는 것은 당연하다 예를들어 어떤 약물 A,B라는 효과가 있다고 했을때 약물의 효과가 A든 B든 사람이 누구냐에 따라 고정된 효과를 준다는것은 현실적이지 않고 사람에 따라 어느정도 효과가 다르게 나온다고 생각하는게 합리적이다.   
이때 $\alpha_i$~$N(c_i,\sigma_i)$은 $\alpha_i+c_i$~$N(0,\sigma_i)+c_i$ 으로 생각할수 있고 (위에서 언급한대로 상수는 뺄수있고) 그래서 random effect model에서는 분산을 중요하게 여기며   
$Y_{ij}=\alpha_i+c_i+e_{ij}$에서 $\alpha_i$~$N(0,\sigma_i)$ $e_{ij}$~$N(0,\sigma)$ 인 모델로 바꾸면 random effect인 $\alpha_i$과 fixed effect인 $c_i$의 혼합모델인 mixed effect model로 변환될수있다. 


