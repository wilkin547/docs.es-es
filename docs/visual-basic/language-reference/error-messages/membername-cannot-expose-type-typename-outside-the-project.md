---
title: "'<membername>' no puede exponer el tipo '<typename>' fuera del proyecto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 729a9f385d94412469d318cb804d216827eeb0fd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397290"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="a3711-102">'\<membername>' no puede exponer el tipo '\<typename>' fuera del proyecto mediante \<containertype> '\<containertypename>'</span><span class="sxs-lookup"><span data-stu-id="a3711-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="a3711-103">Una variable, un parámetro de procedimiento o un valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.</span><span class="sxs-lookup"><span data-stu-id="a3711-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="a3711-104">El código esqueleto siguiente muestra una situación que genera este error.</span><span class="sxs-lookup"><span data-stu-id="a3711-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="a3711-105">Un tipo que se declara `Protected` , `Friend` , `Protected Friend` o `Private` está pensado para tener acceso limitado fuera del contexto de declaración.</span><span class="sxs-lookup"><span data-stu-id="a3711-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="a3711-106">Si se usa como el tipo de datos de una variable con acceso menos restringido, se anularía este propósito.</span><span class="sxs-lookup"><span data-stu-id="a3711-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="a3711-107">En el código de esqueleto anterior, `exposedVar` es `Public` y se expondría `privateClass` al código que no debe tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="a3711-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="a3711-108">**Identificador de error:** BC30909</span><span class="sxs-lookup"><span data-stu-id="a3711-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a3711-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a3711-109">To correct this error</span></span>  
  
- <span data-ttu-id="a3711-110">Cambie el nivel de acceso de la variable, el parámetro de procedimiento o la función que debe ser al menos tan restrictivo como el nivel de acceso de su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="a3711-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3711-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3711-111">See also</span></span>

- [<span data-ttu-id="a3711-112">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3711-112">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
