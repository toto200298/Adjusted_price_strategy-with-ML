## Objective  <a name="objective"></a>

A pricing model should be built that predicts the optimal price for
each car to maximize profits while maintaining a high likelihood of closing sales.

## Proposed solution <a name="proposed_solution">

### Adjusted Price Strategy <a name="adjusted_strategy">

An adjusted pricing strategy is a dynamic approach to setting the advertised price of products or services, which considers various factors such as market conditions, competitor strategies, customer preferences, and economic indicators.  

The primary objective is twofold: to boost profitability and market share by establishing prices that are perceived as fair and competitive, while aligning with the company's goals. This strategy entails continuously adapting prices based on the probability of making a sale, aiming to strike a delicate balance between maximizing revenue and ensuring a favorable likelihood of transaction completion.

Advantages of the Adjusted Price Strategy:
- **Maximized Profits**: By pricing products slightly above market value, the strategy enables the dealership to capture additional value on each sale.
- **High Likelihood of Selling**: Adjusting prices based on the probability of selling ensures that products remain appealing to potential buyers, resulting in increased sales volume.
- **Competitive Advantage**: Adjusted prices strike a balance between profitability and competitiveness, providing the dealership with an advantageous position in the market.
- **Adaptability**: The strategy is flexible and adaptable to changing market dynamics and customer preferences, allowing for responsive pricing decisions.

**Steps for the implementation of the Adjusted Price Strategy:**

1. **Predictive Model Selection**:
   - The strategy begins with the selection of an appropriate predictive model,which can capture complex relationships
between car features and prices. 

2. **Market Value Consideration**:
   - Before adjusting the predicted price, the model takes into account the market value of the car. The market value serves as a benchmark against which the predicted price is compared.

3. **Calculation of Overcharge Ratio**:
   - The overcharge ratio is calculated by dividing the predicted price by the market value and subtracting 1. This ratio indicates how much the predicted price exceeds the market value, if at all.
   
   $$overcharge \: = \frac{predicted \: price}{market \: value} - 1 $$
   
4. **Probability of Selling**:
   - The overcharge ratio is then used to calculate the probability of selling the car. This probability represents the likelihood that the car will be sold at the predicted price, considering the extent to which it exceeds  the market value.   - The probability of selling is calculated as the difference between 1 and the minimum of 1 and the overcharge ratio. 
   
   $$P(predicted \: price |market \: value) = 1 - min(1, overcharge \: ratio) $$
   

5. **Adjustment Based on Probability Threshold**:
   - Next, the strategy defines a probability threshold, representing the minimum acceptable probability of selling. This threshold is set based on business objectives and market dynamics.
   - If the overcharge ratio is positive (indicating the predicted price is higher than the market value) and the probability of selling exceeds the threshold, the price is adjusted.
   - The adjusted price is calculated by multiplying the predicted price by the probability of selling. This adjustment ensures that the price remains attractive enough to maintain a high likelihood of selling while still maximizing profitability.
   
   $$Adjusted \: price = Predicted \: price \times P(predicted \: price | market \: value) $$


