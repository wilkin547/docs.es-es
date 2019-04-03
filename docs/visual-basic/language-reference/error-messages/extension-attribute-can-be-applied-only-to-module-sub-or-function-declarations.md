---
title: El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: a4561359e4d7cb0f6ebe44a5deb09b3374556ed8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826189"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="2de6b-102">El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'</span><span class="sxs-lookup"><span data-stu-id="2de6b-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>
<span data-ttu-id="2de6b-103">La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar.</span><span class="sxs-lookup"><span data-stu-id="2de6b-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="2de6b-104">El método de extensión puede ser un `Sub` procedimiento o un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2de6b-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="2de6b-105">Todos los métodos de extensión se deben marcar con el atributo de extensión, `<Extension()>`, desde el <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2de6b-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="2de6b-106">Si lo desea, se puede marcar un módulo que contiene un método de extensión de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="2de6b-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="2de6b-107">Ningún otro uso del atributo de extensión es válido.</span><span class="sxs-lookup"><span data-stu-id="2de6b-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="2de6b-108">**Identificador de error:** BC36550</span><span class="sxs-lookup"><span data-stu-id="2de6b-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2de6b-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2de6b-109">To correct this error</span></span>  
  
-   <span data-ttu-id="2de6b-110">Quite el atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="2de6b-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="2de6b-111">Vuelva a diseñar la extensión como un método, definido en un módulo envolvente.</span><span class="sxs-lookup"><span data-stu-id="2de6b-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2de6b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2de6b-112">Example</span></span>  
 <span data-ttu-id="2de6b-113">En el ejemplo siguiente se define un `Print` método para el `String` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="2de6b-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="2de6b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2de6b-114">See also</span></span>

- [<span data-ttu-id="2de6b-115">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="2de6b-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="2de6b-116">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="2de6b-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="2de6b-117">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2de6b-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
