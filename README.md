# Introduction

This application will be developed in **React Native**.

# Survey beta spec

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Groups](#groups)
    - [Code](#code)
    - [Properties](#properties)
- [Sections](#sections)
    - [Code](#code-1)
    - [Properties](#properties-1)
- [Questions types](#questions-types)
    - [Common properties](#common-properties)
    - [Text](#text)
        - [Preview](#preview)
        - [Code](#code-2)
        - [Properties](#properties-2)
        - [Component](#component)
    - [Select1 (unique choice)](#select1-unique-choice)
        - [Preview](#preview-1)
        - [Code](#code-3)
        - [Properties](#properties-3)
        - [Component](#component-1)
    - [Select (multiple choices)](#select-multiple-choices)
        - [Preview](#preview-2)
        - [Code](#code-4)
        - [Properties](#properties-4)
        - [Component](#component-2)
    - [Integer](#integer)
        - [Preview](#preview-3)
        - [Code](#code-5)
        - [Properties](#properties-5)
        - [Component](#component-3)
    - [Float](#float)
        - [Preview](#preview-4)
        - [Code](#code-6)
        - [Properties](#properties-6)
        - [Component](#component-4)
    - [Date](#date)
        - [Preview](#preview-5)
        - [Code](#code-7)
        - [Properties](#properties-7)
        - [Component](#component-5)
    - [Time](#time)
        - [Preview](#preview-6)
        - [Code](#code-8)
        - [Properties](#properties-8)
        - [Component](#component-6)
    - [Date and time](#date-and-time)
        - [Preview](#preview-7)
        - [Code](#code-9)
        - [Properties](#properties-9)
        - [Component](#component-7)
    - [Photo](#photo)
        - [Preview](#preview-8)
        - [Code](#code-10)
        - [Properties](#properties-10)
        - [Component](#component-8)
    - [Video](#video)
        - [Code](#code-11)
        - [Properties](#properties-11)
        - [Component](#component-9)
    - [Audio](#audio)
        - [Code](#code-12)
        - [Properties](#properties-12)
    - [Barcode](#barcode)
        - [Preview](#preview-9)
        - [Code](#code-13)
        - [Properties](#properties-13)
        - [Component](#component-10)
    - [Matrix](#matrix)
        - [Preview](#preview-10)
        - [Code](#code-14)
        - [Properties](#properties-14)
        - [Component](#component-11)
- [Conditions](#conditions)
    - [Code](#code-15)
    - [Properties](#properties-15)
- [Results](#results)
    - [Code](#code-16)
    - [Properties](#properties-16)
- [Example](#example)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Groups

### Code

```json
//survey part
{
  "groupId": "1",
  "groupName": "Informations",
  "groupOrder": 1,
  "context": {},
  "sections": []
}
```
### Properties
| Property | Type | Default value | Required ? | Description |
|---|---|---|---|---|
| groupeId | string | `null` | required | **Unique** group id |
| groupeLabel | string | `null` | required | Group title |
| groupeOrder | int | `null` | required | Group order |
| context | object | `{}` | optional | Group context |
| sections | array | `[]` | optional | List of sections |

## Sections

### Code

```json
//survey part
{
  "sectionId": "1",
  "sectionLabel": "Contact",
  "sectionOrder": 1,
  "onPage": true,
  "context": {},
  "questions": []
}
```
### Properties
| Property | Type | Default value | Required ? | Description |
|---|---|---|---|---|
| sectionId | string | `null` | required | **Unique** section id |
| sectionLabel | string | `null` | required | Section label |
| sectionOrder | int | `null` | required | Section order in its group |
| onPage | boolean | `true` | optional | Questions displayed on one page (`true`) or a page per question (`false`) |
| context | object | `{}` | optional | Section context |
| questions | array | `[]` | optional | List of questions |

## Questions types

### Common properties
| Property | Type | Default value | Required ? | Description |
|---|---|---|---|---|
| questionType | string | `null` | required | Question type. Possible values : `text, select1, select, integer, float, date, time, datetime, photo, audio, video, barcode, matrix` |
| questionId | string | `null` | required | **Unique** question id |
| questionLabel | string | `null` | required | Question label |
| order | int | `null` | required | Question order |
| required | boolean | `false` | required | If question is required (`true`) or not (`false`) |
| defaultValue | mixed | `null` | optional | Question answer default value |
| condition | object | `null` | optional | Question is displayed only is these conditions are true (can be empty if no condition) |
| readonly | boolean | `false` | optional | If question is on read-only (`true`) |
| comments | string | `null` | optional | Comments zone |
| options | object | `{}` | optional | Properties depending on question type |
| context | object | `{}` | optional | Qestion context |

### Text

#### Preview

![Text](/img/form_text.png)

#### Code

```json
//survey part
{
  "questionType": "text",
  "questionId": "1",
  "questionLabel": "What's your name ?",
  "order": 1,
  "required": false,
  "defaultValue": "John",
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "format": null,
    "placeholder": "Enter your name",
    "constraint": null
  },
  "context": {}
}
```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| format | `null` | optional | Text format if needed. Possible values : `tel, email` |
| placeholder | `null` | optional | Placeholder text |
| constraint | `null` | optional | Restrict answer with rules (for example with a regex) |

#### Component

Please use [NativeBase](https://github.com/GeekyAnts/NativeBase)

### Select1 (unique choice)

#### Preview

![select1](/img/form_select1.png)

#### Code
```json
//survey part
{
  "questionType": "select1",
  "questionId": "1",
  "questionLabel": "What's your favorite color?",
  "order": 1,
  "required": true,
  "defaultValue": 2, //refered to key's element
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "list": [
      {
        "key": 0,
        "value": "Blank",
        "order": 1
      },
      {
        "key": 1,
        "value": "Blue",
        "order": 2
      },
      {
        "key": 2,
        "value": "Yellow",
        "order": 3
      }
    ],
    "appearance": "dropdown"
  },
  "context": {}
}
```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| listId | `null` | required | List id |
| appearance | `null` | required | List appearance. Possible values : `dropdown, radio` |

#### Component

Please use [NativeBase](https://github.com/GeekyAnts/NativeBase)

### Select (multiple choices)

#### Preview

![select](/img/form_select.png)

#### Code
```json
//survey part
{
  "questionType": "select",
  "questionId": "1",
  "questionLabel": "What are your favorite colors?",
  "order": 1,
  "required": true,
  "defaultValue": [2,3], //array of refered to key's element,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "list": [
      {
        "key": 0,
        "value": "Blank",
        "order": 1
      },
      {
        "key": 1,
        "value": "Blue",
        "order": 2
      },
      {
        "key": 2,
        "value": "Yellow",
        "order": 3
      }
    ],
    "appearance": "checkbox"
  },
  "context": {}
}
```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| listId | `null` | required | List id |
| appearance | `null` | required | List appearance. Possible values : `popup, checkbox`. |

#### Component

Please use [NativeBase](https://github.com/GeekyAnts/NativeBase)

### Integer

#### Preview

![integer](/img/form_integer.png)

#### Code
```json
//survey part
{
  "questionType": "integer",
  "questionId": "1",
  "questionLabel": "How old are you ?",
  "order": 1,
  "required": true,
  "defaultValue": 27,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "placeholder": "Enter your age",
    "constraint": null
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| placeholder | `null` | optional | Placeholder text |
| constraint | `null` | optional | Restrict answer with rules (for example with a regex) |

#### Component

Please use [NativeBase](https://github.com/GeekyAnts/NativeBase)

### Float

#### Preview

![float](/img/form_float.png)

#### Code
```json
//survey part
{
  "questionType": "float",
  "questionId": "1",
  "questionLabel": "How much does this product cost ?",
  "order": 1,
  "required": true,
  "defaultValue": 142.5,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "placeholder": "Enter the price",
    "constraint": null
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| placeholder | `null` | optional | Placeholder text |
| constraint | `null` | optional | Restrict answer with rules (for example with a regex) |

#### Component

Please use [NativeBase](https://github.com/GeekyAnts/NativeBase)

### Date

#### Preview

![date](/img/form_date.png) ![date](/img/form_date1.png)

#### Code
```json
//survey part
{
  "questionType": "date",
  "questionId": "1",
  "questionLabel": "Pick the date :",
  "order": 1,
  "required": true,
  "defaultValue": null,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "minDate": null,
    "maxDate": null
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| minDate | `null` | optional | Minimum date |
| maxDate | `null` | optional | Maximum date |

#### Component

Please use (React Native DatePicker)[https://github.com/xgfe/react-native-datepicker]

### Time

#### Preview

![time](/img/form_time.png) ![time](/img/form_time1.png) ![time](/img/form_time2.png)

#### Code
```json
//survey part
{
  "questionType": "time",
  "questionId": "1",
  "questionLabel": "Pick the time :",
  "order": 1,
  "required": true,
  "defaultValue": null,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "minTime": null,
    "maxTime": null
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| minTime | `null` | optional | Minimum time |
| maxTime | `null` | optional | Maximum time |

#### Component

Please use (React Native DatePicker)[https://github.com/xgfe/react-native-datepicker]

### Date and time

#### Preview

![datetime](/img/form_datetime.png) ![datetime](/img/form_datetime1.png) ![datetime](/img/form_datetime2.png) ![datetime](/img/form_datetime3.png)

#### Code
```json
//survey part
{
  "questionType": "dateTime",
  "questionId": "1",
  "questionLabel": "Pick a date and a time :",
  "order": 1,
  "required": true,
  "defaultValue": null,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "minDateTime": null,
    "maxDateTime": null
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| minDateTime | `null` | optional | Minimum date and time |
| maxDateTime | `null` | optional | Maximum date and time |

#### Component

Please use (React Native DatePicker)[https://github.com/xgfe/react-native-datepicker]

### Photo

#### Preview

![photo](/img/form_photo.png)

#### Code
```json
//survey part
{
  "questionType": "photo",
  "questionId": "1",
  "questionLabel": "Take a selfie",
  "order": 1,
  "required": true,
  "defaultValue": null,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "quality": "normal",
    "limit": 2,
    "limitRequired": 2
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| quality | `normal` | required | Picture quality. Possible values : `normal, high, low` |
| limit | `null` | optional | Limit of photos taken |
| limitRequired | `null` | optional | Number of required photos. It has to be inferior or equal to the `limit` value |

#### Component

Please use (React Native Camera)[https://github.com/lwansbrough/react-native-camera]

### Video

#### Code
```json
//survey part
{
  "questionType": "video",
  "questionId": "1",
  "questionLabel": "Record a video",
  "order": 1,
  "required": true,
  "defaultValue": null,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "quality": "normal",
    "length": 30,
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| quality | `normal` | required | Video quality. Possible values : `normal, high, low` |
| length | `30` | required | Maximum video duration |

#### Component

Please use (React Native Camera)[https://github.com/lwansbrough/react-native-camera]

### Audio

#### Code
```json
//survey part
{
  "questionType": "audio",
  "questionId": "1",
  "questionLabel": "Record your voice",
  "order": 1,
  "required": true,
  "defaultValue": null,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "length": 60,
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| length | `null` | optional | Maximum audio duration |

### Barcode

#### Preview

![barcode](/img/form_barcode.png)

#### Code
```json
//survey part
{
  "questionType": "barcode",
  "questionId": "1",
  "questionLabel": "Scan a barcode",
  "order": 1,
  "required": true,
  "defaultValue": null,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "limit": 2,
    "limitRequired": 2
  },
  "context": {}
}

```
#### Properties
| Property | Default value | Required ? | Description |
|---|---|---|---|
| limit | `null` | optional | Limit of barcodes scanned |
| limitRequired | `null` | optional | Number of required barcodes. It has to be inferior or equal to the `limit` value |

#### Component

Please use (React Native Camera)[https://github.com/lwansbrough/react-native-camera]

### Matrix

#### Preview

![matrix](/img/form_matrix.png)

#### Code
```json
//survey part
{
  "questionType": "matrix",
  "questionId": "1",
  "questionLabel": "Tell us what you like :",
  "order": 1,
  "required": true,
  "defaultValue": null,
  "condition": null,
  "readonly": false,
  "comments": null,
  "options": {
    "matrixType": "select1",
    "matrixData": {
      "columns": [
        {
          "key": 0,
          "value": "No",
          "order": 2,
          "context": {}
        },
        {
          "key": 1,
          "value": "Yes",
          "order": 1,
          "context": {}
        },
      ],
      "rows": [
        {
          "key": 0,
          "value": "Cheese",
          "order": 1,
          "context": {}
        },
        {
          "key": 1,
          "value": "Spinach",
          "order": 2,
          "context": {}
        },
        {
          "key": 2,
          "value": "Potatoes",
          "order": 4,
          "context": {}
        },
        {
          "key": 3,
          "value": "Bacon",
          "order": 3,
          "context": {}
        },
      ]
    }
  },
  "context": {}
}
```
#### Properties
| Property | Type | Default value | Required ? | Description |
|---|---|---|---|---|
| matrixType | `string` | `text` | required | Matrix type. Possible values : `select1, select, int, float, text`  |
| columns | `array` | `[]` | optional | Column elements. If null, display one default column without any label |
| rows | `array` | `null` | required | Row elements |

#### Component

Please use [NativeBase](https://github.com/GeekyAnts/NativeBase) for the grid and radio buttons

## Conditions

### Code

```json
// Condition on a text / integer / float question type
{
  "conditions": [
    {
      "conditionId": "1",
      "questionId": "1",
      "condition": {
        "operator": ">=",
        "value": [4]
      },
      "context": {}
    }
  ]
}

// Condition on a date / datetime question type
{
  "conditions": [
    {
      "conditionId": "1",
      "questionId": "1",
      "condition": {
        "operator": "<",
        "value": [8954562]
      },
      "context": {}
    }
  ]
}

// Condition on a select1 question type
{
  "conditions": [
    {
      "conditionId": "1",
      "questionId": "1",
      "condition": {
        "operator": "<",
        "value": [1]
      },
      "context": {}
    }
  ]
}

// Condition on a select question type
{
  "conditions": [
    {
      "conditionId": "1",
      "questionId": "1",
      "condition": {
        "operator": "=",
        "value": [1, 3]
      },
      "context": {}
    }
  ]
}

// Condition on a select1 / integer / float / text row of a matrix question type
{
  "conditions": [
    {
      "conditionId": "1",
      "questionId": "1",
      "condition": {
        "operator": "=",
        "value": [
          {
            "rowKey": 0,
            "columnKey": 1
          }
        ],
        "context": {}
      }
    }
  ]
}

// Condition on a select row of a matrix question type
{
  "conditions": [
    {
      "conditionId": "1",
      "questionId": "1",
      "condition": {
        "operator": "=",
        "value": [
          {
            "rowKey": 0,
            "columnKey": 1
          },
          {
            "rowKey": 2,
            "columnKey": 3
          }
        ]
      },
      "context": {}
    }
  ]
}

// Mulitple conditions for a same element
{
  "conditions": [
    "(",
    {
      "conditionId": "1",
      "questionId": "1",
      "condition": {
        "operator": "<",
        "value": [1]
      },
      "context": {}
    },
    "and",
    {
      "conditionId": "2",
      "questionId": "3",
      "condition": {
        "operator": "=",
        "value": [4]
      },
      "context": {}
    },
    ")",
    "or",
    {
      "conditionId": "3",
      "questionId": "1",
      "condition": {
        "operator": "=",
        "value": [6]
      },
      "context": {}
    }
  ]
}
```

### Properties

| Property | Default value | Required ? | Description |
|---|---|---|---|
| conditionId | `null` | required | Condition id |
| questionId | `null` | required | Related question id |
| condition | `null` | optional | Condition constraints |
| condition.operator | `null` | optional | Relational operator to compare the question and a value. Possible values : `>, <, >=, =<` |
| condition.value | `null` | optional | Value to compare, always in a `[]` |

If several conditions for a same question: use `string` operators between conditions. Possible values : `and, or, (, )`

Every row of a matrix question can a condition.

## Results

### Code

```json
// Simple result
{
  "result": {
    "key": 2,
    "value": "Ref 3"
  },
  "context": {
    "questionId": "6",
    "idSection": "2",
    "idGroup": "1"
  }
}

// Mulitple select result
{
  "result": [
    {
      "key": 0,
      "value": "Ref 1"
    },
    {
      "key": 2,
      "value": "Ref 3"
    },
  ],
  "context": {
    "questionId": "6",
    "idSection": "2",
    "idGroup": "1"
  }
}

// Matrix result
{
  "result": {
    "row": {
      "key": 3,
      "value": "Ref 4",
    },
    "column": {
      "key": 1,
      "value": "Oui"
    }
  },
  "context": {
    "idRef": "4",
    "idFamille": "12",
    "questionId": "6",
    "idSection": "2",
    "idGroup": "1"
  }
}
```

### Properties

| Property | Default value | Required ? | Description |
|---|---|---|---|
| result | `null` | required | Question result(s) |
| context | `null` | required |Result context. Minimum required : `questionId, idSection, idGroupe` |
| result.key | `null` | required | Answer id |
| result.value | `null` | required | Answer value |

Results are written in a json object at the moment when the question is answered.

## Example

Form example with real questions used in our current application (in french).

[See example](example.md)
