# Corda Enterprise Installation Guide

### Prerequisites

1. Ensure that your Corda Enterprise node is set up and configured ready for CorDapp installation.
2. Ensure your database is configured for your Corda node and that you have the correct JDBC driver installed.
3. Ensure you have the `corda-tools-database-manager-3.1.jar` file installed in the root of your Corda node.

### Steps

For the purpose of the following steps, `/opt/corda` is assumed as the location of your installed Corda Enterprise node.

1. Download the CorDapp JAR files into your `cordapps` directory

```
/opt/corda/cordapps$: sudo wget https://github.com/TradeIX-Limited/MarcoPolo/raw/master/poc/tradeix-concord-0.1.jar
```

```
/opt/corda/cordapps$: sudo wget https://github.com/TradeIX-Limited/MarcoPolo/raw/master/poc/tradeix-concord-domain-0.1.jar
```

2. Create migrations for the CorDapp state schemas

```
/opt/corda$: sudo java -jar corda-tools-database-manager-3.1.jar --base-directory . --create-migration-sql-for-cordapp com.tradeix.concord.schemas.InvoiceSchemaV1
```

```
/opt/corda$: sudo java -jar corda-tools-database-manager-3.1.jar --base-directory . --create-migration-sql-for-cordapp com.tradeix.concord.schemas.PurchaseOrderSchemaV1
```

3. Create a jar file for the schema migration

```
/opt/corda$: sudo jar cvf /opt/corda/cordapps/tradeix-concord-migrations.jar migration
```

4. Run the CorDapp

```
/opt/corda$: sudo systemctl start corda
```

5. Run the Corda web server

```
/opt/corda$: sudo nohup java -jar corda-webserver.jar
```

### Testing

Provided that the above steps have worked, you should be able to browse to the MarcoPolo vault explorer from the following URL:

`http(s)://{ip-address}:{port-number}/web/tix`

