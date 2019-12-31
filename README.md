## Womens Clothing E Commerce Reviews - Sentiment Training

### DataSet
  * The dataset I chose consisted of 11 columns that provided information about individual reviews of clothing purchased online. These columns included some useful information like age, type of clothing, department name etc, but for the purposes of this sentiment training I chose to condense the data to  ```Review Text``` and ```Rating```
  * Each```Rating``` is an integer between 1 and 5, with 5 being the most positive. The ```Review Text``` consists of personalized reviews from each patron, discussing in detail why they did or did not like the product, making it ideal for sentiment training. That said if this were to be used outside of a commerce setting, you'd have to keep in mind how the context of words like 'tight', 'big' or 'small' can convey negative sentiment when discussing clothing.

  ### Preprocessing
   * To begin, I reshape my data down to review text and rating, giving me just under 23500 rows over 2 columns
   * With the ratings being numbers between 0 and 5, it seemed most logical, at least to start, to apply sentiment as follows:
    A rating of 4 or 5 = 2
    A rating of 3 = 1
    A rating of 2 or 1 = 0
    I use this logic in a helper function and create a new column for sentiment by applying the function to the Rating column
  * Then, I seperate the data into training columns and call the appropritate tokenizer methods to create my 2d array