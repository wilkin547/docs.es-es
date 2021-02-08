---
description: "Más información sobre: BC30909: ' <membername> ' no puede exponer el tipo ' <typename> ' fuera del proyecto mediante <containertype> '<containertypename>"
title: "'<membername>' no puede exponer el tipo '<typename>' fuera del proyecto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: e2cc1d950b646bb787dfe714c39efea78a530129
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795864"
---
# <a name="bc30909-membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="1beca-103">BC30909: ' \<membername> ' no puede exponer el tipo ' \<typename> ' fuera del proyecto a través de \<containertype> ' \<containertypename> '</span><span class="sxs-lookup"><span data-stu-id="1beca-103">BC30909: '\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>

<span data-ttu-id="1beca-104">Una variable, un parámetro de procedimiento o un valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.</span><span class="sxs-lookup"><span data-stu-id="1beca-104">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>

 <span data-ttu-id="1beca-105">El código esqueleto siguiente muestra una situación que genera este error.</span><span class="sxs-lookup"><span data-stu-id="1beca-105">The following skeleton code shows a situation that generates this error.</span></span>

```vb
Private Class privateClass
End Class
Public Class mainClass
    Public exposedVar As New privateClass
End Class
```

 <span data-ttu-id="1beca-106">Un tipo que se declara `Protected` , `Friend` , `Protected Friend` o `Private` está pensado para tener acceso limitado fuera del contexto de declaración.</span><span class="sxs-lookup"><span data-stu-id="1beca-106">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="1beca-107">Si se usa como el tipo de datos de una variable con acceso menos restringido, se anularía este propósito.</span><span class="sxs-lookup"><span data-stu-id="1beca-107">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="1beca-108">En el código de esqueleto anterior, `exposedVar` es `Public` y se expondría `privateClass` al código que no debe tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="1beca-108">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>

 <span data-ttu-id="1beca-109">**Identificador de error:** BC30909</span><span class="sxs-lookup"><span data-stu-id="1beca-109">**Error ID:** BC30909</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1beca-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1beca-110">To correct this error</span></span>

- <span data-ttu-id="1beca-111">Cambie el nivel de acceso de la variable, el parámetro de procedimiento o la función que debe ser al menos tan restrictivo como el nivel de acceso de su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="1beca-111">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="1beca-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1beca-112">See also</span></span>

- [<span data-ttu-id="1beca-113">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1beca-113">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
