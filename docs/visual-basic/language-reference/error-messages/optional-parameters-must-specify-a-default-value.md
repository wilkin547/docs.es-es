---
description: 'Más información sobre: BC30812: los parámetros opcionales deben especificar un valor predeterminado.'
title: Los parámetros opcionales deben especificar un valor predeterminado
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 1cbed1c0f1297ecacdae94d9234d18a3d268f487
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795539"
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
