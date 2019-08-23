
# Functions with Arguments Lab

### Introduction

In this lesson, we have decided to visit another of our travel destinations! This time we have chosen to visit Albuquerque, but we aren't very familiar with this city and are quite hungry after our long flight. We will be working with information we pulled from the Yelp database to help us find a restaurant where we can satisfy our hunger. While Yelp is great for learning about what to do in Albuquerque, it gives us back a lot of information. We'll use what we know about functions and dictionaries to format and read our data more easily. 

### Exploring Two Restaurants in Albuquerque

Let's take a quick look at the information Yelp provides for a single restaurant:


```python
fork_fig = {'categories': [{'alias': 'burgers', 'title': 'Burgers'},
  {'alias': 'sandwiches', 'title': 'Sandwiches'},
  {'alias': 'salad', 'title': 'Salad'}],
 'coordinates': {'latitude': 35.10871, 'longitude': -106.56739},
 'display_phone': '(505) 881-5293',
 'distance': 3571.724649307866,
 'id': 'fork-and-fig-albuquerque',
 'image_url': 'https://s3-media1.fl.yelpcdn.com/bphoto/_-DpXKfS3jv6DyA47g6Fxg/o.jpg',
 'is_closed': False,
 'location': {'address1': '6904 Menaul Blvd NE',
  'address2': 'Ste C',
  'address3': '',
  'city': 'Albuquerque',
  'country': 'US',
  'display_address': ['6904 Menaul Blvd NE', 'Ste C', 'Albuquerque, NM 87110'],
  'state': 'NM',
  'zip_code': '87110'},
 'name': 'Fork & Fig',
 'phone': '+15058815293',
 'price': '$$',
 'rating': 4.5,
 'review_count': 604,
 'transactions': [],
 'url': 'https://www.yelp.com/biz/fork-and-fig-albuquerque?adjust_creative=SYc8R4Gowqru5h4SBKZXsQ&utm_campaign=yelp_api_v3&utm_medium=api_v3_business_search&utm_source=SYc8R4Gowqru5h4SBKZXsQ'}
```


```python
# __SOLUTION__ 
fork_fig = {'categories': [{'alias': 'burgers', 'title': 'Burgers'},
  {'alias': 'sandwiches', 'title': 'Sandwiches'},
  {'alias': 'salad', 'title': 'Salad'}],
 'coordinates': {'latitude': 35.10871, 'longitude': -106.56739},
 'display_phone': '(505) 881-5293',
 'distance': 3571.724649307866,
 'id': 'fork-and-fig-albuquerque',
 'image_url': 'https://s3-media1.fl.yelpcdn.com/bphoto/_-DpXKfS3jv6DyA47g6Fxg/o.jpg',
 'is_closed': False,
 'location': {'address1': '6904 Menaul Blvd NE',
  'address2': 'Ste C',
  'address3': '',
  'city': 'Albuquerque',
  'country': 'US',
  'display_address': ['6904 Menaul Blvd NE', 'Ste C', 'Albuquerque, NM 87110'],
  'state': 'NM',
  'zip_code': '87110'},
 'name': 'Fork & Fig',
 'phone': '+15058815293',
 'price': '$$',
 'rating': 4.5,
 'review_count': 604,
 'transactions': [],
 'url': 'https://www.yelp.com/biz/fork-and-fig-albuquerque?adjust_creative=SYc8R4Gowqru5h4SBKZXsQ&utm_campaign=yelp_api_v3&utm_medium=api_v3_business_search&utm_source=SYc8R4Gowqru5h4SBKZXsQ'}
```

Above is the information provided about `Fork & Fig`, but all restaurants are provided with this information.  For example, here is the information provided by Yelp for another restaurant, `Frontier Restaurant`.


