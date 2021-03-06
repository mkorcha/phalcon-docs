Class **Phalcon\\Db\\Result\\Pdo**
==================================

*implements* :doc:`Phalcon\\Db\\ResultInterface <Phalcon_Db_ResultInterface>`

Encapsulates the resultset internals  

.. code-block:: php

    <?php

    $result = $connection->query("SELECT * FROM robots ORDER BY name");
    $result->setFetchMode(Phalcon\Db::FETCH_NUM);
    while ($robot = $result->fetchArray()) {
    	print_r($robot);
    }



Methods
-------

public  **__construct** (:doc:`Phalcon\\Db\\AdapterInterface <Phalcon_Db_AdapterInterface>` $connection, *\PDOStatement* $result, [*string* $sqlStatement], [*array* $bindParams], [*array* $bindTypes])

Phalcon\\Db\\Result\\Pdo constructor



public  **execute** ()

Allows to execute the statement again. Some database systems don't support scrollable cursors, So, as cursors are forward only, we need to execute the cursor again to fetch rows from the begining



public  **fetch** ([*unknown* $fetchStyle], [*unknown* $cursorOrientation], [*unknown* $cursorOffset])

Fetches an array/object of strings that corresponds to the fetched row, or FALSE if there are no more rows. This method is affected by the active fetch flag set using Phalcon\\Db\\Result\\Pdo::setFetchMode 

.. code-block:: php

    <?php

    $result = $connection->query("SELECT * FROM robots ORDER BY name");
    $result->setFetchMode(Phalcon\Db::FETCH_OBJ);
    while ($robot = $result->fetch()) {
    	echo $robot->name;
    }




public  **fetchArray** ()

Returns an array of strings that corresponds to the fetched row, or FALSE if there are no more rows. This method is affected by the active fetch flag set using Phalcon\\Db\\Result\\Pdo::setFetchMode 

.. code-block:: php

    <?php

    $result = $connection->query("SELECT * FROM robots ORDER BY name");
    $result->setFetchMode(Phalcon\Db::FETCH_NUM);
    while ($robot = result->fetchArray()) {
    	print_r($robot);
    }




public  **fetchAll** ([*unknown* $fetchStyle], [*unknown* $fetchArgument], [*unknown* $ctorArgs])

Returns an array of arrays containing all the records in the result This method is affected by the active fetch flag set using Phalcon\\Db\\Result\\Pdo::setFetchMode 

.. code-block:: php

    <?php

    $result = $connection->query("SELECT * FROM robots ORDER BY name");
    $robots = $result->fetchAll();




public  **numRows** ()

Gets number of rows returned by a resultset 

.. code-block:: php

    <?php

    $result = $connection->query("SELECT * FROM robots ORDER BY name");
    echo 'There are ', $result->numRows(), ' rows in the resultset';




public  **dataSeek** (*unknown* $number)

Moves internal resultset cursor to another position letting us to fetch a certain row 

.. code-block:: php

    <?php

    $result = $connection->query("SELECT * FROM robots ORDER BY name");
    $result->dataSeek(2); // Move to third row on result
    $row = $result->fetch(); // Fetch third row




public  **setFetchMode** (*unknown* $fetchMode, [*unknown* $colNoOrClassNameOrObject], [*unknown* $ctorargs])

Changes the fetching mode affecting Phalcon\\Db\\Result\\Pdo::fetch() 

.. code-block:: php

    <?php

    //Return array with integer indexes
    $result->setFetchMode(Phalcon\Db::FETCH_NUM);
    
    //Return associative array without integer indexes
    $result->setFetchMode(Phalcon\Db::FETCH_ASSOC);
    
    //Return associative array together with integer indexes
    $result->setFetchMode(Phalcon\Db::FETCH_BOTH);
    
    //Return an object
    $result->setFetchMode(Phalcon\Db::FETCH_OBJ);




public  **getInternalResult** ()

Gets the internal PDO result object



