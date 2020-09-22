---
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
ms.openlocfilehash: 34d6b94f31336e3e99b8ca981a9c4899e5a3d912
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875527"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="1f6d1-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f6d1-102">Assembly (Visual Basic)</span></span>

<span data-ttu-id="1f6d1-103">Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f6d1-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f6d1-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f6d1-104">Remarks</span></span>  

 <span data-ttu-id="1f6d1-105">Muchos atributos pertenecen a un elemento de programación individual, como una clase o una propiedad.</span><span class="sxs-lookup"><span data-stu-id="1f6d1-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="1f6d1-106">Este atributo se aplica asociando el bloque de atributos, entre corchetes angulares ( `< >` ), directamente a la instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="1f6d1-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="1f6d1-107">Si un atributo pertenece no solo al elemento siguiente, sino a todo el ensamblado, coloca el bloque de atributos al principio del archivo de código fuente e identifica el atributo con la `Assembly` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1f6d1-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="1f6d1-108">Si se aplica al módulo de ensamblado actual, se usa la palabra clave [Module](module-keyword.md) .</span><span class="sxs-lookup"><span data-stu-id="1f6d1-108">If it applies to the current assembly module, you use the [Module](module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="1f6d1-109">También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo. VB, en cuyo caso no es necesario usar un bloque de atributos en el archivo de código fuente principal.</span><span class="sxs-lookup"><span data-stu-id="1f6d1-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f6d1-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f6d1-110">See also</span></span>

- [<span data-ttu-id="1f6d1-111">Destina \<keyword></span><span class="sxs-lookup"><span data-stu-id="1f6d1-111">Module \<keyword></span></span>](module-keyword.md)
- [<span data-ttu-id="1f6d1-112">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="1f6d1-112">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
