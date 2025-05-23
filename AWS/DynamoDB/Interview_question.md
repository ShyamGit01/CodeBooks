# 💡 DynamoDB Interview Questions and Answers

---

## 1. ❓ What is DynamoDB?

**Answer**:  
DynamoDB is a fully managed NoSQL key-value and document database service by AWS. It delivers single-digit millisecond performance at any scale and is serverless with built-in security, backup, and replication.

---

## 2. ❓ What are the key components of DynamoDB?

**Answer**:
- **Tables**: The container for data.
- **Items**: A single row in a table.
- **Attributes**: A single data element within an item.
- **Primary Key**: Uniquely identifies each item (can be simple or composite).
- **Global Secondary Index (GSI)**: Enables queries on non-primary key attributes.
- **Local Secondary Index (LSI)**: Allows alternate sort keys for the same partition key.

---

## 3. ❓ What is the difference between Partition Key and Sort Key?

**Answer**:
- **Partition Key**: A single attribute used to divide data across partitions.
- **Sort Key**: Optional; allows multiple items with the same partition key but different sort keys.

---

## 4. ❓ When would you use a GSI over an LSI?

**Answer**:
- Use **GSI** when you need to query on a different partition key or when LSIs are insufficient.
- Use **LSI** when the partition key remains the same, but you need to sort differently.

---

## 5. ❓ What is eventually consistent vs strongly consistent read?

**Answer**:
- **Eventually Consistent**: Default, may not reflect latest writes immediately (faster).
- **Strongly Consistent**: Guarantees the latest write is reflected (slightly slower).

---

## 6. ❓ Explain DynamoDB throughput capacity modes.

**Answer**:
- **Provisioned Mode**: You specify read/write capacity units (RCUs/WCUs).
- **On-Demand Mode**: DynamoDB automatically adjusts capacity based on workload.

---

## 7. ❓ What are DynamoDB Streams?

**Answer**:
DynamoDB Streams capture table activity (insert, update, delete) and can trigger AWS Lambda functions in near-real-time.

---

## 8. ❓ How does DynamoDB handle large items?

**Answer**:
Each item in DynamoDB can be up to **400 KB**. For larger data, store in S3 and store the S3 URL in DynamoDB.

---

## 9. ❓ How is data distributed in DynamoDB?

**Answer**:
Data is automatically partitioned using a hash of the partition key, enabling high availability and horizontal scaling.

---

## 10. ❓ What are RCUs and WCUs?

**Answer**:
- **RCU (Read Capacity Unit)**: 1 strongly consistent read per second for items up to 4 KB.
- **WCU (Write Capacity Unit)**: 1 write per second for items up to 1 KB.

---

## 11. ❓ Can you use DynamoDB with transactions?

**Answer**:
Yes, DynamoDB supports ACID transactions via `TransactWriteItems` and `TransactGetItems` API calls.

---

## 12. ❓ What tools are used to interact with DynamoDB?

**Answer**:
- AWS SDKs (Node.js, Python, Java, etc.)
- AWS CLI
- DynamoDB Local (for offline dev/testing)
- AWS Console
- NoSQL Workbench (GUI for modeling)

---

## 13. ❓ What are the limits of DynamoDB?

**Answer**:
- Max item size: **400 KB**
- Max table size: **Unlimited**
- Max LSIs: **5 per table**
- Max GSIs: **20 per table**

---

## 14. ❓ Explain Time to Live (TTL) in DynamoDB.

**Answer**:
TTL automatically deletes expired items based on a timestamp attribute, useful for managing session data, logs, etc.

---

## 15. ❓ What is DynamoDB Accelerator (DAX)?

**Answer**:
DAX is an in-memory caching layer for DynamoDB. It improves response times from milliseconds to microseconds.

---

## 16. ❓ Real-world use case scenario?

**Problem**: User sessions that need fast access and TTL cleanup.  
**Solution**: Store sessions in DynamoDB with `userId` as partition key, `sessionId` as sort key, and use TTL for auto-expiry.

---

