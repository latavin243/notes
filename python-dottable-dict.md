# Dottable Dict
```python
class DottableDict(dict):
    """
    Dot accessible python dict.
    e.g.
    d = DottableDict(a="aa", b=2)
    print(d.a)  # aa
    print(d.b)  # 2
    """

    def __init__(self, **kwargs):
        super(DottableDict, self).__init__(**kwargs)
        if kwargs:
            for k, v in kwargs.items():
                self[k] = v

    def __getattr__(self, attr):
        return self.get(attr)

    def __setattr__(self, key, value):
        self.__setitem__(key, value)

    def __setitem__(self, key, value):
        super(DottableDict, self).__setitem__(key, value)
        self.__dict__.update({key: value})

    def __delattr__(self, item):
        self.__delitem__(item)

    def __delitem__(self, key):
        super(DottableDict, self).__delitem__(key)
        del self.__dict__[key]
```