---
title: "No se puede aplicar la resolución de sobrecarga enlazada a &#39; &lt;nombreProcedimiento&gt;&#39; porque la instancia de acceso es un tipo de interfaz"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb7f8a9f6eadfc9fd856ea57d362b43d25ff81a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="f9ddf-102">No se puede aplicar la resolución de sobrecarga enlazada a &#39; &lt;nombreProcedimiento&gt;&#39; porque la instancia de acceso es un tipo de interfaz</span><span class="sxs-lookup"><span data-stu-id="f9ddf-102">Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type</span></span>
<span data-ttu-id="f9ddf-103">El compilador está intentando resolver una referencia a una propiedad o procedimiento sobrecargados, pero se produce un error en la referencia porque es un argumento de tipo `Object` y el objeto que hace referencia tiene el tipo de datos de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="f9ddf-104">El `Object` argumento hace que el compilador para resolver la referencia como en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="f9ddf-105">En estas circunstancias, el compilador resuelve la sobrecarga a través de la clase de implementación en lugar de a través de la interfaz subyacente.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="f9ddf-106">Si la clase cambia el nombre de una de las versiones sobrecargadas, el compilador no tiene en cuenta que la versión sea una sobrecarga porque su nombre es distinto.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="f9ddf-107">Esto hace al compilador que omita la versión cuyo nombre ha cambiado cuando podría haber sido la opción correcta para resolver la referencia.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="f9ddf-108">**Id. de error:** BC30933</span><span class="sxs-lookup"><span data-stu-id="f9ddf-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9ddf-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f9ddf-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f9ddf-110">Use `CType` convertir el argumento de `Object` al tipo especificado por la firma de la sobrecarga que desea llamar.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="f9ddf-111">Tenga en cuenta que no sirve para convertir el objeto que hace referencia a la interfaz subyacente.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="f9ddf-112">Primero debe convertir el argumento para evitar este error.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9ddf-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9ddf-113">Example</span></span>  
 <span data-ttu-id="f9ddf-114">En el ejemplo siguiente se muestra una llamada a una sobrecarga `Sub` procedimiento que se produzca este error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f9ddf-115">En el ejemplo anterior, si el compilador permite que la llamada a `s1` tal y como se escribe, la resolución tendrá lugar a través de la clase `c1` en lugar de la interfaz `i1`.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="f9ddf-116">Esto significaría que el compilador no consideraría `s2` porque su nombre es distinto en `c1`, aunque es la opción correcta tal como se define por `i1`.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="f9ddf-117">Puede corregir el error cambiando la llamada a cualquiera de las siguientes líneas de código:</span><span class="sxs-lookup"><span data-stu-id="f9ddf-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="f9ddf-118">Cada una de las líneas de código anteriores convierte de forma explícita el `Object` variable `o1` a uno de los tipos de parámetro definidos para las sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="f9ddf-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ddf-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9ddf-119">See Also</span></span>  
 [<span data-ttu-id="f9ddf-120">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="f9ddf-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="f9ddf-121">Resolución de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="f9ddf-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [<span data-ttu-id="f9ddf-122">Función CType</span><span class="sxs-lookup"><span data-stu-id="f9ddf-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
