# Example

Exemple de formulaire avec le contexte et la partie métier, sur des questions existantes.

```json
// Survey

{
  "context": {
    "idCdnc": 52,
    "idPersonne": 653,
    "idMission": 58
  },
  "survey": [
    // C'est le groupe qui a possibilité de répéter une ou plusieurs sections via un filtre
    // Group 1
    {
      "groupId": "1",
      "groupName": "Relevés de produits",
      "groupOrder": 1,
      "sections": [
        // Section 1
        {
          "sectionId": "1" ,
          "sectionLabel": "Relevé produit",
          "sectionOrder": 1,
          "onPage": false,
          "questions": [
            // Présence du produit
            {
              "questionId": "1",
              "questionType": "matrix",
              "questionLabel": "Présence du produit :",
              "order": 1,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "matrixType": "select1",
                "matrixData": {
                  "columns": [
                    {
                      "key": 0,
                      "value": "Non",
                      "order": 2
                    },
                    {
                      "key": 1,
                      "value": "Oui",
                      "order": 1
                    }
                  ],
                  "rows": [
                    {
                      "key": 0,
                      "value": "Ref 1",
                      "context": {
                        "idRef": "1"
                      }
                    },
                    {
                      "key": 1,
                      "value": "Ref 2",
                      "context": {
                        "idRef": "2"
                      }
                    },
                    {
                      "key": 2,
                      "value": "Ref 3",
                      "context": {
                        "idRef": "3"
                      }
                    },
                    {
                      "key": 3,
                      "value": "Ref 4",
                      "context": {
                        "idRef": "4"
                      }
                    }
                  ]
                }
              },
              "conditions": [],
              "context": {}
            },
            // Facing
            {
              "questionId": "2",
              "questionType": "matrix",
              "questionLabel": "Facing :",
              "order": 2,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "matrixType": "integer",
                "matrixData": {
                  "rows": [
                    {
                      "key": 0,
                      "value": "Ref 1",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 0,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "1"
                      }
                    },
                    {
                      "key": 1,
                      "value": "Ref 2",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 1,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "2"
                      }
                    },
                    {
                      "key": 2,
                      "value": "Ref 3",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 2,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "3"
                      }
                    },
                    {
                      "key": 3,
                      "value": "Ref 4",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 3,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "4"
                      }
                    }
                  ]
                }
              },
              "conditions": [],
              "context": {}
            },
            // Prix
            {
              "questionId": "3",
              "questionType": "matrix",
              "questionLabel": "Prix :",
              "order": 3,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "matrixType": "float",
                "matrixData": {
                  "rows": [
                    {
                      "key": 0,
                      "value": "Ref 1",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 0,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "1"
                      }
                    },
                    {
                      "key": 1,
                      "value": "Ref 2",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 1,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "2"
                      }
                    },
                    {
                      "key": 2,
                      "value": "Ref 3",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 2,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "3"
                      }
                    },
                    {
                      "key": 3,
                      "value": "Ref 4",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 3,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "4"
                      }
                    }
                  ]
                }
              },
              "conditions": [],
              "context": {}
            },
            // Etiquettes
            {
              "questionId": "4",
              "questionType": "matrix",
              "questionLabel": "Etiquettes :",
              "order": 4,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "matrixType": "select1",
                "matrixData": {
                  "columns": [
                    {
                      "key": 0,
                      "value": "Non",
                      "order": 2
                    },
                    {
                      "key": 1,
                      "value": "Oui",
                      "order": 1
                    }
                  ],
                  "rows": [
                    {
                      "key": 0,
                      "value": "Ref 1",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 0,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "1"
                      }
                    },
                    {
                      "key": 1,
                      "value": "Ref 2",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 1,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "2"
                      }
                    },
                    {
                      "key": 2,
                      "value": "Ref 3",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 2,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "3"
                      }
                    },
                    {
                      "key": 3,
                      "value": "Ref 4",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 3,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "4"
                      }
                    }
                  ]
              },
              "conditions": [],
              "context": {}
            },
            // Position
            {
              "questionId": "5",
              "questionType": "matrix",
              "questionLabel": "Position :",
              "order": 5,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "matrixType": "integer",
                "matrixData": {
                  "rows": [
                    {
                      "key": 0,
                      "value": "Ref 1",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 0,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "1"
                      }
                    },
                    {
                      "key": 1,
                      "value": "Ref 2",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 1,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "2"
                      }
                    },
                    {
                      "key": 2,
                      "value": "Ref 3",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 2,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "3"
                      }
                    },
                    {
                      "key": 3,
                      "value": "Ref 4",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 3,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "4"
                      }
                    }
                  ]
                }
              },
              "conditions": [],
              "context": {}
            }
          ], // end questions
          "conditions": [],
          "context": {}
        },
        // Section 2
        {
          "sectionId": "2" ,
          "sectionLabel": "Autre(s) relevé(s)",
          "sectionOrder": 2,
          "onPage": false,
          "questions": [
            // Photo avant action
            {
              "questionId": "6",
              "questionType": "photo",
              "questionLabel": "Photo avant action :",
              "order": 1,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "quality": "normal",
                "limit": 2,
                "limitRequired": 1
              },
              "conditions": [],
              "context": {}
            },
            // PDL
            {
              "questionId": "7",
              "questionType": "matrix",
              "questionLabel": "PDL :",
              "order": 2,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "matrixType": "integer",
                "matrixData": {
                  "rows": [
                    {
                      "key": 0,
                      "value": "Ref 1",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 0,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "1"
                      }
                    },
                    {
                      "key": 1,
                      "value": "Ref 2",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 1,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "2"
                      }
                    },
                    {
                      "key": 2,
                      "value": "Ref 3",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 2,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "3"
                      }
                    },
                    {
                      "key": 3,
                      "value": "Ref 4",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 3,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "4"
                      }
                    }
                  ]
                }
              },
              "conditions": [],
              "context": {}
            }
          ], // end questions
          "conditions": [],
          "context": {}
        }
      ], // end sections
      "conditions": [],
      "context": {
        // Si répétition par famille
        "familleId": "12"
        // Si répétition par emplacement
        // "idEmplacement": "2"
        // Si pas de répétition, context vide
      }
    },
    // Group 2
    {
      "groupId": "2",
      "groupName": "Actions",
      "groupOrder": 2,
      "sections": [
        // Section 3
        {
          "sectionId": "3" ,
          "sectionLabel": "Quelles actions ?",
          "sectionOrder": 1,
          "onPage": false,
          "questions": [
            // As-tu fait une action ?
            {
              "questionId": "8",
              "questionType": "select1",
              "questionLabel": "As-tu fait une action ?",
              "order": 1,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "list": [
                  {
                    "key": 0,
                    "value": "Non",
                    "order": 2
                  },
                  {
                    "key": 1,
                    "value": "Oui",
                    "order": 1
                  }
                ]
              },
              "conditions": [],
              "context": {}
            },
            // Quelles actions ?
            {
              "questionId": "9",
              "questionType": "select",
              "questionLabel": "Quelles actions ?",
              "order": 2,
              "required": false,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "list": [
                  {
                    "key": 0,
                    "value": "Réimplantation / Recadrage",
                    "order": 1
                  },
                  {
                    "key": 1,
                    "value": "MEA négociée",
                    "order": 2
                  },
                  {
                    "key": 2,
                    "value": "MEA installée",
                    "order": 3
                  },
                  {
                    "key": 3,
                    "value": "PLV négociée",
                    "order": 4
                  },
                  {
                    "key": 4,
                    "value": "PLV installée",
                    "order": 5
                  },
                  {
                    "key": 5,
                    "value": "2 en 1",
                    "order": 6
                  },
                  {
                    "key": 6,
                    "value": "Implantation sur produits absents",
                    "order": 7
                  },
                  {
                    "key": 7,
                    "value": "Commandes (tous produits)",
                    "order": 8
                  }
                ]
              },
              "conditions": [
                {
                  "questionId": "8",
                  "condition": {
                    "values": [
                      {
                        "key": 1
                      }
                    ],
                    "operator": "="
                  },
                  "context": {}
                }
              ],
              "context": {}
            }
          ], // end questions
          "conditions": [],
          "context": {}
        }
      ], // end sections
      "conditions": [],
      "context": {}
    },
    // Group 3
    {
      "groupId": "3",
      "groupName": "Réimplantation / Recadrage",
      "groupOrder": 3,
      "sections": [
        // Section 4
        {
          "sectionId": "4" ,
          "sectionLabel": "Réimplantation / Recadrage",
          "sectionOrder": 1,
          "onPage": false,
          "questions": [
            // Réimplantation ou recadrage ?
            {
              "questionId": "10",
              "questionType": "select1",
              "questionLabel": "Réimplantation ou recadrage ?",
              "order": 1,
              "required": false,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "list": [
                  {
                    "key": 0,
                    "value": "Réimplantation",
                    "order": 1
                  },
                  {
                    "key": 1,
                    "value": "Recadrage",
                    "order": 2
                  }
                ]
              },
              "conditions": [],
              "context": {}
            },
            {
              "questionId": "11",
              "questionType": "select",
              "questionLabel": "Quelles marques ?",
              "order": 2,
              "required": false,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "list": [
                  {
                    "key": 0,
                    "value": "Marque 1",
                    "order": 1
                  },
                  {
                    "key": 1,
                    "value": "Marque 2",
                    "order": 2
                  }
                ]
              },
              "conditions": [],
              "context": {}
            }
          ], // end questions
          "conditions": [],
          "context": {}
        }
      ], // end sections
      "conditions": [
        {
          "questionId": "9",
          "condition": {
            "values": [
              {
                "key": 0
              }
            ],
            "operator": "="
          },
          "context": {}
        }
      ],
      "context": {}
    },
    // Group 4
    {
      "groupId": "4",
      "groupName": "Réimplantation / Recadrage : Marque 1",
      "groupOrder": 4,
      "sections": [
        // Section 5
        {
          "sectionId": "5" ,
          "sectionLabel": "Relevé de produits de la marque 1 - Réimplantation / Recadrage",
          "sectionOrder": 1,
          "onPage": false,
          "questions": [
            // Facing
            {
              "questionId": "12",
              "questionType": "matrix",
              "questionLabel": "Facing marque 1 - Réimplantation / Recadrage",
              "order": 1,
              "required": false,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "matrixType": "integer",
                "matrixData": {
                  "rows": [
                    {
                      "key": 0,
                      "value": "Ref 1",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 0,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "1"
                      }
                    },
                    {
                      "key": 1,
                      "value": "Ref 2",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 1,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "2"
                      }
                    },
                    {
                      "key": 2,
                      "value": "Ref 3",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 2,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "3"
                      }
                    },
                    {
                      "key": 3,
                      "value": "Ref 4",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 3,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "4"
                      }
                    }
                  ]
                }
              },
              "conditions": [],
              "context": {}
            },
            // Position
            {
              "questionId": "13",
              "questionType": "matrix",
              "questionLabel": "Position marque 1 - Réimplantation / Recadrage",
              "order": 2,
              "required": false,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "matrixType": "integer",
                "matrixData": {
                  "rows": [
                    {
                      "key": 0,
                      "value": "Ref 1",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 0,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "1"
                      }
                    },
                    {
                      "key": 1,
                      "value": "Ref 2",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 1,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "2"
                      }
                    },
                    {
                      "key": 2,
                      "value": "Ref 3",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 2,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "3"
                      }
                    },
                    {
                      "key": 3,
                      "value": "Ref 4",
                      "conditions": [
                        {
                          "questionId": "1",
                          "condition": {
                            "operator": "=",
                            "values": [
                              {
                                "rowKey": 3,
                                "columnKey": 1
                              }
                            ],
                            "context": {}
                          }
                        }
                      ],
                      "context": {
                        "idRef": "4"
                      }
                    }
                  ]
                }
              },
              "conditions": [],
              "context": {}
            },
            // Photo après action
            {
              "questionId": "14",
              "questionType": "photo",
              "questionLabel": "Photo après action marque 1",
              "order": 3,
              "required": true,
              "defaultValue": null,
              "readonly": false,
              "comments": null,
              "options": {
                "quality": "normal",
                "limit": 2,
                "limitRequired": 1
              },
              "conditions": [],
              "context": {}
            }
          ], // end questions
          "conditions": [],
          "context": {}
        }
      ], // end sections
      "conditions": [
        {
          "questionId": "11",
          "condition": {
            "values": [
              {
                "key": 0
              }
            ],
            "operator": "="
          },
          "context": {}
        }
      ],
      "context": {
        "familleId": "12"
      }
    }
  ] // end groups
} // end survey
```
