### 1. `calculate` Type Fields
* **Behavior:** KoboToolbox enforces strict checks on `calculate` rows; if `type` is set to `calculate`, the `calculation` column must not be blank.
* **Fix:** Populated `position(..)` for `roster_index` on Row 14.

### 2. Cascading Selects (`choice_filter`)
* **Behavior:** Kobo evaluates XPath expressions in `choice_filter` strictly against key-value headers in the `choices` sheet. 
* **Observation:** Unfiltered option lists appear if column names in `choices` do not match the exact key referenced in `choice_filter: column_name=${question_name}`.
### 3. Cascading Select Visibility
* **Enketo / Kobo Behavior:** Questions with `choice_filter` display their label/title immediately with an empty choice list. 
* **Design Pattern:** Adding `relevant: ${parent_var} != ''` hides both the question title and field until the parent question is answered.

### 8. CommCare Roster Adaptation (Fixed Slots vs. Repeat Groups)
* **Challenge:** Dynamic `begin_repeat` loops throw schema/case generation errors in CommCare HQ when importing raw XLSForms without pre-configured case block mappings.
* **Workaround:** Implemented a fixed-slot approach (up to 10 household members) in the XML structure to ensure smooth form rendering and reliable offline data capture in CommCare Collect.