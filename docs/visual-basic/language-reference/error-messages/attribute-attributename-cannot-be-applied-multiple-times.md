---
title: No se puede aplicar el atributo '<attributename>' más de una vez
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 27cbe6d0043179c4a5d52baae06bad805f9d1d3a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162666"
---
# <a name="bc30663-attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="82bf7-102">BC30663: el atributo ' \<attributename> ' no se puede aplicar varias veces</span><span class="sxs-lookup"><span data-stu-id="82bf7-102">BC30663: Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="82bf7-103">El atributo solo se puede aplicar una vez.</span><span class="sxs-lookup"><span data-stu-id="82bf7-103">The attribute can only be applied once.</span></span> <span data-ttu-id="82bf7-104">El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.</span><span class="sxs-lookup"><span data-stu-id="82bf7-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>

 <span data-ttu-id="82bf7-105">**Identificador de error:** BC30663</span><span class="sxs-lookup"><span data-stu-id="82bf7-105">**Error ID:** BC30663</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="82bf7-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="82bf7-106">To correct this error</span></span>

1. <span data-ttu-id="82bf7-107">Asegúrese de que el atributo solo se aplica una vez.</span><span class="sxs-lookup"><span data-stu-id="82bf7-107">Make sure the attribute is only applied once.</span></span>

2. <span data-ttu-id="82bf7-108">Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar su `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="82bf7-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>

```vb
<AttributeUsage(AllowMultiple := True)>
```

## <a name="see-also"></a><span data-ttu-id="82bf7-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="82bf7-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="82bf7-110">Crear atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="82bf7-110">Creating Custom Attributes</span></span>](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="82bf7-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="82bf7-111">AttributeUsage</span></span>](../../programming-guide/concepts/attributes/attributeusage.md)
