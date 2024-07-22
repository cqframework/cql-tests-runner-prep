The buildLibraryTests.py is a python script that generates library test xml versions of the CQF Unit Tests for expressions.

For example, the output could look like this for CqlAggregateFunctionsTest.xml:

```xml
<tests>
  <test name="CqlAggregateFunctionsTest">
    <library>library CqlAggregateFunctionsTest version '1.0.0'

define AllTrueAllTrue:
  AllTrue({true,true})

define AllTrueTrueFirst:
  AllTrue({true,false})

...

    </library>
    <output name="AllTrueAllTrue">true</output>
    <output name="AllTrueTrueFirst">false</output>
    ...
  </test>
</tests>
```

These files could then be used in place of the individual tests to run them all as a library using the test runner's library test capability.

To use:

```bash
python buildLibraryTests.py /path/to/input_test_file.xml /path/to/output_directory
```

The script will generate the versions of the test files with ``_library.xml`` appended to the end.

For example, to copy all of the CQFramework unit tests, replace the `/path/to/output_directory` path to your desired location and run this:

```bash
python buildLibraryTests.py ../cql-tests/tests/cql/CqlAggregateFunctionsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlAggregateTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlArithmeticFunctionsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlComparisonOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlConditionalOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlDateTimeOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlErrorsAndMessagingOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlIntervalOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlListOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlLogicalOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlNullologicalOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlOverloadMatching.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlQueryTests.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlStringOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlTypeOperatorsTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/CqlTypesTest.xml /path/to/output_directory
python buildLibraryTests.py ../cql-tests/tests/cql/ValueLiteralsAndSelectors.xml /path/to/output_directory
```