- Create table

```
# tokenize=icu zh_CN
# tokenize=unicode61

CREATE VIRTUAL TABLE email USING fts4(sender, title, body, tokenize=icu zh_CN);
```

- Inseart data

```
# simple
INSERT INTO  email (
    sender,
    title,
    body
) 
VALUES
(
    "k.xu@test.com",
    "this is a test title",
    "this is a test body"
);
```

```
# simple Chinese
INSERT INTO  email (
    sender,
    title,
    body
) 
VALUES
(
    "k.xu@test.com",
    "这是标题",
    "这是内容"
);
```

- Full text search 

```
# default fts5 not working for Chinese
SELECT * FROM email WHERE email MATCH "标题";
```
