---
description: 'Más información acerca de: module <keyword> (Visual Basic)'
title: Destina <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 1bd25b00b41f5da4fca535220fe4e1694c81baca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640698"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="8f22c-103">Module \<keyword> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f22c-103">Module \<keyword> (Visual Basic)</span></span>

<span data-ttu-id="8f22c-104">Especifica que un atributo al principio de un archivo de código fuente se aplica al módulo de ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="8f22c-104">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f22c-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8f22c-105">Remarks</span></span>  

 <span data-ttu-id="8f22c-106">Muchos atributos pertenecen a un elemento de programación individual, como una clase o una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8f22c-106">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="8f22c-107">Este atributo se aplica asociando el bloque de atributos, entre corchetes angulares ( `< >` ), directamente a la instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="8f22c-107">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="8f22c-108">Si un atributo pertenece no solo al siguiente elemento, sino al módulo de ensamblado actual, coloca el bloque de atributos al principio del archivo de código fuente e identifica el atributo con la `Module` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="8f22c-108">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="8f22c-109">Si se aplica a todo el ensamblado, se utiliza la palabra clave [Assembly](assembly.md) .</span><span class="sxs-lookup"><span data-stu-id="8f22c-109">If it applies to the entire assembly, you use the [Assembly](assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="8f22c-110">El `Module` modificador no es lo mismo que la [instrucción del módulo](../statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8f22c-110">The `Module` modifier is not the same as the [Module Statement](../statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f22c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f22c-111">See also</span></span>

- [<span data-ttu-id="8f22c-112">Ensamblaje</span><span class="sxs-lookup"><span data-stu-id="8f22c-112">Assembly</span></span>](assembly.md)
- [<span data-ttu-id="8f22c-113">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8f22c-113">Module Statement</span></span>](../statements/module-statement.md)
- [<span data-ttu-id="8f22c-114">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="8f22c-114">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
