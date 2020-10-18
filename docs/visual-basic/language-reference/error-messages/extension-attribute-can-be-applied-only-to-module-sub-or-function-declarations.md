---
title: El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: bd4d14721b93800831dbce897535b4f5956fe9c7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160755"
---
# <a name="bc36550-extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="5ac32-102">BC36550: el atributo ' Extension ' solo se puede aplicar a las declaraciones ' module ', ' sub ' o ' function '</span><span class="sxs-lookup"><span data-stu-id="5ac32-102">BC36550: 'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>

<span data-ttu-id="5ac32-103">La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar.</span><span class="sxs-lookup"><span data-stu-id="5ac32-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="5ac32-104">El método de extensión puede ser un `Sub` procedimiento o un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5ac32-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="5ac32-105">Todos los métodos de extensión se deben marcar con el atributo `<Extension()>` de extensión,, del <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5ac32-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="5ac32-106">Opcionalmente, un módulo que contiene un método de extensión se puede marcar de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="5ac32-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="5ac32-107">Ningún otro uso del atributo de extensión es válido.</span><span class="sxs-lookup"><span data-stu-id="5ac32-107">No other use of the extension attribute is valid.</span></span>

<span data-ttu-id="5ac32-108">**Identificador de error:** BC36550</span><span class="sxs-lookup"><span data-stu-id="5ac32-108">**Error ID:** BC36550</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5ac32-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5ac32-109">To correct this error</span></span>

- <span data-ttu-id="5ac32-110">Quite el atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="5ac32-110">Remove the extension attribute.</span></span>

- <span data-ttu-id="5ac32-111">Rediseñe la extensión como un método, definido en un módulo envolvente.</span><span class="sxs-lookup"><span data-stu-id="5ac32-111">Redesign your extension as a method, defined in an enclosing module.</span></span>

## <a name="example"></a><span data-ttu-id="5ac32-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ac32-112">Example</span></span>

<span data-ttu-id="5ac32-113">En el ejemplo siguiente se define un `Print` método para el `String` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5ac32-113">The following example defines a `Print` method for the `String` data type.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5ac32-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ac32-114">See also</span></span>

- [<span data-ttu-id="5ac32-115">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="5ac32-115">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="5ac32-116">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="5ac32-116">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="5ac32-117">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5ac32-117">Module Statement</span></span>](../statements/module-statement.md)
