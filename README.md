This repo contains the book crossing data and the script to preprocessing it.

The original book crossing dataset has 271,379 books, 278,858 users and 1,149,780 ratings. However, we only collect the book content of 36,528 books. Some of the books are written in languages other than English (e.g., German and French).

When we preprocess the dataset, we only keep the English books with content, which results in 34,448 books. We only keep the users who read at least three books so that we can create a validation dataset and testing dataset for each user. This results in 21,891 users.

After all of these filterings, we get 34,448 books, 21,891 users and 570,652 ratings.

We split the filtered dataset into a training set, validation set and testing set. Each of them has 526,870, 21,891, 21,891 ratings, respectively. In the validation and testing set, each user has a book.

The preprocessed data is stored in 6 files:
* bx_book_map.pkl: mapping between book ISBN and book index in the book feature matrices.
* bx_user_map.pkl: mapping between the original user Id and user index.
* bx_eval.pkl: the evaluation set (a tuple of validation set and testing set)
* bx_neg.pkl: the negative samples for validation and testing.
* bx_train.pkl: the training set.
* bx_book_abstract.pkl.gz: the Bert embedding of book abstracts.
* bx_book_title.pkl.gz: the Bert embedding of book titles.
