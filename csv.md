# TIL - csv data manipulation

__Unfortunately "awk -F," (field separator of comma) doesn't work with most real CSV files, because of quoted fields, commas in fields, and (less frequently) multiline fields.__

## Print first column

```awk
awk -F, '{print $1}' file.csv
```

## Print first and third column

```awk
awk -F, '{print $1 "," $3}' file.csv
```

## Print only the lines containing specific string

```bash
grep "string" file.csv
grep -i "string" file.csv
```

## Sort file based on the values in second column

```bash
sort -t, -k2 file.csv
```

## To remove the first row (header), use

```bash
tail -n +2 file.csv
```

## To remove duplicates based on values in the first column

```bash
awk -F, '!seen[$1]++' file.csv
```

## To sum up the values in third column

```bash
awk -F, '{sum+=$3} END {print sum}' file.csv
```

## Convert CSV to JSON array

```bash
jq -R -r 'split(",") | {firstname:.[0],lastname:.[1]}'
```

## To remove the header

```bash
tail -n +2 sample.csv | jq -R -r 'split(",") | {firstname:.[0],lastname:.[1]}'
```

## Create SQL insert statement

```bash
awk -F, '{printf "INSERT INTO table VALUES (\"%s\", \"%s\", \"%s\");\n", $1, $2, $3}'
```

## duckdb

```
duckdb -c "from 'customers.csv'"
```

## Sum field

```
duckdb -c "select sum(C) from 'test.csv'"
```

## cvskit - https://csvkit.readthedocs.io/en/latest/

