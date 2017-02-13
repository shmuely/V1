## V1 Patterns - Textual Representation

## V1 Element types

|   | JSON type property | V1 element type         | visual representation
|---|------------|-------------------------|----------------------
|1  | Start      | Query Start             | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element01.png)
|2  | Yellow     | Yellow Entity           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element02.png)
|3  | Blue       | Blue Entity             | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element03.png)
|4  | Red        | Red Entity              | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element04.png)
|5  | AggEnt     | Aggregate Entity        | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element05.png)
|6  | LogEnt     | Logical Entity          | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element06.png)
|7  | Rel        | Relationship            | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element07.png)
|8  | EntProp    | Entity's Property       | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element08.png)
|9  | RelProp    | Relationship's Property | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element09.png)
|10 | Quant1     | Quantifier 1            | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element10.png)
|11 | Quant2     | Quantifier 2            | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element11.png)
|12 | EComb      | E-Combiner              | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element12.png)
|13 | RComb      | R-Combiner              | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element13.png)
|14 | Path       | Path                    | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element14.png)
|15 | PathSeg    | Path Segment            | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element15.png)
|16 | HQuant     | Horizontal Quantifier   | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element16.png)
|17 | HComb      | Horizontal Combiner     | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element17.png)
|18 | SplitBy    | Split By                | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element18.png)
|19 | SplitsCond | Splits Condition        | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element19.png)
|31 | AggL1     | L1 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element31.png)
|32 | AggL2     | L2 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element32.png)
|33 | AggL3     | L3 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element33.png)
|34 | AggL4     | L4 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element34.png)
|41 | AggM1     | M1 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element41.png)
|42 | AggM2     | M2 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element42.png)
|43 | AggM3     | M3 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element43.png)
|44 | AggM4     | M4 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element44.png)
|45 | AggM5     | M5 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element45.png)
|51 | AggP1     | P1 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element51.png)
|52 | AggP2     | P2 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element52.png)
|53 | AggP3     | P3 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element53.png)
|54 | AggP4     | P4 Aggregation           | ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/Element54.png)

## Wrappers for relationships / paths

