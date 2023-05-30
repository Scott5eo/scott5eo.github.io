## 정의  
푸리에 급수 Fourier Series를 이용해 주기적 함수(신호) $f(t)$를 Complex Exponential의 급수로 정의할 수 있었다.
$$f(t)=\sum_{n=-\infty}^\infty c_n e^{jnw_nt}
$$
이 때, 주기가 $T=2L$인 함수 $f(x)$에 대해서 $c_n$의 값은 아래와 같이 계산할 수 있었다.
$$c_n = \frac{1}{2L} \int_{-L}^L f(x)e^{-jw_nt} dt$$
푸리에 급수에서 Fourier Series Coefficient는 Basis Signal의 크기를 의미한다고 볼 수 있다. 이 때, L의 크기를 매우 크게, $\infty$로 보내면 급수는 discete한 frequency의 basis signal의 합이 아니라 continuous한 frequency의 합이 된다. 자세한 유도공식은 생략하고 아래와 같이 정리할 수 있다.
$$f(t)= \frac{1}{2\pi} \int_{-\infty}^\infty(\int_{-\infty}^{\infty}f(x)e^{-jwt}dt)e^{jwt}jw$$

괄호의 있는 적분식을 $\hat{f}$ 으로 표현하고 이를 $f$의 Fourier Transformation이라 칭한다.

Fourier Transform $\mathcal{F}(f)$:
$$\mathcal{F}(f)=\hat{f}(jw)=\int_{-\infty}^\infty f(t)e^{-jwt}dt$$

Inverse Fourier Transform $\mathcal{F}^{-1}(\mathcal{F}(f))$ :
$$\mathcal{F}^{-1}(\mathcal{F}(f)) = f(t)=\frac{1}{2\pi} \int_{-\infty}^\infty(\hat{f})e^{jwt} dw$$

## 해석
그럼 신호 $x(t)$에 대해 Fourier Transform한 결과의 의미는 무엇일까?

정의에서 보았듯이 푸리에 변환은 푸리에 급수에서 계수항과 관계가 있다. 즉, 신호 $x(t)$를 만드는 모든 continuous한 주파수 신호들의 크기에 대한 continuous한 함수라고 이해해 볼 수 있다. 아래 그림을 참고하면 어떻게 한 신호가 다른 frequency를 가지는 신호들의 합이 되는지 볼 수 있다.
<img src="https://www.nti-audio.com/portals/0/pic/news/FFT-Time-Frequency-View-540.png">
[source](https://www.nti-audio.com/en/support/know-how/fast-fourier-transform-fft)

그럼으로 time domain의 있는 신호 $x(t)$를 frequency domain에서 $X(f)=X(jw)$로 해석하는 것이다.

## 성질

푸리에 변환은 여러가지의 유용한 성질을 가지고 있다.
### 1. Linearity
$$ax(t)+by(t)\Leftrightarrow aX(f) + bY(f)$$

### 2. Scale Change
$$x(at) \Leftrightarrow \frac{1}{|a|}X(\frac{f}{a})$$
### 3. Time Reversal
$$x(-t) \Leftrightarrow X(-f)$$
### 4. Complex conjugation
$$x^\ast(t) \Leftrightarrow X^\ast(-f)$$
### 5. Duality
$$x(t) \Leftrightarrow X(f)$$
$$X(t) \Leftrightarrow x(-f)$$
### 6. Time Shift
$$x(t-t_0) \Leftrightarrow X(f)e^{-j2\pi ft_0}$$
### 7. Frequency Translation
$$x(t)e^{j2\pi f_0 t} \Leftrightarrow X(f-f_0)$$
### 8. Modulation
$$x(t)cos(2\pi f_0 t) \Leftrightarrow \frac{1}{2}X(f-f_0)+\frac{1}{2}X(f+f_0)$$
### 9. Time Differentiation
