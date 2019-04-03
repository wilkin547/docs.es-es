---
title: No se puede aplicar el atributo '<attributename>' más de una vez
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: fe72e7a14723bcfa429ce80b15dbc22b256774aa
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843596"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="75567-102">Atributo '\<attributename >' no se puede aplicar varias veces</span><span class="sxs-lookup"><span data-stu-id="75567-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>
<span data-ttu-id="75567-103">El atributo solo puede aplicarse una vez.</span><span class="sxs-lookup"><span data-stu-id="75567-103">The attribute can only be applied once.</span></span> <span data-ttu-id="75567-104">El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.</span><span class="sxs-lookup"><span data-stu-id="75567-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="75567-105">**Identificador de error:** BC30663</span><span class="sxs-lookup"><span data-stu-id="75567-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="75567-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="75567-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="75567-107">Asegúrese de que el atributo sólo se aplica una vez.</span><span class="sxs-lookup"><span data-stu-id="75567-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="75567-108">Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar sus `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="75567-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="75567-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="75567-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="75567-110">Creación de atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="75567-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="75567-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="75567-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