```python
frontier_restaurant = {'categories': [{'alias': 'mexican', 'title': 'Mexican'},
  {'alias': 'diners', 'title': 'Diners'},
  {'alias': 'tradamerican', 'title': 'American (Traditional)'}],
 'coordinates': {'latitude': 35.0808088832532, 'longitude': -106.619402244687},
 'display_phone': '(505) 266-0550',
 'distance': 4033.6583235266075,
 'id': 'frontier-restaurant-albuquerque-2',
 'image_url': 'https://s3-media4.fl.yelpcdn.com/bphoto/M9L2z6-G0NobuDJ6YTh6VA/o.jpg',
 'is_closed': False,
 'location': {'address1': '2400 Central Ave SE',
  'address2': '',
  'address3': '',
  'city': 'Albuquerque',
  'country': 'US',
  'display_address': ['2400 Central Ave SE', 'Albuquerque, NM 87106'],
  'state': 'NM',
  'zip_code': '87106'},
 'name': 'Frontier Restaurant',
 'phone': '+15052660550',
 'price': '$',
 'rating': 4.0,
 'review_count': 1369,
 'transactions': [],
 'url': 'https://www.yelp.com/biz/frontier-restaurant-albuquerque-2?adjust_creative=SYc8R4Gowqru5h4SBKZXsQ&utm_campaign=yelp_api_v3&utm_medium=api_v3_business_search&utm_source=SYc8R4Gowqru5h4SBKZXsQ'}
```


```python
# __SOLUTION__ 
frontier_restaurant = {'categories': [{'alias': 'mexican', 'title': 'Mexican'},
  {'alias': 'diners', 'title': 'Diners'},
  {'alias': 'tradamerican', 'title': 'American (Traditional)'}],
 'coordinates': {'latitude': 35.0808088832532, 'longitude': -106.619402244687},
 'display_phone': '(505) 266-0550',
 'distance': 4033.6583235266075,
 'id': 'frontier-restaurant-albuquerque-2',
 'image_url': 'https://s3-media4.fl.yelpcdn.com/bphoto/M9L2z6-G0NobuDJ6YTh6VA/o.jpg',
 'is_closed': False,
 'location': {'address1': '2400 Central Ave SE',
  'address2': '',
  'address3': '',
  'city': 'Albuquerque',
  'country': 'US',
  'display_address': ['2400 Central Ave SE', 'Albuquerque, NM 87106'],
  'state': 'NM',
  'zip_code': '87106'},
 'name': 'Frontier Restaurant',
 'phone': '+15052660550',
 'price': '$',
 'rating': 4.0,
 'review_count': 1369,
 'transactions': [],
 'url': 'https://www.yelp.com/biz/frontier-restaurant-albuquerque-2?adjust_creative=SYc8R4Gowqru5h4SBKZXsQ&utm_campaign=yelp_api_v3&utm_medium=api_v3_business_search&utm_source=SYc8R4Gowqru5h4SBKZXsQ'}
```

As we already know, one way to quickly view the attributes of a dictionary is to look at the keys of the dictionary.


```python
fork_fig.keys()
```


```python
# __SOLUTION__ 
fork_fig.keys()
```




    dict_keys(['categories', 'coordinates', 'display_phone', 'distance', 'id', 'image_url', 'is_closed', 'location', 'name', 'phone', 'price', 'rating', 'review_count', 'transactions', 'url'])




```python
frontier_restaurant.keys()
```


```python
# __SOLUTION__ 
frontier_restaurant.keys()
```




    dict_keys(['categories', 'coordinates', 'display_phone', 'distance', 'id', 'image_url', 'is_closed', 'location', 'name', 'phone', 'price', 'rating', 'review_count', 'transactions', 'url'])




```python
fork_fig.keys() == frontier_restaurant.keys()
```


```python
# __SOLUTION__ 
fork_fig.keys() == frontier_restaurant.keys()
```




    True



As we can see from our above comparison, Yelp provides us with the same information for both restaurants.  

### Writing our functions

Ok, now let's write our functions.  Write a function called `restaurant_name` that, provided a dictionary representing a restaurant like you saw above, returns that restaurant's name.


```python
def restaurant_name(restaurant):
    pass
```


```python
# __SOLUTION__ 
def restaurant_name(restaurant):
    return restaurant['name']
```


```python
restaurant_name(frontier_restaurant) # 'Frontier Restaurant'
```


