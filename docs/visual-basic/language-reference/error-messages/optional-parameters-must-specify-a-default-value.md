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
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="9b6e5-102">BC30812: los parámetros opcionales deben especificar un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9b6e5-102">BC30812: Optional parameters must specify a default value</span></span>

<span data-ttu-id="9b6e5-103">Los parámetros opcionales deben proporcionar valores predeterminados que se pueden utilizar si un procedimiento que realiza la llamada no proporciona ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="9b6e5-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="9b6e5-104">**Identificador de error:** BC30812</span><span class="sxs-lookup"><span data-stu-id="9b6e5-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="9b6e5-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b6e5-105">Example</span></span>

<span data-ttu-id="9b6e5-106">En el ejemplo siguiente se genera BC30812:</span><span class="sxs-lookup"><span data-stu-id="9b6e5-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="9b6e5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9b6e5-107">To correct this error</span></span>

<span data-ttu-id="9b6e5-108">Especifique los valores predeterminados para los parámetros opcionales:</span><span class="sxs-lookup"><span data-stu-id="9b6e5-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="9b6e5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b6e5-109">See also</span></span>

- [<span data-ttu-id="9b6e5-110">Opcional</span><span class="sxs-lookup"><span data-stu-id="9b6e5-110">Optional</span></span>](../modifiers/optional.md)
