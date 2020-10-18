---
title: Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 85798e6453bc6cea6174ecc536b35835865e0459
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163459"
---
# <a name="bc36647-and-bc36644-data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a>BC36647 y BC36644: los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos

Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos. Especificar los tipos de datos explícitamente puede corregir este error.

Este error se produce en caso de error en la resolución de sobrecarga. Se produce como un mensaje subordinado que indica por qué se ha eliminado un candidato de sobrecarga determinado. El mensaje de error explica que el compilador no puede usar la inferencia de tipos para buscar tipos de datos para los parámetros de tipo.

> [!NOTE]
> Al especificar argumentos no es una opción (por ejemplo, para operadores de consulta en expresiones de consulta), el mensaje de error aparece sin la segunda oración.

El código siguiente muestra el error.

```vb
Module Module1

    Sub Main()

        '' Not Valid.
        'OverloadedGenericMethod("Hello", "World")

    End Sub

    Sub OverloadedGenericMethod(Of T)(ByVal x As String,
                                      ByVal y As InterfaceExample(Of T))
    End Sub

    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,
                                         ByVal y As InterfaceExample(Of R))
    End Sub

End Module

Interface InterfaceExample(Of T)
End Interface
```

**Identificador de error:** BC36647 y BC36644

## <a name="to-correct-this-error"></a>Para corregir este error

Es posible que pueda especificar un tipo de datos para el parámetro o parámetros de tipo en lugar de confiar en la inferencia de tipo.

## <a name="see-also"></a>Vea también

- [Conversión de delegado flexible](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Generic Procedures in Visual Basic](../../programming-guide/language-features/data-types/generic-procedures.md)
- [Conversiones de tipos en Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
