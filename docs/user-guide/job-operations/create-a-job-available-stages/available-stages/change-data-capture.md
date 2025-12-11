# Change Data Capture Stage.

This stage is intended to find all differences between before (old) and after (new) datasets. Based on them, CDC
produces an additional column — 'Operation', which indicates the state of the row from the old dataset considering its
presence/absence in the new one. CDC compares each row of the new and the old datasets based on keys and col-
umns to compare values and sets Operation value.

**Note**: old and new datasets must not contain duplicates (rows with the same key) based on key column(s). Old and
new datasets columns to compare, as well as key columns, must be present in both datasets with the same name.
If there are duplicated rows in at least one dataset, the result of the CDC gets unpredictable.

![](../../../../assets/user-guide-img/image36.png)
