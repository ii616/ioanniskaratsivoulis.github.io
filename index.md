# Machine Learning algorithms

## Logistic Regression
- Used for binary classification problems
- Implemented on scikit-learn.

Advantages: 
- Straightforward to implement, explain, and computationally inexpensive to train.
- In low dimensional datasets, it is less likely that logistic regression will overfit the data.
- Overfitting in high dimensional datasets can be controlled using L1 and L2 regularisation.
- Performs exceptionally well when the dataset is linearly separable.

Disadvantages: 
- It assumes that the datasets are linearly separable, which is seldom the case in real world data. Thus, cannot solve non-lienar problems.
- Very likely to overfit the data in high dimensional datasets, where the number of features exceeds the number of observations.
- The input variables cannot be correlated between one another. 
- Cannot solve non-linear problems


Assumptions:
- The target variable is binary 
- The features in the dataset are independent from one another.
- There is a linear relationship between the independent and target variables. 

Avoiding overfitting can be done with:
- Regularisation, see [here](https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression).
- With cross-validation. However, be careful to (i) make sure there is not leakage from train to test set and (ii) be careful with time series.

## Random forest
- These are built from decision trees
- DTs are easy to build, use and interpret, but they are very inaccurate.
- Random Forests combine decision trees

### Steps for building the Random Forest
1. Bootstrapping: We take the original dataset, and randomly select samples (instances). We _can_ select the same sample twice.
2. Pick the root node: Create a DT using the bootsrapped dataset, but only consider a subset of (randomly selected) variables/columns, for the **root** node. 
3. At each step of building the DT, use only a **random subset of variables**.
4. Repeat steps 1 to 3. You can build as many trees as you want. 

### Classifying a new sample using the RF
1. Get a new data entry
2. Run it through one Decision Tree and record the output (Yes/no or 1/0). 
3. Repeat for the remaining number of DTs.
4. After we have evaluated the class of the new entry throughout all of the trees in our Random Forest, wee see which class has got the **most votes** and set this as the new entry's class. 

### Evaluation of accuracy

- Usually about 33% of the data does not go into the bootstrapped dataset. We can use this _out of bag_ data to evaluate the performance of the RF.
- We measure accuracy with the proportion of correctly classified out-of-bag samples.



### The hyperparameters are: 
- Number of trees
- Maximum depth of the tree
- Criterion for splitting the nodes
- Minimum and maximum number of features to consider when constructing the trees (to split the nodes). 

For more information see [here](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html).

Advantages: 

Disadvantages: 

Assumptions:

# Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/ii616/ioanniskaratsivoulis.github.io/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ii616/ioanniskaratsivoulis.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
