# Iterative Prompt Development for Smart Coffee Maker

In this lesson, you'll iteratively analyze and refine your prompts to generate a product description for a smart coffee maker based on a product fact sheet.

## Product Fact Sheet

**OVERVIEW**
- A state-of-the-art smart coffee maker that brews coffee via smartphone control.
- Compatible with Alexa and Google Assistant for voice-activated brewing.
- Features customizable brew strength and temperature settings.
- Includes a built-in grinder for fresh coffee grounds.
- Eco-friendly with energy-saving mode.
- Perfect for home and office use.

**CONSTRUCTION**
- Made from high-quality stainless steel.
- Easy-to-clean removable parts.

**DIMENSIONS**
- WIDTH: 25 CM | 9.84”
- DEPTH: 30 CM | 11.81”
- HEIGHT: 35 CM | 13.78”
- CAPACITY: 1.5 L | 50.72 oz

**COUNTRY OF ORIGIN**
- Germany

## Initial Prompt
```
prompt = f"""
Your task is to help a marketing team create a 
description for a retail website of a product based 
on a technical fact sheet.

Write a product description based on the information 
provided in the technical specifications delimited by 
triple backticks.

Technical specifications: ```{fact_sheet_coffee_maker}```
"""
response = get_completion(prompt)
print(response)
```

## Issue 1: Description is Too Long

Limit the number of words.
```
prompt = f"""
Your task is to help a marketing team create a 
description for a retail website of a product based 
on a technical fact sheet.

Write a product description based on the information 
provided in the technical specifications delimited by 
triple backticks.

Use at most 50 words.

Technical specifications: ```{fact_sheet_coffee_maker}```
"""
response = get_completion(prompt)
print(response)
```


## Issue 2: Focus on Relevant Details

Request a focus on key features.
```
prompt = f"""
Your task is to help a marketing team create a 
description for a retail website of a product based 
on a technical fact sheet.

Write a product description based on the information 
provided in the technical specifications delimited by 
triple backticks.

The description is intended for coffee enthusiasts, 
so it should highlight features like smart control and 
customization.

Use at most 50 words.

Technical specifications: ```{fact_sheet_coffee_maker}```
"""
response = get_completion(prompt)
print(response)

```

## Issue 3: Include a Table of Dimensions

Ask for a structured table.
```
prompt = f"""
Your task is to help a marketing team create a 
description for a retail website of a product based 
on a technical fact sheet.

Write a product description based on the information 
provided in the technical specifications delimited by 
triple backticks.

The description is intended for coffee enthusiasts, 
so it should highlight features like smart control and 
customization.

At the end of the description, include a table that 
gives the product's dimensions. The table should have 
two columns: one for the dimension name and one for 
the measurements in inches only.

Title the table 'Product Dimensions'.

Format everything as HTML for web use. 
Place the description in a <div> element.

Technical specifications: ```{fact_sheet_coffee_maker}```
"""
response = get_completion(prompt)
print(response)
```


