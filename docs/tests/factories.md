# Factories

Wagtail test data can be created with [wagtail-factories](https://github.com/mvantellingen/wagtail-factories) - a library that helps create [factoryboy](https://factoryboy.readthedocs.io/en/latest/)
factories for wagtail models.

Each model in `models.py` should have a factory in `factories.py`.
The factories can be used in unit tests, and also as a way to define test data for local development.

### Example

```
# models.py

class MyPage(WebPage):
    my_field = models.CharField()
```

```
# factories.py

class MyPageFactory(wagtail_factories.PageFactory):
    my_field = "Test data for this field"
```

```
# test_something.py

class MyTests(TestCase):

    def setUp(self):
        super().setUp()
        self.page = MyPageFactory()

    def test_page(self):
        assert self.page.my_field == "Test data for this field"
```
