# Creating a database

``` sql
CREATE DATABASE doku_imp;

```

# Creating a table
``` sql
-- table where imports are stored
CREATE TABLE I_IMPORT(
    ID              INT NOT NULL PRIMARY KEY,
    EXT_ID          VARCHAR(20),
    IMPORT_DATE     TIMESTAMP DEFAULT CURRENT_DATE
);

-- table for extension data
CREATE TABLE I_ZONE(
    ID              INT NOT NULL PRIMARY KEY,
    IMPORT_ID       INT NOT NULL,
    ZONE_NAME       VARCHAR(20),
    FOREIGN KEY (IMPORT_ID) REFERENCES I_IMPORT(ID) ON DELETE CASCADE
);

CREATE TABLE I_ASSET(
    ID              INT NOT NULL PRIMARY KEY,
    IMPORT_ID       INT NOT NULL,
    ASSET_NAME       VARCHAR(20)
);

ALTER TABLE I_ASSET
ADD FOREIGN KEY (IMPORT_ID) REFERENCES I_IMPORT(ID) ON DELETE CASCADE;

```

# Inserting values into tables
``` sql
INSERT INTO I_IMPORT (
    ID
    ,EXT_ID
) VALUES (
    198
    ,'AO-124324'
);

INSERT INTO I_ZONE (
    ID
    ,IMPORT_ID
    ,ZONE_NAME
) VALUES (
    23445
    ,198
    ,'Zwenkau'
);

INSERT INTO I_ASSET (
    ID
    ,IMPORT_ID
    ,ASSET_NAME
) VALUES (
    23445
    ,198
    ,'Zwenkau'
);
```

# Show values in Database
``` sql
SELECT *
FROM I_IMPORT;

SELECT *
FROM I_ZONE;

SELECT *
FROM I_ASSET;
```

# deleting values from database and activate on delete cascade
``` sql
DELETE FROM I_IMPORT 
WHERE ID = 198;
```

