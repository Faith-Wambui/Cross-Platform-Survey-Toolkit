### 1. `calculate` Type Fields
* **Behavior:** KoboToolbox enforces strict checks on `calculate` rows; if `type` is set to `calculate`, the `calculation` column must not be blank.
* **Fix:** Populated `position(..)` for `roster_index` on Row 14.

### 2. Cascading Selects (`choice_filter`)
* **Behavior:** Kobo evaluates XPath expressions in `choice_filter` strictly against key-value headers in the `choices` sheet. 
* **Observation:** Unfiltered option lists appear if column names in `choices` do not match the exact key referenced in `choice_filter: column_name=${question_name}`.