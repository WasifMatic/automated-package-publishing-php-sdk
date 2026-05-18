# Simple Calculator

```php
$simpleCalculatorController = $client->getSimpleCalculatorController();
```

## Class Name

`SimpleCalculatorController`


# Calculate

Calculates the expression using the specified operation.

```php
function calculate(string $operation, float $x, float $y): float
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `operation` | [`string(OperationTypeEnum)`](../../doc/models/operation-type-enum.md) | Template, Required | The operator to apply on the variables |
| `x` | `float` | Query, Required | The LHS value |
| `y` | `float` | Query, Required | The RHS value |

## Response Type

**200**

`float`

## Example Usage

```php
$operation = OperationTypeEnum::SUM;

$x = 222.14;

$y = 165.14;

$simpleCalculatorController = $client->getSimpleCalculatorController();

try {
    $result = $simpleCalculatorController->calculate(
        $operation,
        $x,
        $y
    );
    echo 'float:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

