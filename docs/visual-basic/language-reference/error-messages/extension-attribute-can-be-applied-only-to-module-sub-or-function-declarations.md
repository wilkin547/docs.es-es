---
title: El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 95a67a552efacf9e77dc3ebc3e0187817a6d82e2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698586"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="c7c25-102">El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'</span><span class="sxs-lookup"><span data-stu-id="c7c25-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>
<span data-ttu-id="c7c25-103">La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar.</span><span class="sxs-lookup"><span data-stu-id="c7c25-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="c7c25-104">El método de extensión puede ser un procedimiento `Sub` o un procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="c7c25-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="c7c25-105">Todos los métodos de extensión se deben marcar con el atributo de extensión, `<Extension()>`, del espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c7c25-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="c7c25-106">Opcionalmente, un módulo que contiene un método de extensión se puede marcar de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="c7c25-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="c7c25-107">Ningún otro uso del atributo de extensión es válido.</span><span class="sxs-lookup"><span data-stu-id="c7c25-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="c7c25-108">**IDENTIFICADOR de error:** BC36550</span><span class="sxs-lookup"><span data-stu-id="c7c25-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c7c25-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c7c25-109">To correct this error</span></span>  
  
- <span data-ttu-id="c7c25-110">Quite el atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="c7c25-110">Remove the extension attribute.</span></span>  
  
- <span data-ttu-id="c7c25-111">Rediseñe la extensión como un método, definido en un módulo envolvente.</span><span class="sxs-lookup"><span data-stu-id="c7c25-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7c25-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7c25-112">Example</span></span>  
 <span data-ttu-id="c7c25-113">En el ejemplo siguiente se define un método `Print` para el tipo de datos `String`.</span><span class="sxs-lookup"><span data-stu-id="c7c25-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c7c25-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7c25-114">See also</span></span>

- [<span data-ttu-id="c7c25-115">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="c7c25-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="c7c25-116">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="c7c25-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="c7c25-117">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c7c25-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
