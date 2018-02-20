# Create 'exchange_rate' keyspace

CREATE KEYSPACE exchange_rates
WITH replication={'class':'SimpleStrategy','replication_factor': 2};

# Show keyspaces spec
describe keyspace exchange_rates;

# Activate keyspace
USE exchanges_rate;

# Create Table:

create table if not exists rates(
 company text,
 timestp int,
 open float,
 low float,
 high float,
 close float,
 volume float,
 PRIMARY KEY (company, timestp)
);

# Altering table
create table rates(
 company text,
 date timestamp,
 open float,
 high double,
 low double,
 close double,
 PRIMARY KEY (company, date)
);

# Verify table
SELECT * FROM rates;

# PRIMARY KEY:

# Deux valeurs : (Partition key, Clustering key)
# Partition key : indique sur quel node les données sont storées
# Clustering key : détermine par quelle colonne les données sont indexées


# cass_spark usage

1. "docker load -i cass_spark.tar
2 "./spark.sh"

Note : Le container se supprime en sortant du ssh. = "instant interpreter"
