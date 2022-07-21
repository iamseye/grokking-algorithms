# Chapter 10 - K-nearest neighbors


### Classifying oranges vs. grapefruit

- If you are only given the `color` and `size` of a fruit, how do you determine whether it is orange or grapefruit?
    - We can use `k-nearest neighbors` algorithm for classifcation. You can classify by looking at its closest neighbors.
        
        
    - In this example, `color` and `size` are the `features`.

### Calculating distance

- How do we measure the distance between two points? Pythagorus formula.
    - $\sqrt{(x_1-x_2)^2 + (y_1-y_2)^2}$
- The distance formula is flexible: you can have a set of million numbers and still use the same formula to calculate the distance.
    - $\sqrt{(a_1-a_2)^2 + (b_1-b_2)^2 + (c_1-c_2)^2 + (d_1-d_2)^2 ...}$

### Regression

- Regression predicts a number
    - Classification: is it orange or grapefruit? e.g. orange
    - Regression: how many loaves of bread will sell tomorrow? e.g. 100 loaves

### Cosine similarity

- So far we’ve been using the distance formula to compare the distance between two samples, but is this the best formula to use?
    - Suppose two Netflix users are similar, but one of them is more conservative in their ratings. Although the two users have similar taste, they might not be each other’s neighbors.
- `Cosine similarity` solves this problem by comparing the angles of the two vectors, instead of measuring the distance between them.

### Picking good features

- When you’re working with KNN, it’s important to pick the right features to compare against. Picking the right features means:
    - Features that directly correlate to the movies you’re trying to recommend.
    - Features that don’t have a bias (for example, if you ask the users to only rate comedy movies, that doesn’t tell you whether they like action movies).

### Intro to machine learning

- OCR (optical character recognition)
    - A technique to parse text from an image
    - It uses KNN to find the nearest neighbor. Generally speaking, OCR algorithms measure lines, points, and curves.
- Spam filter
    - Spam filter uses an algorithm called the `Naive Bayes classifier`.
    - For example, you get an email with the subject “collect your million dollars now”. Is it spam?
        - You can break the sentence into words and for each word, see what the probability is for that word to show up in a spam email.
        

### Recap

- KNN is used for classification and regression. It involves looking at the k-nearest neighbors.
- Classification: categorization into a group.
- Regression: predicting a response (like a number).
- Feature extraction means converting an item (like a fruit or a user) into a list of numbers that can be compared.
- Picking good features is an important part of a successful KNN algorithm.