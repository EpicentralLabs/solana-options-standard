
# Solana Options Standard

An open source software/program development kit (SDK). Inside of the SDK, there are a few things that will be built and optimized over a course of time. More detailed documentation and descriptions written in [docs.epicentrallabs.com](https://docs.epicentrallabs.com/option-standard-sdk/introduction).

# Black Scholes Model Formula:

[*Reference/Citation(s) - Wikipedia: Black Scholes Model*](https://en.wikipedia.org/wiki/Black%E2%80%93Scholes_model#Notation)

### Call Option

$C(S,t) = N(d_+)S_t - N(d_-)Ke^{-r(T-t)}$

### Put Option

$P(S,t) = N(-d_+)Ke^{-r(T-t)} - N(-d_-)S_t$

--- 

**Where:**

$d_+ = \frac{1}{\sigma\sqrt{T-t}}\left[\ln\left(\frac{S_t}{K}\right) + \left(r + \frac{\sigma^2}{2}\right)(T-t)\right]$

$d_- = d_+ - \sigma\sqrt{T-t}$

> Above is the two standardized normal variables used in the Black-Scholes formula.

## Notation:

### **Market Related:**

$S$ = Current price of the underlying token/asset.

$σ$ = Volatility of the underlying token/asset.

$t$ = is a time in years; with $t = 0$ generally representing the present year.

$r$ = is the annualized "risk-free" interest rate, continuously compounded (APY).

### **Option Related:**

$V(S,t)$ = is the current option price based on the asset price and time.

$C(S,t)$ = is the call option price and $P(S,t)$ is the put option price.

$T$ = is when the option expires.

$\tau$ = is time left until expiry ($T - t$).

$K$ = is the strike price (agreed price to buy/sell).

$e$ = [Euler's number](https://en.wikipedia.org/wiki/E_(mathematical_constant)) (≈ 2.718281823) a mathematical constant and is the base of the natural logarithm.

$ln$ = is the natural logarithm.

$N(x)$ = denotes the [standard normal](https://en.wikipedia.org/wiki/Normal_distribution#Standard_normal_distribution) [cumulative distribution function (CDF)](https://en.wikipedia.org/wiki/Cumulative_distribution_function):

$N(x) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{x} e^{-z^2/2} dz.$

# Greeks

[*Reference/Citation(s) - Wikipedia: Option Greeks*](https://en.wikipedia.org/wiki/en:Greeks_(finance)?variant=zh-tw)

The Greeks serve as essential metrics for managing risk in options trading. They help traders understand how their portfolio value changes when specific market factors fluctuate. By analyzing each Greek independently, traders can assess individual risk components and adjust their positions to maintain their target risk profile.

## Delta

Delta shows how much the option value changes when the underlying asset price changes. It represents the number of tokens needed to hedge the option.

$\Delta = \frac{\partial V}{\partial S}$

## Theta

Theta shows how much value an option loses as time passes. It represents the daily decay in option value as it gets closer to expiration.

$\Theta = -\frac{\partial V}{\partial \tau}$

## Vega 

Vega shows how much the option value changes when volatility changes. It measures the impact of a 1% change in volatility.

$\nu = \frac{\partial V}{\partial \sigma}$

## Gamma

Gamma shows how fast delta changes when the asset price moves. It helps measure how stable an option position is.

$\Gamma = \frac{\partial \Delta}{\partial S} = \frac{\partial^2 V}{\partial S^2}$\

## Rho

Rho shows how much the option value changes when interest rates change. It measures the impact of a 1% change in rates.

$\rho = \frac{\partial V}{\partial r}$