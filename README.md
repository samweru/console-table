# PHP ConsoleTable

**ConsoleTabe** makes you easy to build console style tables. It helps you to display tabular data in terminal/shell. This is a component of [PHPLucidFrame](https://github.com/phplucidframe/phplucidframe).

License: MIT

## Example 1: Bordered Table (Default)

    require 'src/LucidFrame/Console/ConsoleTable.php';

    $table = new LucidFrame\Console\ConsoleTable();
    $table
        ->addHeader('Language')
        ->addHeader('Year')
        ->addRow()
            ->addColumn('PHP')
            ->addColumn(1994)
        ->addRow()
            ->addColumn('C++')
            ->addColumn(1983)
        ->addRow()
            ->addColumn('C')
            ->addColumn(1970)
        ->display()
    ;

You can also print the table using `getTable` method such as `echo $table->getTable();`

**Output**:

    +----------+------+
    | Language | Year |
    +----------+------+
    | PHP      | 1994 |
    | C++      | 1983 |
    | C        | 1970 |
    +----------+------+

## Example 2: Bordered Table with Padding Width 2

You can also use `setHeaders()` and `addRow` with Arrays.

    require 'src/LucidFrame/Console/ConsoleTable.php';

    $table = new LucidFrame\Console\ConsoleTable();
    $table
        ->setHeaders(array('Language', 'Year'))
        ->addRow(array('PHP', 1994))
        ->addRow(array('C++', 1983))
        ->addRow(array('C', 1970))
        ->setPadding(2)
        ->display()
    ;

**Output**:

    +------------+--------+
    |  Language  |  Year  |
    +------------+--------+
    |  PHP       |  1994  |
    |  C++       |  1983  |
    |  C         |  1970  |
    +------------+--------+

## Example 3: Bordered Table with Left Margin Width 4

    require 'src/LucidFrame/Console/ConsoleTable.php';

    $table = new LucidFrame\Console\ConsoleTable();
    $table
        ->setHeaders(array('Language', 'Year'))
        ->addRow(array('PHP', 1994))
        ->addRow(array('C++', 1983))
        ->addRow(array('C', 1970))
        ->setIndent(4)
        ->display()
    ;

**Output**:

        +----------+------+
        | Language | Year |
        +----------+------+
        | PHP      | 1994 |
        | C++      | 1983 |
        | C        | 1970 |
        +----------+------+

## Example 4: Non-bordered Table with Header

    require 'src/LucidFrame/Console/ConsoleTable.php';

    $table = new LucidFrame\Console\ConsoleTable();
    $table
        ->setHeaders(array('Language', 'Year'))
        ->addRow(array('PHP', 1994))
        ->addRow(array('C++', 1983))
        ->addRow(array('C', 1970))
        ->hideBorder()
        ->display()
    ;

**Output**:

     Language  Year
    ----------------
     PHP       1994
     C++       1983
     C         1970

## Example 5: Non-bordered Table without Header

    require 'src/LucidFrame/Console/ConsoleTable.php';

    $table = new LucidFrame\Console\ConsoleTable();
    $table
        ->addRow(array('PHP', 1994))
        ->addRow(array('C++', 1983))
        ->addRow(array('C', 1970))
        ->hideBorder()
        ->display()
    ;

**Output**:

     PHP  1994
     C++  1983
     C    1970