```python
# __SOLUTION__ 
restaurant_name(frontier_restaurant) # 'Frontier Restaurant'
```




    'Frontier Restaurant'




```python
restaurant_name(fork_fig) # 'Fork & Fig'
```


```python
# __SOLUTION__ 
restaurant_name(fork_fig) # 'Fork & Fig'
```




    'Fork & Fig'



Now write a function called `restaurant_rating` that returns the rating of the provided restaurant.


```python
def restaurant_rating(restaurant):
    pass
```


```python
# __SOLUTION__ 
def restaurant_rating(restaurant):
    return restaurant['rating']
```


```python
restaurant_rating(frontier_restaurant) # 4.0
```


```python
# __SOLUTION__ 
restaurant_rating(frontier_restaurant) # 4.0
```




    4.0




```python
restaurant_rating(fork_fig) # 4.5
```


```python
# __SOLUTION__ 
restaurant_rating(fork_fig) # 4.5
```




    4.5



### Comparing restaurants

Now let's write a function called `is_better` that returns `True` if a restaurant has a higher rating than an alternative restaurant.  The first argument should be called `restaurant` and the second argument should be called `alternative`.  The function returns `False` if the two ratings are equal.


```python
def is_better(restaurant, alternative):
    pass
```


```python
# __SOLUTION__ 
def is_better(restaurant, alternative):
    if restaurant['rating'] > alternative['rating']:
        return True
    return False
```


```python
is_better(frontier_restaurant, fork_fig) # False
```


```python
# __SOLUTION__ 
is_better(frontier_restaurant, fork_fig) # False
```




    False




```python
is_better(fork_fig, frontier_restaurant) # True
```


```python
# __SOLUTION__ 
is_better(fork_fig, frontier_restaurant) # True
```




    True




```python
is_better(fork_fig, fork_fig) # False
```


```python
# __SOLUTION__ 
is_better(fork_fig, fork_fig) # False
```




    False



Now let's write a function called `is_cheaper` that returns `True` if a restaurant has a lower price, that is the restaurant has fewer `'$'` signs, than an alternative restaurant. The first argument should be called `restaurant` and the second argument should be called `alternative`. The function returns `False` if the two prices are equal.

> **Hint:** *Strings in Python respond to then `len` function.*


```python
def is_cheaper(restaurant, alternative):
    pass
```


```python
# __SOLUTION__ 
def is_cheaper(restaurant, alternative):
    if len(restaurant['price']) < len(alternative['price']):
        return True
    return False
```


```python
is_cheaper(fork_fig, frontier_restaurant) # False
```


```python
# __SOLUTION__ 
is_cheaper(fork_fig, frontier_restaurant) # False
```




    True




```python
is_cheaper(frontier_restaurant, fork_fig) # True
```


```python
# __SOLUTION__ 
is_cheaper(frontier_restaurant, fork_fig) # True
```




    False




```python
is_cheaper(fork_fig, fork_fig) # False
```


```python
# __SOLUTION__ 
is_cheaper(fork_fig, fork_fig) # False
```




    False



Now write a function called `high_rating` that takes a `restaurant` as a first argument and a rating (in the form of a number) as the second argument and returns `True` if the given restaurant's rating is greater than or equal to the provided rating and returns `False` otherwise.


```python
def high_rating(restaurant, rating):
    pass
```


```python
# __SOLUTION__ 
def high_rating(restaurant, rating):
    if restaurant['rating'] >= rating:
        return True
    return False
```


```python
high_rating(fork_fig, 4) # True
```


```python
# __SOLUTION__ 
high_rating(fork_fig, 4) # True
```




    True




```python
high_rating(fork_fig, 5) # False
```


```python
# __SOLUTION__ 
high_rating(fork_fig, 5) # False
```




    False




```python
high_rating(frontier_restaurant, 4) # True
```


```python
# __SOLUTION__ 
high_rating(frontier_restaurant, 4) # False
```




    True



### Summary

Great! In this lab we saw how to pass both single and multiple arguments to functions.
