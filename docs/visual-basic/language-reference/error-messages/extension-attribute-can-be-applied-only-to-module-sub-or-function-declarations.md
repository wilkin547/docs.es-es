---
description: "Más información sobre: BC36550: el atributo ' Extension ' solo se puede aplicar a las declaraciones ' module ', ' sub ' o ' function '"
title: El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: f0c87de34238974229bc572a0f634a16e8cc78d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796319"
---
# <a name="bc36550-extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="8abfe-103">BC36550: el atributo ' Extension ' solo se puede aplicar a las declaraciones ' module ', ' sub ' o ' function '</span><span class="sxs-lookup"><span data-stu-id="8abfe-103">BC36550: 'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>

<span data-ttu-id="8abfe-104">La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar.</span><span class="sxs-lookup"><span data-stu-id="8abfe-104">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="8abfe-105">El método de extensión puede ser un `Sub` procedimiento o un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8abfe-105">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="8abfe-106">Todos los métodos de extensión se deben marcar con el atributo `<Extension()>` de extensión,, del <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8abfe-106">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="8abfe-107">Opcionalmente, un módulo que contiene un método de extensión se puede marcar de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="8abfe-107">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="8abfe-108">Ningún otro uso del atributo de extensión es válido.</span><span class="sxs-lookup"><span data-stu-id="8abfe-108">No other use of the extension attribute is valid.</span></span>

<span data-ttu-id="8abfe-109">**Identificador de error:** BC36550</span><span class="sxs-lookup"><span data-stu-id="8abfe-109">**Error ID:** BC36550</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8abfe-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8abfe-110">To correct this error</span></span>

- <span data-ttu-id="8abfe-111">Quite el atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="8abfe-111">Remove the extension attribute.</span></span>

- <span data-ttu-id="8abfe-112">Rediseñe la extensión como un método, definido en un módulo envolvente.</span><span class="sxs-lookup"><span data-stu-id="8abfe-112">Redesign your extension as a method, defined in an enclosing module.</span></span>

## <a name="example"></a><span data-ttu-id="8abfe-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8abfe-113">Example</span></span>

<span data-ttu-id="8abfe-114">En el ejemplo siguiente se define un `Print` método para el `String` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="8abfe-114">The following example defines a `Print` method for the `String` data type.</span></span>

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a><span data-ttu-id="8abfe-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8abfe-115">See also</span></span>

- [<span data-ttu-id="8abfe-116">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="8abfe-116">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="8abfe-117">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="8abfe-117">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="8abfe-118">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8abfe-118">Module Statement</span></span>](../statements/module-statement.md)
