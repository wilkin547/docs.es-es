---
title: '&#39;Extensión&#39; atributo se puede aplicar únicamente a &#39;módulo&#39;, &#39;Sub&#39;, o &#39;función&#39; declaraciones'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: d7f8829cb879d612711ac6bcc6bf4aa065fbe323
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587324"
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="944e7-102">&#39;Extensión&#39; atributo se puede aplicar únicamente a &#39;módulo&#39;, &#39;Sub&#39;, o &#39;función&#39; declaraciones</span><span class="sxs-lookup"><span data-stu-id="944e7-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="944e7-103">La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar.</span><span class="sxs-lookup"><span data-stu-id="944e7-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="944e7-104">El método de extensión puede ser un `Sub` procedimiento o una `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="944e7-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="944e7-105">Todos los métodos de extensión se deben marcar con el atributo de extensión, `<Extension()>`, desde el <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="944e7-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="944e7-106">Si lo desea, se puede marcar un módulo que contiene un método de extensión de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="944e7-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="944e7-107">Ningún otro uso del atributo de extensión es válido.</span><span class="sxs-lookup"><span data-stu-id="944e7-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="944e7-108">**Id. de error:** BC36550</span><span class="sxs-lookup"><span data-stu-id="944e7-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="944e7-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="944e7-109">To correct this error</span></span>  
  
-   <span data-ttu-id="944e7-110">Quite el atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="944e7-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="944e7-111">Vuelva a diseñar la extensión como un método, definido en un módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="944e7-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="944e7-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="944e7-112">Example</span></span>  
 <span data-ttu-id="944e7-113">En el ejemplo siguiente se define un `Print` método para el `String` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="944e7-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="944e7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="944e7-114">See Also</span></span>  
 [<span data-ttu-id="944e7-115">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="944e7-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="944e7-116">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="944e7-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="944e7-117">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="944e7-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
