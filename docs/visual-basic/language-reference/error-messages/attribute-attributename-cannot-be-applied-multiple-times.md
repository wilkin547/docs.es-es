---
title: Atributo &#39; &lt;attributename&gt;&#39; no se puede aplicar varias veces
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 216cf54fd164ca95b6378517a679b5b54183559f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a><span data-ttu-id="baf8e-102">Atributo &#39; &lt;attributename&gt;&#39; no se puede aplicar varias veces</span><span class="sxs-lookup"><span data-stu-id="baf8e-102">Attribute &#39;&lt;attributename&gt;&#39; cannot be applied multiple times</span></span>
<span data-ttu-id="baf8e-103">El atributo solo puede aplicarse una vez.</span><span class="sxs-lookup"><span data-stu-id="baf8e-103">The attribute can only be applied once.</span></span> <span data-ttu-id="baf8e-104">El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.</span><span class="sxs-lookup"><span data-stu-id="baf8e-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="baf8e-105">**Id. de error:** BC30663</span><span class="sxs-lookup"><span data-stu-id="baf8e-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="baf8e-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="baf8e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="baf8e-107">Asegúrese de que el atributo solo se aplica una vez.</span><span class="sxs-lookup"><span data-stu-id="baf8e-107">Make sure the attribute is only applied once.</span></span>  
  
2.  <span data-ttu-id="baf8e-108">Si se usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar su `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="baf8e-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="baf8e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="baf8e-109">See Also</span></span>  
 <xref:System.AttributeUsageAttribute>  
 [<span data-ttu-id="baf8e-110">Creación de atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="baf8e-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="baf8e-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="baf8e-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
