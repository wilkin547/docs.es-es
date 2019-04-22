---
title: Module <keyword> (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: f6ded1184aedf1702f4b6e5eebb85709cf8e39f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814281"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="0e3d3-102">Módulo \<palabra clave > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e3d3-102">Module \<keyword> (Visual Basic)</span></span>
<span data-ttu-id="0e3d3-103">Especifica que un atributo al principio de un archivo de código fuente se aplica al módulo de ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="0e3d3-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e3d3-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e3d3-104">Remarks</span></span>  
 <span data-ttu-id="0e3d3-105">Muchos atributos pertenecen a un elemento de programación individual, como una clase o propiedad.</span><span class="sxs-lookup"><span data-stu-id="0e3d3-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="0e3d3-106">Aplicar este atributo adjuntando el bloque de atributos dentro de corchetes angulares (`< >`), directamente a la instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="0e3d3-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="0e3d3-107">Si un atributo se aplica no solo para el elemento siguiente pero al módulo de ensamblado actual, coloque el bloque de atributos al principio del archivo de origen e identificar el atributo con el `Module` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="0e3d3-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="0e3d3-108">Si se aplica a todo el ensamblado, usa el [ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="0e3d3-108">If it applies to the entire assembly, you use the [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="0e3d3-109">El `Module` modificador no es igual que el [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0e3d3-109">The `Module` modifier is not the same as the [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e3d3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e3d3-110">See also</span></span>

- [<span data-ttu-id="0e3d3-111">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="0e3d3-111">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)
- [<span data-ttu-id="0e3d3-112">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0e3d3-112">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="0e3d3-113">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="0e3d3-113">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
