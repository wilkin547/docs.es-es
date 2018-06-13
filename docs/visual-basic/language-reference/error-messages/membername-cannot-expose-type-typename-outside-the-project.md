---
title: '&#39;&lt;MemberName&gt; &#39; no se puede exponer el tipo &#39; &lt;typename&gt; &#39; fuera del proyecto a través de &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 36add48ebee2d1804921eeeec0b59cdd4cbafecc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588098"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="d7e4c-102">&#39;&lt;MemberName&gt; &#39; no se puede exponer el tipo &#39; &lt;typename&gt; &#39; fuera del proyecto a través de &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="d7e4c-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="d7e4c-103">Una variable, parámetro de procedimiento o valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.</span><span class="sxs-lookup"><span data-stu-id="d7e4c-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="d7e4c-104">La estructura de código siguiente muestra una situación que genera este error.</span><span class="sxs-lookup"><span data-stu-id="d7e4c-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="d7e4c-105">Un tipo que se declara `Protected`, `Friend`, `Protected Friend`, o `Private` está diseñado para tener acceso limitado fuera de su contexto de declaración.</span><span class="sxs-lookup"><span data-stu-id="d7e4c-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="d7e4c-106">Lo usa como los datos de tipo de una variable con acceso menos restringido iría contra este propósito.</span><span class="sxs-lookup"><span data-stu-id="d7e4c-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="d7e4c-107">En el código anterior de esqueleto, `exposedVar` es `Public` y expondría `privateClass` al código que no debe tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="d7e4c-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="d7e4c-108">**Id. de error:** BC30909</span><span class="sxs-lookup"><span data-stu-id="d7e4c-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d7e4c-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d7e4c-109">To correct this error</span></span>  
  
-   <span data-ttu-id="d7e4c-110">Cambiar el nivel de acceso de la variable, el parámetro de procedimiento o la función devuelve para que sea al menos tan restrictiva como el nivel de acceso de su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d7e4c-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e4c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7e4c-111">See Also</span></span>  
 [<span data-ttu-id="d7e4c-112">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7e4c-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
