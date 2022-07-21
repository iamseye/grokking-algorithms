# Chapter 5 - Hash tables

Suppose you work at a grocery store. When a customer buys an item, you have to look up the price in a book.

- simple search: if book is unsorted, you have to look at every line to find the price (linear)
- binary search: if book is sorted, you could run binary search (log n)
- hash table: if you have a friend who has all the names and prices memorized (constant)

| # of items | Simple search | Binary search | Hash table |
| --- | --- | --- | --- |
| 100 | 100 | 7 | 1 |
| 1,000 | 1,000 | 10 | 1 |
| 10,000 | 10,000 | 14 | 1 |

### Hash function

- A hash function is a function where you put in a string (a sequence of bytes) and you get back a number. It maps strings to numbers.
- Requirements for a hash function:
    - It needs to be consistent. Each input should create the same output every time.
    - It should map different words to different numbers. A hash function is no good if it always returns “1” for any word you put in. In the best case, every different word should map to a different number.

### Hash table

- Hash table uses a hash function to figure out where to store elements. If different items result in the same hash, they will be stored in a linked list. Hash table is essentially a combination of hash function and arrays.
- Also known as hash maps, maps, dictionaries, and associative arrays.
- Hash table is good for:
    - Modeling relationships from one thing to another
    - Filtering out duplicates
    - Caching/memorizing data instead of making your server do the work

### Use cases

- Using hash tables for lookups
    - A phone book where you map people’s names to phone numbers.
    - DNS resolution that maps a web address to an IP address.
- Preventing duplicate entries
- Using hash tables as a cache
    - Websites remember the data instead of recalculating it for certain URLs.
    - All big websites use caching and that data is cached in a hash.

### Collisions

- Collisions happen when more than one key have the same hash.
    - For example, if your hash function assigns a spot in the array alphabetically, “apple” and “avocado” will be assigned to the same “a” spot.
- Hash tables start a linked list if there is a collision.
     

### Average and worst case performance

|  | Hash tables (average) | Hash tables (worst) | Arrays | Linked lists |
| --- | --- | --- | --- | --- |
| Search | O(1) | O(n) | O(1) | O(n) |
| Insert | O(1) | O(n) | O(n) | O(1) |
| Delete | O(1) | O(n) | O(n) | O(1) |
- On average, hash tables are as fast as arrays at searching and as fast as linked lists at insert/delete.
- In the worst case, hash tables are slow at both search and insert/delete.
    - A worst case hash table is when all keys map to one slot.
- To avoid worst case performance, we need to avoid collisions. It can be fixed in two ways:
    - A low load factor
    - A good hash function

### Load factor

- load factor = # of items in hash table / total number of slots
     
- **Resizing** is needed if your load factor is too high.
    - Having a load factor greater than 1 means you have more items than slots in your array. There is no way each item will get its own slot, because there aren’t enough slots. Once the load factor starts to grow, you need to add more slots to your hash table.
    - The rule of thumb is to make an array that is twice the size.
- You will have fewer collisions with a lower load factor and your table will perform better.
- A good rule of thumb is to resize when your load factor is greater than 0.7.

### A good hash function

- A good hash function distributes values in the array evenly.
     
- A bad hash function groups values together and produces a lot of collisions.
     
- SHA is a good hash function.

### Recap

- A hash table is made by combining a hash function with an array.
- Collisions are bad. You need a hash function that minimizes collisions.
- Hash tables have really fast search, insert, and delete.
- hash tables are good for modeling relationships from one item to another.
- Once your load factor is greater than 0.7, it’s time to resize your hash table.
- Hash tables are used for caching data (e.g. with web server).
- Hash tables are great for catching duplicates.