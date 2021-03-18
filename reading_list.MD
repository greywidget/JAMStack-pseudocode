# Reading List

## Task
- Keep track of which books you read and which books you want to read!
- Create an array of objects, where each object describes a book and has properties for the title (a string), author (a string), and already read (a boolean indicating if you have read it yet).
- Iterate through the array of books. For each book, log the book title and book author like so: *"The Hobbit by J.R.R. Tolkien"*.
- Now use an `if/else` statement to change the output depending on whether you have read it yet or not. If you have read it, log a string like *'You already read "The Hobbit" by J.R.R. Tolkien'*, and if not, log a string like *'You still need to read "The Lord of the Rings" by J.R.R. Tolkien'*.

## Pseudocode
```
FUNCTION list_books(book_array)
    FOR EACH book in book_array
        PRINT(book.Title, ' by ', book.Author)
        PRINT(newline)
```


```
FUNCTION list_books_with_status(book_array)
    FOR EACH book in book_array
        IF book.Read == TRUE
            status = 'You already read '
        ELSE
            status = 'You still need to read '

        PRINT(status, book.Title, ' by ', book.Author)
        PRINT(newline)
```

## Python Solution
```
from collections import namedtuple

book = namedtuple('book', 'title author read')

book1 = book('The Hobbit', 'J.R.R Tolkien', True)
book2 = book('The Lord of the Rings', 'J.R.R Tolkien', False)
book3 = book('Lord of the Flies', 'William Golding', True)

books = [book1, book2, book3]

def list_books(books):
    for book in books:
        print(book.title, 'by', book.author)

def list_books_with_status(books):
    for book in books:
        status = 'You already read' if book.read else 'You still need to read'
        print(f'{status} "{book.title}" by {book.author}')

list_books(books)
print()
list_books_with_status(books)
```

## Output
```
>>> The Hobbit by J.R.R Tolkien
>>> The Lord of the Rings by J.R.R Tolkien
>>> Lord of the Flies by William Golding

>>> You already read "The Hobbit" by J.R.R Tolkien
>>> You still need to read "The Lord of the Rings" by J.R.R Tolkien
>>> You already read "Lord of the Flies" by William Golding
```