# Tests

| Test code                   | Test title                                | Status | Dependencies |
|-----------------------------|-------------------------------------------|--------|--------------|
| PJ01                        | Project Setup                             | ready  | none         |
| GL01                        | Global Positioning (map coordinates)      | ready  | PJ01         |
| [AL22](./AL22_example-test) | Two railway track alignments without cant | ready  | GL01         |
| AL23                        | Two railway track alignments with cant    | ready  | AL22         |
| AL24                        | Stationing for two alignments             | ready  | AL23         |
| SB01                        | Track sub-structure for single track      | ready  | AL23         |
| SP01                        | Track super-structure for single track    | ready  | AL23         |
| TSTP                        | Track Structures Turnout Panel            | ready  | AL22         |
| GR01                        | Group objects                             | ready  | SB01, SP01   |
| CL01                        | Classify objects                          | ready  | SB01, SP01   |
| PP01                        | Add properties                            | ready  | GR01         |
| ALRW1                       | Alignment Railway Curves - Bloss          |        | none         |
| ALRW2                       | Alignment Railway Curves - Clothoid       |        | none         |
| ALRW3                       | Alignment Railway Curves - Cosine         |        | none         |
| ALRW4                       | Alignment Railway Curves - Helmert        |        | none         |
| ALRW5                       | Alignment Railway Curves - Sine           |        | none         |
| ALRW6                       | Alignment Railway Curves - Viennese Bend  |        | none         |
| ...                         |                                           |        |              |
| ...                         |                                           |        |              |
