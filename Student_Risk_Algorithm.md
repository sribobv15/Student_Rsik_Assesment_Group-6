# Student Risk Assessment Algorithm — Pseudocode

**Project:** Identifying Students at Risk of Academic Failure Using Educational Data  
**Group:** 6

## Algorithm

```text
START

// STAGE 1: DATA LOADING
LOAD "Data.csv" INTO dataset
SET cleaned_data = EMPTY LIST
SET seen_rows = EMPTY SET
SET missing_count = 0
SET invalid_count = 0
SET duplicate_count = 0

// STAGE 2: DATA CLEANING
FOR EACH student IN dataset

    IF failures IS MISSING OR
       studytime IS MISSING OR
       absences IS MISSING OR
       G3 IS MISSING THEN
        missing_count = missing_count + 1
        CONTINUE
    END IF

    IF failures NOT IN [0,1,2,3] OR
       studytime NOT IN [1,2,3,4] OR
       absences IS NOT a nonnegative integer OR
       G3 IS NOT a number BETWEEN 0 AND 20 THEN
        invalid_count = invalid_count + 1
        CONTINUE
    END IF

    IF COMPLETE_ROW(student) IN seen_rows THEN
        duplicate_count = duplicate_count + 1
        CONTINUE
    END IF

    ADD COMPLETE_ROW(student) TO seen_rows
    ADD student TO cleaned_data

END FOR

// STAGE 3: INITIALISE COUNTERS
SET low_count = 0
SET medium_count = 0
SET high_count = 0
SET TP = 0
SET FP = 0
SET FN = 0
SET TN = 0

// STAGE 4: RISK SCORING
FOR EACH student IN cleaned_data

    SET risk_score = 0

    IF failures >= 2 THEN
        risk_score = risk_score + 2
    ELSE IF failures = 1 THEN
        risk_score = risk_score + 1
    END IF

    IF studytime = 1 THEN
        risk_score = risk_score + 1
    END IF

    IF absences > 10 THEN
        risk_score = risk_score + 1
    END IF

    // STAGE 5: RISK CLASSIFICATION
    IF risk_score >= 3 THEN
        SET risk = "High Risk"
        high_count = high_count + 1
    ELSE IF risk_score >= 1 THEN
        SET risk = "Medium Risk"
        medium_count = medium_count + 1
    ELSE
        SET risk = "Low Risk"
        low_count = low_count + 1
    END IF

    // STAGE 6: EVALUATION USING G3
    SET predicted_failure = (risk = "High Risk")
    SET actual_failure = (G3 < 10)

    IF predicted_failure AND actual_failure THEN
        TP = TP + 1
    ELSE IF predicted_failure AND NOT actual_failure THEN
        FP = FP + 1
    ELSE IF NOT predicted_failure AND actual_failure THEN
        FN = FN + 1
    ELSE
        TN = TN + 1
    END IF

    OUTPUT student, risk_score, risk, G3

END FOR

// STAGE 7: FINAL RESULTS
SET total = TP + FP + FN + TN

IF total > 0 THEN
    SET accuracy = ((TP + TN) / total) * 100
ELSE
    SET accuracy = "Not available"
END IF

OUTPUT "Missing records:", missing_count
OUTPUT "Invalid records:", invalid_count
OUTPUT "Possible duplicates:", duplicate_count
OUTPUT "Cleaned records:", SIZE(cleaned_data)

OUTPUT "Low Risk students:", low_count
OUTPUT "Medium Risk students:", medium_count
OUTPUT "High Risk students:", high_count

OUTPUT "True Positives:", TP
OUTPUT "False Positives:", FP
OUTPUT "False Negatives:", FN
OUTPUT "True Negatives:", TN
OUTPUT "Prediction Accuracy:", accuracy

END
```