**N** - No-existance  ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/WrapperX.png)
**X** - No-connection ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/WrapperN.png)
**L** - Latent        ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/WrapperL.png)
**O** - Optional      ![V1](https://raw.githubusercontent.com/LiorKogan/V1/master/Elements/WrapperO.png)

**TODO**: add entity tag inequalities

## JSON structure

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | Ont       | string | Ontology name
| +       | Name      | string | Query name
| +       | Elements  | [...]  | Elements composing the query

**Elements: for each query element:**

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | ENum      | int    | Element number. Distinct value for each element
| +       | Type      | string | JSON element type

## E1: Query Start (Type = 'Start')

There must be a single element with type 'Start'. Its ENum must equals to 0.

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | R         | int    | ENum of element on the right. <br> Valid element types: SplitBy

## E2: Yellow Entity (Type = 'Yellow')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | ETag      | string | Entity tag (e.g. "A")
| +       | EID       | int    | Technical ID of the entity
| +       | EType     | int    | Entity type (e.g. of 'Person') <br> According to the ontology
| +       | EName     | string | Display name of the entity (e.g. "Lior Kogan")
|         | R         | int    | ENum of element on the right. <br> Valid element types: Rel, EntProp, Quant1, EComb, Path

## E3: Blue Entity (Type = 'Blue')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | ETag      | string | Entity tag (e.g. "A")
| +       | EType     | int    | Entity type (e.g. of 'Person') <br> According to the ontology
|         | R         | int    | ENum of element on the right.  <br> Valid element types: Rel, EntProp, Quant1, EComb, Path
|         | B         | int    | ENum of element below. <br> Valid element types: AggP1, AggP4

## E4: Red Entity (Type = 'Red')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | ETag      | string | Entity tag (e.g. "A")
|         | VTypes    | [int]  | Valid entity types <br> According to the ontology <br> VTypes and NVTypes can't be both present
|         | NVTypes   | [int]  | Invalid entity types <br> According to the ontology <br> VTypes and NVTypes can't be both present
|         | R         | int    | ENum of element on the right. <br> Valid element types: Rel, EntProp, Quant1, EComb, Path

## E5: Aggregate Entity (Type = 'AggEnt')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | ETag      | string | Entity tag (e.g. "A")
| +       | FName     | string | file name, where defined
| +       | EName     | string | name - as defined in file
|         | R         | int    | ENum of element on the right. <br> Valid element types: Rel, EntProp, Quant1, EComb, Path

## E6: Logical Entity (Type = 'LogEnt')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | ETag      | string | Entity tag (e.g. "A")
| +       | FName     | string | file name, where defined
| +       | EName     | string | name - as defined in file
|         | R         | int    | ENum of element on the right.  <br> Valid element types: Rel, EntProp, Quant1, EComb, Path

## E7: Relationship (Type = 'Rel')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | RType     | int    | Relationship type (e.g. of 'own') <br> According to the ontology
| +       | Dir       | char   | "-": non-directional, "R": Arrow pointing right, "L": Arrow pointing left
|         | Wrapper   | char   | "X": no-existance, "N": no-connection, "L": Latent, "O": Optional
|         | R         | int    | ENum of element on the right. <br> Valid element types: Yellow, Blue, Red, AggEnt, LogEnt, Quant2, RComb
|         | B         | int    | ENum of element below. <br> Valid element types: <ul><li>RelProp</li> <li>HQuant</li> <li>AggL1 (valid wrappers: NL)</li> <li>AggL2 (valid wrappers: L)</li> <li>AggL3 (valid wrappers: L)</li> <li>AggL4 (valid wrappers: NL)</li> <li>AggM1 (valid wrappers: NL)</li> <li>AggM2(valid wrappers: L)</li> <li>AggM3 (valid wrappers: L)</li> <li>AggM4 (valid wrappers: L)</li> <li>AggM5 (no valid wrappers)</li> <li>SplitBy (valid wrappers: NL)</li></ul> 

## E8: Entity's Property (Type = 'EntProp') 

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | PType     | int    | Property type (e.g. of 'own') <br> According to the ontology
|         | PTag      | string | Property tag to assign (e.g. "1")
|         | Cond      | string | condition

## E9: Relationship's Property (Type = 'RelProp')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | PType     | int    | Property type (e.g. of 'own') <br> According to the ontology
|         | PTag      | string | Property tag to assign (e.g. "1")
|         | Cond      | string | condition
|         | B         | int    | ENum of element below. <br> Valid element types: HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5, SplitBy

## E10: Quantifier 1 (Type = 'Quant1')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | QType     | string | "all", "notall", "none", "notnone", "eq", "gt", "ge", "lt", "le", "ne", "range", "notrange"
| +       | Branches  | int    | number of branches (>1)
| +       | R         | [int]  | ENum of elements on the right. <br> Valid element types: Rel, Path, EntProp, Quant1
|         | B         | int    | ENum of element below. <br> Valid element types: <ul><li>HQuant </li> <li> AggL1 </li> <li> AggL2 </li> <li> AggL4 </li> <li> AggM1 </li> <li> AggM2 </li> <li> AggM4 </li> <li> SplitBy </li></ul> (Aggregation is valid only if there is at least one entity right of the quantifier)

## E11: Quantifier 2 (Type = 'Quant2')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | QType     | string | "all", "notall", "none", "notnone", "eq", "gt", "ge", "lt", "le", "ne", "range", "notrange"
| +       | Branches  | int    | number of branches (>1)
| +       | R         | [int]  | ENum of elements on the right. <br> Valid element types: Yellow, Blue, Red, AggEnt, LogEnt, Quant2

## E12: E-Combiner (Type = 'EComb')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | R         | int    | ENum of elements on the right. <br> Valid element types: Rel, EntProp, Quant1, EComb, Path

## E13: R-Combiner (Type = 'RComb')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | R         | int    | ENum of element on the right. <br> Valid element types: Yellow, Blue, Red, AggEnt, LogEnt, RComb, Quant2

## E14: Path (Type = 'Path') 

|Mandatory| Name      | Type       | Description
|---------|-----------|------------| ------
|         | ETypes    | [ * ]      | Entity types <br> For each entry: <ul><li>Entity type - according to the ontology</li> <li> Optional [string] operator ("eq", "lt", or "le") and [int] value</li></ul>
|         | RTypes    | [ * ]      | Relationship types <br> For each entry: <ul><li>Relationship type - according to the ontology</li> <li>Optional [string] operator ("eq", "lt", or "le") and [int] value</li> <li>Optional [string] direction ("R" or "L")</li></ul>
|         | Length    | *          | Path length. Either <ul><li>[string] operator ("eq", "lt", "le") and [int] value</li> <li>[string] operator ('in') and [int],[int] values</li> <li>[string] operator ('shortest')</li></ul>
|         | Wrapper   | string     | "X": no-existance, "N": no-connection, "L": Latent, "O": Optional
|         | R         | int        | ENum of element on the right. <br> Valid element types: Yellow, Blue, Red, AggEnt, LogEnt, Quant1, RComb
|         | B         | int        | ENum of element below. <br> Valid element types: <ul><li>RelProp</li> <li>HQuant</li> <li>AggL1 (valid wrappers: NLO)</li> <li>AggL2 (valid wrappers: LO)</li> <li>AggL4 (valid wrappers: NLO)</li> <li>AggM1 (valid wrappers: NL)</li> <li>AggM2 (valid wrappers: L)</li> <li>AggM4(valid wrappers: L)</li></ul> 

## E15: Path Segment (Type = 'PathSeg')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
|         |           |        |

## E16: Horizontal Quantifier (Type = 'HQuant')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
| +       | QType     | string | "all", "notall", "none", "notnone", "eq", "gt", "ge", "lt", "le", "ne", "range", "notrange"
| +       | Branches  | int    | number of branches (>1)
| +       | B         | int    | ENum of element below. <br> Valid element types: RelProp, HQuant, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5


## E17: Horizontal Combiner (Type = 'HComb')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
|         | B         | int    | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5

## E18: Split by (Type = 'SplitBy')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
|         | RelProp   | string | name of relationship's property to split by (e.g. "since")
|         | Tag       | string | pt/at/st to split by (e.g. "1")
|         | ETTag     | string | entity type tag to split by (e.g. "1")

Exactly one of the above must be presented

## E19: Splits condition (Type = 'SplitsCond')

|Mandatory| Name      | Type   | Description
|---------|-----------|--------| ------
|         | Cond      | string | condition
|         | STag      | string | split tag to assign (e.g. "1")

At least one of the above must be presented

## E31: L1 Aggregation (Type = 'AggL1')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
| +       | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
| +       | ETag      | string   | entity tag on the '→/{et}' clause. '→' is denoted '->'
|         | ATag      | string   | attribute tag to assign (e.g. "1")
|         | Cond      | string   | condition
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5


## E32: L2 Aggregation (Type = 'AggL2')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
| +       | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
|         | ATag      | string   | attribute tag to assign (e.g. "1")
|         | Cond      | string   | condition
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5

## E33: L3 Aggregation (Type = 'AggL3')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
| +       | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
|         | ATag      | string   | attribute tag to assign (e.g. "1")
| +       | AggOp     | string   | aggregation operator ("min" / "max" / "sum" / "avg" / "distinct")
| +       | RelProp   | string   | name of relationship's property to aggregate (e.g. "since")
|         | Cond      | string   | condition
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5

## E34: L4 Aggregation (Type = 'AggL4')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
| +       | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
|         | ATag      | string   | attribute tag to assign (e.g. "2")
| +       | AggOp     | string   | aggregation operator ("min" / "max" / "sum" / "avg" / "distinct")
| +       | Tag       | string   | pt/at/st to aggregate (e.g. "1")
|         | Cond      | string   | condition
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5

## E41: M1 Aggregation (Type = 'AggM1')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
|         | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
| +       | n         | int      | number of min/max entities
| +       | ETag      | [string] | entity tags on the 'n {et,et,...} clause
| +       | op        | string   | "min" / "max"
| +       | ETag2     | [string] | entity tags on the 'with min/max {et,et,...} clause
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5

## E42: M2 Aggregation (Type = 'AggM2')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
|         | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
| +       | n         | int      | number of min/max entities
| +       | ETag      | [string] | entity tags on the 'n {et,et,...} clause
| +       | op        | string   | "min" / "max"
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5

## E43: M3 Aggregation (Type = 'AggLM3')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
|         | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
| +       | n         | int      | number of min/max entities
| +       | ETag      | [string] | entity tags on the 'n {et,et,...} clause
| +       | op        | string   | "min" / "max"
| +       | AggOp     | string   | aggregation operator ("min" / "max" / "sum" / "avg" / "distinct")
| +       | RelProp   | string   | name of relationship's property to aggregate (e.g. "since")
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5

## E44: M4 Aggregation (Type = 'AggM4')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
|         | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
| +       | n         | int      | number of min/max entities
| +       | ETag      | [string] | entity tags on the 'n {et,et,...} clause
| +       | op        | string   | "min" / "max"
| +       | Tag       | string   | pt/at/st to aggregate (e.g. "1")
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5

## E45: M5 Aggregation (Type = 'AggM5')

|Mandatory| Name      | Type     | Description
|---------|-----------|----------| ------
|         | Per       | [string] | entity tags on the 'per {et,et,...}/→' clause. '→' is denoted '->'
| +       | n         | int      | number of min/max entities
| +       | op        | string   | "min" / "max"
| +       | RelProp   | string   | name of relationship's property to aggregate (e.g. "since")
|         | B         | int      | ENum of elements below. <br> Valid element types: RelProp, HQuant, HComb, AggL1, AggL2, AggL3, AggL4, AggM1, AggM2, AggM3, AggM4, AggM5