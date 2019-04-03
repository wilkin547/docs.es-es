---
title: Assembly (Visual Basic)
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
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819260"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="74056-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74056-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="74056-103">Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="74056-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74056-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74056-104">Remarks</span></span>  
 <span data-ttu-id="74056-105">Muchos atributos pertenecen a un elemento de programación individual, como una clase o propiedad.</span><span class="sxs-lookup"><span data-stu-id="74056-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="74056-106">Aplicar este atributo adjuntando el bloque de atributos dentro de corchetes angulares (`< >`), directamente a la instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="74056-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="74056-107">Si un atributo se aplica no solo al siguiente elemento, sino a todo el ensamblado, coloque el bloque de atributos al principio del archivo de origen e identificar el atributo con el `Assembly` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="74056-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="74056-108">Si se aplica al módulo de ensamblado actual, usa el [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="74056-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="74056-109">También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo.vb, en cuyo caso no es necesario usar un bloque de atributos en el archivo de código fuente principal.</span><span class="sxs-lookup"><span data-stu-id="74056-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74056-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="74056-110">See also</span></span>

- [<span data-ttu-id="74056-111">Module \<keyword></span><span class="sxs-lookup"><span data-stu-id="74056-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="74056-112">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="74056-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
