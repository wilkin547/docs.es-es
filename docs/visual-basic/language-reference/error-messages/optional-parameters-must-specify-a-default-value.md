---
title: Los parámetros opcionales deben especificar un valor predeterminado
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 3718fe5c42c8af0948f3b5cb0d120c6876c6f98f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162458"
---
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a>BC30812: los parámetros opcionales deben especificar un valor predeterminado.

Los parámetros opcionales deben proporcionar valores predeterminados que se pueden utilizar si un procedimiento que realiza la llamada no proporciona ningún parámetro.

**Identificador de error:** BC30812

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se genera BC30812:

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a>Para corregir este error

Especifique los valores predeterminados para los parámetros opcionales:

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a>Vea también

- [Opcional](../modifiers/optional.md)
