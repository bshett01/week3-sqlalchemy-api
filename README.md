Courses API:

As a part of weekend activity , here we will run  pytests for lab exercise Part1,Part2,Part3 of week 3.



**Lets get started...**

Point to directory : cd week3-sqlalchemy-api

Create Virtual environment: python3 -m venv .venv

Install packages: python -m pip install -r requirements.txt

Run:
python -m pytest -q
Totally 11 tests are expected to pass.

Run:
python -m pytest -q

expected result:

tests/test_api.py::test_create_and_retrieve PASSED                                                           [  9%]
tests/test_api.py::test_duplicate_does_not_add_row PASSED                                                    [ 18%]
tests/test_api.py::test_invalid_input_does_not_add_row PASSED                                                [ 27%]
tests/test_api.py::test_missing_course PASSED                                                                [ 36%]
tests/test_api.py::test_starts_empty PASSED                                                                  [ 45%]
tests/test_api.py::test_data_survives_new_application PASSED                                                 [ 54%]
tests/test_api.py::test_missing_title PASSED                                                                 [ 63%]
tests/test_api.py::test_create_after_duplicate PASSED                                                        [ 72%]
tests/test_rules.py::test_enrolment_boundary[-1-True] PASSED                                                 [ 81%]
tests/test_rules.py::test_enrolment_boundary[0-False] PASSED                                                 [ 90%]
tests/test_rules.py::test_enrolment_boundary[1-False] PASSED                                                 [100%]





test flow:

pytest
  |
  v
client fixture
  |
  v
app_factory fixture
  |
  v
create temporary database
  |
  v
create FastAPI app
  |
  v
replace get_db with test database
  |
  v
create TestClient
  |
  v
pass client into test
