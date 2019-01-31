---
title: "'<membername>' no puede exponer el tipo '<typename>' fuera del proyecto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 03767501488a395073f925e27adea439751c0de6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265069"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="abdcb-102">'\<membername >' no puede exponer el tipo '\<typename >' fuera del proyecto mediante \<containertype > '\<containertypename >'</span><span class="sxs-lookup"><span data-stu-id="abdcb-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="abdcb-103">Una variable, parámetro de procedimiento o valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.</span><span class="sxs-lookup"><span data-stu-id="abdcb-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="abdcb-104">La estructura de código siguiente muestra una situación que genera este error.</span><span class="sxs-lookup"><span data-stu-id="abdcb-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="abdcb-105">Un tipo que se declara `Protected`, `Friend`, `Protected Friend`, o `Private` está diseñado para tener acceso limitado fuera de su contexto de declaración.</span><span class="sxs-lookup"><span data-stu-id="abdcb-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="abdcb-106">Lo utilizan como los datos de tipo de una variable con acceso menos restringido iría con este fin.</span><span class="sxs-lookup"><span data-stu-id="abdcb-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="abdcb-107">En el código anterior de esqueleto, `exposedVar` es `Public` y expondría `privateClass` al código que no debería tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="abdcb-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="abdcb-108">**Identificador de error:** BC30909</span><span class="sxs-lookup"><span data-stu-id="abdcb-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="abdcb-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="abdcb-109">To correct this error</span></span>  
  
-   <span data-ttu-id="abdcb-110">Cambiar el nivel de acceso de la variable, parámetro de procedimiento o función que se devuelven para que sea al menos tan restrictiva como el nivel de acceso de su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="abdcb-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abdcb-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="abdcb-111">See also</span></span>
- [<span data-ttu-id="abdcb-112">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abdcb-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
