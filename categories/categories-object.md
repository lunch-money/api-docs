# Categories Object

| **Attribute Name** |  | **Type** |  | **Description** |
| :--- | :--- | :--- | :--- | :--- |
| **id** |  | number |  | Unique identifier for category |
| **name** |  | string |  | Name of category. Must be between 1 and 40 characters |
| **description** |  | string |  | Description of category. Must not exceed 140 characters |
| **is\_income** |  | boolean |  | Whether or not transactions in this category should be treated as income |
| **exclude\_from\_budget** |  | boolean |  | Whether or not transactions in this category should be excluded from budget |
| **exclude\_from\_totals** |  | boolean |  | Whether or not transactions in this category should be excluded from totals |
| **updated\_at** |  | string |  | Date/time at which category was last updated in ISO 8601 extended format |
| **created\_at** |  | string |  | Date/time at which category was created in ISO 8601 extended format |
| **is\_group** |  | boolean |  | If true, denotes a category group |
| **group\_id** |  | number |  | If not null, this category is part of a category group and this value denotes the ID of top-level category  |

