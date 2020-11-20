# ACID

## 1. Atomicity
- All queries must succed. If one fails ll should rollback 

![Atomicity example](/images/acid_1.PNG)

There are further more queries need to be done after the update query but for some reasons the database crashed. The balance has just gone. Like, I sent $ 100 to somebody but nobody gets it.

## 2. Isolation
- Can my inflight transaction see changes made by other transactions?
- Read phenomena
    - Dirty Reads
  
        ![Dirty read](/images/dirty_read.PNG)

    - Non-repeatable read
  
        ![Non-repeatable read](/images/non-repeatable.PNG)

    - Phantom read
  
        ![phantom-read](/images/phantom_read.PNG)

- Isolation Levels
  - Read uncommitted -> No isolation. Any change from the outside is visible to the transaction.
  - Read committed -> Each query in a transaction only sees committed stuff.
  - Repeatable Read -> Each query in a transaction only sees committed updates at the beginning of transaction.
  - Serializable -> Trasnactions are serialized.
  
    ![Isolation levels vs read phenomena](/images/isolation_read.PNG)

## 3. Consistency