# pytest

## Fixtures

```python
import pytest

@pytest.fixture
def my_value():
    return 5

def test_my_fruit_in_basket(my_value):
    result = my_value + 5
    assert result == 10
```

- also see <https://docs.pytest.org/en/6.2.x/fixture.html#back-to-fixtures>
- [Fixture scopes](https://docs.pytest.org/en/6.2.x/fixture.html#fixture-scopes)

## Temporary Directories

- fixture `tmp_path`: provides a `pathlib.Path` object
- fixture `tmpdir`: provides a legacy `py.path.local` object

## Parametrize

```python
import pytest

@pytest.mark.parametrize("test_input,expected", [("3+5", 8), ("2+4", 6), ("6*9", 42)])
def test_eval(test_input, expected):
    assert eval(test_input) == expected
```

- also see <https://docs.pytest.org/en/7.3.x/how-to/parametrize.html#pytest-mark-parametrize-parametrizing-test-functions>

## Assert expected Exception

```python
import pytest

def test_zero_division():
    with pytest.raises(ZeroDivisionError):
        1 / 0
```

- also see <https://docs.pytest.org/en/7.4.x/how-to/assert.html#assertions-about-expected-exceptions>

## Skip Tests

```python
import pytest

@pytest.mark.skip(reason="no way of currently testing this")
def test_the_unknown():
    ...
```

- also see <https://docs.pytest.org/en/7.1.x/how-to/skipping.html#skipping-test-functions>

## Flaky Tests

- rerun flaky tests
- see [pytest-rerunfailures](https://github.com/pytest-dev/pytest-rerunfailures)

```python
import pytest

# reruns_delay is in seconds and optional
@pytest.mark.flaky(reruns=5, reruns_delay=2)
def test_example():
    assert random.choice([True, False])
```
