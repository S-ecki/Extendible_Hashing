# Extendible_Hashing

<img src="https://user-images.githubusercontent.com/75510543/102941268-920b1780-44b2-11eb-8ab8-9133a62921e3.png" width=500 align="right">

 A Datastructure based on *<<std::set>>* using the Extendible Hashing method.
 
Extendible Hashing is a dynamic hash system that is less affected by table growth than static hashing methods. It uses a lookup table that points to Buckets of data, where in the case of an overflow, only the Buckets with an actual overflow get rehashed (instead of the whole table). <br/>
If you want to learn more, click [here](https://www.researchgate.net/publication/220225699_Extendible_Hashing_-_A_Fast_Access_Method_for_Dynamic_Files).

This implementation was created for my class [Algorithmen und Datenstrukturen 1](https://ufind.univie.ac.at/de/course.html?lv=051024&semester=2020S) at the University of Vienna.

## Structure

### Creating a Set
An ads_set can be created in multiple ways:
* Default Constructor: `ADS_set()` creates an empty set
* Initializer List: `ADS_set({args})` creates a set with elements in *args*
* Range Constructor: `ADS_set(InputIt begin, InputIt end)` creates a set from range *begin* until excluding *end*
* Copy Constructor: `ADS_set(ADS_set other)` creates a set with same elements as *other*
* Assignment Operator: `operator=` can be used in conjunction with another *ADS_set* or an *initializer_list*. However, the set must be created beforehand.

Note: the template type `<key_type>` must be specified when creating an ADS_set
### Inserting
You can either use `insert(key)`, `insert({args}` or `insert(InputIt begin, InputIt end)` <br/>
While the former returns a *pair<iterator, bool>* (iterator to inserted element, true if insertion was successful), the other 2 variants return *void*.

### Deleting
`erase(key)` deletes the given key and returns the amount of deleted elements (0/1, because we are dealing with a set) <br/>
`clear()` deletes all elements

### Searching
`count(key)` returns the amount of elements with *key* (0/1) <br/>
`find(key)` returns an *iterator* to the element with *key*, or *end()* if it is not part of the set

### Iterator
ADS_set has an own iterator based on a constant *ForwardIterator* <br/>
`begin()`, `end()` and `operator++` (pre & postfix) work as expected. Iterators can be dereferenced with `operator*` and `operator->`. Moreover, comparisons with `operator==` and `operator!=` are also available, making range-based for-loops possible.

Even though the theoretical option to create an Iterator directly exists, it is strongly discouraged. <br/>
You should rather create Iterators using the above mentioned methods or `find(key)`

### Additional Functionality
`size()` returns the number of elements in the set, while `empty()` returns a boolean. <br/>
`swap(ADS_set other)` can be used to exchange the elements of *this* with *other* in O(1) (only if *other* is passed as a const reference) <br/>
The comparison of 2 ADS_sets with `operator==` and `operator!=` is also available. <br/>
Mainly for debugging, `dump(ostream)` can be called. It prints the content of your current ADS_set + useful information to the passed ostream.


## What I´ve learned
* The principles of different hashing methods (pros and cons)
* Programming close to the hardware with C++ Pointers
* Debugging using Valgrind
* Dealing with ~~existential crisis caused by~~ Segmentation Faults 
* The hardships of using multiple layers of Pointers
* Having to thoroughly research something before you can implementing it (reading papers etc)
* Splitting up a project into phases


### Some Closing Remarks
alles header
comments


