# psgspythonstl


```
most_common
```
- list of elements and counts sorted by count

```
elements
```
- expands a counter to a list
- omits non-positive counts


```
update
```
- adds to counts instead of replacing them


```
subtract
```
- subtracts counts, complement of update

example1
```
from collections import Counter
c=Counter()
c['a']=1
c['b']=3
c['c']=2
c.most_common()
c['d'] #0
```


example2
```
str="a b c s a d"
str=str.lower()
words = str.split(' ')
str_count = Counter()
for word in words:
  str_count[word]+=1
str_count.most_common()
```
example3
```
list(str_count.elements())
str_count.keys()
```
example4
```
lis=['a','b','c','d']
list_counter=Counter(lis)
c.update(list_counter)

another_lis=['a']
another_lis_counter=Counter(another_lis)
c.subtract(another_lis_counter)
c.most_common()
```


### 3 Other dict Extensions
```
defaultdict
```
- generate default values for missing keys
- initializer for a type
- factory function

```
OrderedDict
```
- pop_item
- move_to_end
- Raises an error for missing keys


```
from collections import defaultdict
str_dict = defaultdict(str)
str_dict['a'] # ''
```
```
from collections import defaultdict
str_dict = defaultdict(float)
str_dict['a'] # 0.0
```

```
class Fraction(object):
  def __init__(self):
    self.n=1
    self.d=2
  
  def __repr__(self):
    return '{0}/{1}'.format(self.n,self.d)
```
```
frac = defaultdict(Fraction)
frac_dict['foo']  #1/2
```

```
def dne():
  return 'DNE'

dne_dict = defaultDict(dne)
dne_dict['foo']
```
#### 05:52
```
fruit = OrderedDict()
for f in ['a','b','c']:
  fruit[f]=random.randint(50,100)
# move to end
```
fruit.move_to_end('b')
```
# move to first
```
fruit.move_to_end('b',False)
```

#remove last item
```
fruit.popitem()
```
#remove first item
```
fruit.popitem(False)
```

### 4 Named Tuples
```
from collections import namedtuple
Address = namedtuple('Name',['server','client'])
```
