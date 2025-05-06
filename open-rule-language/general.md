# Open Rule Language

Define la forma de comunicarse con un _reader_ de reglas, que resultados arroja en caso de éxito o default.

Puede incorporse para reglas tipo tabla, árbol o grafos.

```json
{
  "id": "rule-name or rule-id", // optional
  "type": "table", // tree, table
  "cases": [
    {
      "id": "optional",
      "position": 1,
      "condition": [
        {
          "variable": "var_name",
          "operator": "EQ", // "EQ, NE, GT, LT, GE, LE, IN, EX, BT, NB"
          "value": "23"
        },
        {
          "variable": "var_name_2",
          "operator": "BT",
          "value": "18, 60"
        },
        {
          "variable": "var_name_2",
          "operator": "IN",
          "value": "a, e, i, o, u"
        }
      ],
      "kvs": [
        {
          "key": "out01",
          "value": "200"
        },
        {
          "key": "rate",
          "value": "13"
        }
      ]
    }
  ]
}
```
