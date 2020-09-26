# Linear Hashing Data Structure
A simple data structure using Linear Hashing to store and organise data. This code is not fully optimised and can be rather wordy for the sake of clarity. I wanted this code to be able to be improved upon and used to show an intuitive (if unoptimised) way of solving the problem at hand to students, classmates, or anyone browsing the internet. During my time writing this code I have found many online implementations of Linear Hashing to be quite impressive, yet unusable for learning purposes as they showed many optimal ways of solving issues that the student may just copy and shrug off. In showing a less optimal, yet intuitive and clear way of approaching the problem I hope future ADS students as well as other students interested in the subject may find a little bit of clarity and understanding of the way Linear Hashing works.
In the future, I might return to this code and make a more optimised branch, but for now I am satisfied with the way the code works (and mostly reads).
Created for the [Algorithms and Data Structures course at the University of Vienna in the 2020 Summer Semester.](https://ufind.univie.ac.at/en/course.html?lv=051024&semester=2020S)

# Functionality
ADS_set represents a simplified, generalised version of the STL types *«std::set»* and *«std::unordered_set»*.
For full specification, [click here](https://cewebs.cs.univie.ac.at/ADS/ss20/index.php?m=D&t=unterlagen&c=show&CEWebS_what=Spezifikation). *(in German)*

### Creating and Initialising a New ADS_set
To initialise an ADS_set use `ADS_set<key_type> name {args}`.
For `args` you can either use nothing to create an empty ADS_set or use an `std::initializer_list<type> list` to initialise the ADS_Set with the values of the list, duplicate values will be skipped. You can also use two `InputIt` and the range in between them will be used as initial values for the ADS_set.
#### Assignment operators
You can also use `operator=` to set an existing ADS_set to another ADS_set or to an `std::initializer_list<type> list`.

### Inserting and Erasing Elements
The `insert(args)` function can be called with `args` of a single key of the same type as the ADS_set, for a range of two `InputIt` or an `std::initializer_list<type> list`. If a single key is inserted, the `insert` function will return an `std::pair<iterator,bool>` where the `iterator` will point to the inserted element (or, if the element could not be inserted due to already being in the ADS_set, to that element) and the `bool` will represent whether an element was inserted (`true`) or not (`false`).
To erase an element from the ADS_set use `erase(key_type)`. This function returns the amount of erased elements, 0 or 1.
You can also use `clear()` to erase all elements from the ADS_set.

### Finding Elements
All the find functions first use the `count(key_type)` function, which returns the number of times the specified element is stored in the ADS_set, 0 or 1.
`find(key_type)` returns an iterator pointing to the specified element, or, if it couldn't be found, `end()`.

### Other Functions
The ADS_set can be compared to another using `operator==` and `operator!=`, can use `swap(ADS_set)` to swap contents with another ADS_set, can check number of stored elements with `size()` and check whether the container is empty with `empty()`.

### Iterator Class
The ADS_set comes complete with an iterator class that represents a constant `«ForwardIterator»`.
The iterator makes sure that, for example, range based for loops can be executed on ADS_set.
The iterator can be incremented using `operator++` (postfix and prefix).
You can also use `begin()` and `end()` to return iterators to the beginning or end of an ADS_set.
To initialise an iterator, you can use multiple constructor parameters, the most relevant is:
`Iterator(const key_type*, const ADS_set*, Bucket*, int, int)` with the following parametres:
* The value stored at the iterator
* The ADS_set the iterator belongs to
* A pointer to the Bucket the stored value is stored in
* The index the value is stored at in the Bucket it is stored in
* The row of the table the Bucket is stored in in the ADS_set

### Disclaimer
Hello future ADS students! Don't copy my code, the professors will find out. Dankeschön!
