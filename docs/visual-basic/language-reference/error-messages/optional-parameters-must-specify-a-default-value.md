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
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="c4d07-103">BC30812: los parámetros opcionales deben especificar un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c4d07-103">BC30812: Optional parameters must specify a default value</span></span>

<span data-ttu-id="c4d07-104">Los parámetros opcionales deben proporcionar valores predeterminados que se pueden utilizar si un procedimiento que realiza la llamada no proporciona ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="c4d07-104">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="c4d07-105">**Identificador de error:** BC30812</span><span class="sxs-lookup"><span data-stu-id="c4d07-105">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="c4d07-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4d07-106">Example</span></span>

<span data-ttu-id="c4d07-107">En el ejemplo siguiente se genera BC30812:</span><span class="sxs-lookup"><span data-stu-id="c4d07-107">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="c4d07-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c4d07-108">To correct this error</span></span>

<span data-ttu-id="c4d07-109">Especifique los valores predeterminados para los parámetros opcionales:</span><span class="sxs-lookup"><span data-stu-id="c4d07-109">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="c4d07-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4d07-110">See also</span></span>

- [<span data-ttu-id="c4d07-111">Opcional</span><span class="sxs-lookup"><span data-stu-id="c4d07-111">Optional</span></span>](../modifiers/optional.md)
