CREATE VIEW dbo.vw_AllTransactions AS

    SELECT AccountNo, TranCode, TranDate, Amount, 'LIVE' AS Source
    FROM LiveDB.dbo.Transactions

    UNION ALL

    SELECT AccountNo, TranCode, TranDate, Amount, 'ARCHIVE' AS Source
    FROM ArchiveDB.dbo.Transactions

---

WITH LastTranSummary AS (
    SELECT 
        AccountNo,
        TranCode,
        TranDate,
        SUM(Amount) AS TotalAmount
    FROM dbo.vw_AllTransactions
    WHERE 
        TranCode = 'DD'
        AND TranDate = (
            SELECT MAX(t2.TranDate)
            FROM dbo.vw_AllTransactions t2
            WHERE t2.AccountNo = vw_AllTransactions.AccountNo
              AND t2.TranCode = 'DD'
        )
    GROUP BY AccountNo, TranCode, TranDate
)

---

SELECT 
    m.*,
    lts.TranDate    AS LastDDDate,
    lts.TotalAmount AS LastDDAmount
FROM YourMainTable m
LEFT JOIN LastTranSummary lts 
    ON lts.AccountNo = m.AccountNo

