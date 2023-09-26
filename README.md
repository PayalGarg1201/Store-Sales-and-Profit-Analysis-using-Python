# Store-Sales-and-Profit-Analysis-using-Python
Store Sales and Profit Analysis using Python

Problem Statement : 

To find some Business Insights to improve  store sales and profit. With growing demands and cut-throat competitions in the market, a Superstore Giant is seeking your knowledge in understanding what works best for them. They would like to understand which products, regions, categories and customer segments they should target or avoid.

Dataset is taken form Kaggle https://www.kaggle.com/datasets/vivek468/superstore-dataset-final.
 
Store sales and profit analysis is the task of analyzing the performance of a retail store in terms of its sales and profits. It helps businesses identify areas for improvement and make data-driven decisions to optimize their operations, pricing, marketing, and inventory management strategies to drive revenue and growth. 

<img width="664" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/34175d76-d8af-4bfb-8dec-97dac1e7827e">


  
  
  <img width="524" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/8eef5243-1d09-4b9b-822e-d582d74277fe">




  

Let's look at descriptive statistics


<img width="605" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/07155d2b-cceb-437f-a9b0-4d61bab0c440">




The dataset has an order date column. We can use this column to create new columns like order month, order year, and order day, which will be very valuable for sales and profit analysis according to time periods.


<img width="666" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/4109e492-ec2a-421c-bfe0-3325db549d05">





<img width="640" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/c0f774f7-c269-4f19-aa47-5234a77ecdec">




<img width="676" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/60bc3249-2ab5-4a56-96a2-c426aa5eff41">




<img width="658" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/8f5d4b8d-844c-4a5e-a19d-dc7034737ca0">





Sales by Sub category : 


<img width="666" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/207eb22a-e53f-4a9a-862a-22cc8abc16ea">





<img width="647" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/38edf55e-d26c-4195-a0f1-778b5d92bbd1">





Monthly profit 

<img width="677" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/f02f6965-2a80-442b-9153-8562e94a4a3c">





<img width="636" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/e059b3cc-fedb-4329-b862-1089569696af">





Profit by category 

<img width="662" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/12e2fb3a-f737-4345-8da7-58a9a7209b15">





Profit by Subcategory

<img width="660" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/44484c49-04c0-47d1-a561-8676d53d1b15">





<img width="640" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/09da424f-9ce4-4be4-89bc-dec46a32ab15">





sales and profit analysis by customer segments:

sales_profit_by_segment = data.groupby('Segment').agg({'Sales': 'sum', 'Profit': 'sum'}).reset_index()

color_palette = colors.qualitative.Pastel

fig = go.Figure()
fig.add_trace(go.Bar(x=sales_profit_by_segment['Segment'], 
                     y=sales_profit_by_segment['Sales'], 
                     name='Sales',
                     marker_color=color_palette[0]))
fig.add_trace(go.Bar(x=sales_profit_by_segment['Segment'], 
                     y=sales_profit_by_segment['Profit'], 
                     name='Profit',
                     marker_color=color_palette[1]))

fig.update_layout(title='Sales and Profit Analysis by Customer Segment',
                  xaxis_title='Customer Segment', yaxis_title='Amount')

fig.show()





![image](https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/2bc5d79b-7a29-4958-981b-77864396a8d3)



 
Validate the findings:




sales_profit_by_segment = data.groupby('Segment').agg({'Sales': 'sum', 'Profit': 'sum'}).reset_index()
sales_profit_by_segment['Sales_to_Profit_Ratio'] = sales_profit_by_segment['Sales'] / sales_profit_by_segment['Profit']
print(sales_profit_by_segment[['Segment', 'Sales_to_Profit_Ratio']])




<img width="482" alt="image" src="https://github.com/PayalGarg1201/Store-Sales-and-Profit-Analysis-using-Python/assets/133757186/3eff6381-eba9-44f8-ad37-8c4109190ee0">







Summary

Based on my finding the store has higher profits from the product sales for consumers, but the profit from corporate product sales is better in the sales-to-profit ratio.


























  








