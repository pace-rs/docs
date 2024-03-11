<!-- TODO! This is not the current state -->

# Importing and Exporting Data

This section covers the data import and export features of pace.

- [Importing Data](#importing-data)
- [Exporting Data](#exporting-data)

## Importing Data

### From CSV

You can import data from a CSV file using the
`pace convert --from <path-to-csv>` command. The CSV file should have the
following columns:

<!-- TAKEN FROM BYRON, CHECK WHAT IS PLAUSIBLE FOR GENERAL USE CASES -->

```csv
"Project","Client","Description","Task","User","Group","Email","Tags","Billable","Start Date","Start Time","End Date","End Time","Duration (h)","Duration (decimal)","Billable Rate (EUR)","Billable Amount (EUR)"
```
