---
description: 'Más información acerca de cómo: asignar una matriz a otra (Visual Basic)'
title: Procedimiento para asignar una matriz a otra
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: dc86225c1f25c207e793e33a048d948646ac77b6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434737"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>Cómo: Asignar una matriz a otra (Visual Basic)

Dado que las matrices son objetos, puede usarlas en instrucciones de asignación como otros tipos de objeto. Una variable de matriz contiene un puntero a los datos que conforman los elementos de la matriz y la información de rango y longitud, y una asignación solo copia este puntero.

### <a name="to-assign-one-array-to-another-array"></a>Para asignar una matriz a otra matriz

1. Asegúrese de que las dos matrices tienen el mismo rango (número de dimensiones) y tipos de datos de elementos compatibles.

2. Use una instrucción de asignación estándar para asignar la matriz de origen a la matriz de destino. No siga ningún nombre de matriz entre paréntesis.

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

Al asignar una matriz a otra, se aplican las siguientes reglas:

- **Rangos iguales.** El rango (número de dimensiones) de la matriz de destino debe ser el mismo que el de la matriz de origen.

  Siempre que los rangos de las dos matrices sean iguales, no es necesario que las dimensiones sean iguales. El número de elementos de una dimensión determinada puede cambiar durante la asignación.

- **Tipos de elemento.** Ambas matrices deben tener elementos de *tipo de referencia* o ambas matrices deben tener elementos de *tipo de valor* . Para obtener más información, vea [tipos de valor y tipos de referencia](../data-types/value-types-and-reference-types.md).

  - Si ambas matrices tienen elementos de tipo de valor, los tipos de datos de los elementos deben ser exactamente iguales. La única excepción a esto es que puede asignar una matriz de `Enum` elementos a una matriz del tipo base de ese `Enum` .

  - Si ambas matrices tienen elementos de tipo de referencia, el tipo de elemento de origen debe derivar del tipo de elemento de destino. En este caso, las dos matrices tienen la misma relación de herencia que sus elementos. Esto se denomina *covarianza de matriz*.

El compilador notifica un error si se infringen las reglas anteriores, por ejemplo, si los tipos de datos no son compatibles o los rangos no son iguales. Puede Agregar control de errores al código para asegurarse de que las matrices son compatibles antes de intentar una asignación. También puede usar la palabra clave del [operador TryCast](../../../language-reference/operators/trycast-operator.md) si desea evitar que se produzca una excepción.

## <a name="see-also"></a>Vea también

- [Matrices](index.md)
- [Solución de problemas de matrices](troubleshooting-arrays.md)
- [Instrucción Enum](../../../language-reference/statements/enum-statement.md)
- [Conversiones de matriz](../data-types/array-conversions.md)
