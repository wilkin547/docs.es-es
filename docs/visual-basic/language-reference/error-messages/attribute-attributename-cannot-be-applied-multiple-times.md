---
title: Atributo &#39; &lt;attributename&gt; &#39; no se puede aplicar varias veces
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 6609ce299799bc3c4b78d48478e99e4d4101dd72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565168"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a><span data-ttu-id="481d6-102">Atributo &#39; &lt;attributename&gt; &#39; no se puede aplicar varias veces</span><span class="sxs-lookup"><span data-stu-id="481d6-102">Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times</span></span>
<span data-ttu-id="481d6-103">El atributo solo puede aplicarse una vez.</span><span class="sxs-lookup"><span data-stu-id="481d6-103">The attribute can only be applied once.</span></span> <span data-ttu-id="481d6-104">El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.</span><span class="sxs-lookup"><span data-stu-id="481d6-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="481d6-105">**Identificador de error:** BC30663</span><span class="sxs-lookup"><span data-stu-id="481d6-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="481d6-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="481d6-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="481d6-107">Asegúrese de que el atributo sólo se aplica una vez.</span><span class="sxs-lookup"><span data-stu-id="481d6-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="481d6-108">Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar sus `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="481d6-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="481d6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="481d6-109">See also</span></span>
- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="481d6-110">Creación de atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="481d6-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="481d6-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="481d6-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
