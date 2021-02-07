---
description: 'Más información acerca de: Assembly (Visual Basic)'
title: Ensamblado
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 60b8ce4ed2b8b5cb7deeabb702c33d1e561d765f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701188"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="c729e-103">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c729e-103">Assembly (Visual Basic)</span></span>

<span data-ttu-id="c729e-104">Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c729e-104">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c729e-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c729e-105">Remarks</span></span>  

 <span data-ttu-id="c729e-106">Muchos atributos pertenecen a un elemento de programación individual, como una clase o una propiedad.</span><span class="sxs-lookup"><span data-stu-id="c729e-106">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="c729e-107">Este atributo se aplica asociando el bloque de atributos, entre corchetes angulares ( `< >` ), directamente a la instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="c729e-107">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="c729e-108">Si un atributo pertenece no solo al elemento siguiente, sino a todo el ensamblado, coloca el bloque de atributos al principio del archivo de código fuente e identifica el atributo con la `Assembly` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="c729e-108">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="c729e-109">Si se aplica al módulo de ensamblado actual, se usa la palabra clave [Module](module-keyword.md) .</span><span class="sxs-lookup"><span data-stu-id="c729e-109">If it applies to the current assembly module, you use the [Module](module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="c729e-110">También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo. VB, en cuyo caso no es necesario usar un bloque de atributos en el archivo de código fuente principal.</span><span class="sxs-lookup"><span data-stu-id="c729e-110">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c729e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c729e-111">See also</span></span>

- [<span data-ttu-id="c729e-112">Destina \<keyword></span><span class="sxs-lookup"><span data-stu-id="c729e-112">Module \<keyword></span></span>](module-keyword.md)
- [<span data-ttu-id="c729e-113">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="c729e-113">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
