---
description: "Más información acerca de: BC30663: el atributo ' <attributename> ' no se puede aplicar varias veces"
title: No se puede aplicar el atributo '<attributename>' más de una vez
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 84b77111a7401eb6f30eb7cd167f4b5689f33e77
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797151"
---
# <a name="bc30663-attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="d5c63-103">BC30663: el atributo ' \<attributename> ' no se puede aplicar varias veces</span><span class="sxs-lookup"><span data-stu-id="d5c63-103">BC30663: Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="d5c63-104">El atributo solo se puede aplicar una vez.</span><span class="sxs-lookup"><span data-stu-id="d5c63-104">The attribute can only be applied once.</span></span> <span data-ttu-id="d5c63-105">El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.</span><span class="sxs-lookup"><span data-stu-id="d5c63-105">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>

 <span data-ttu-id="d5c63-106">**Identificador de error:** BC30663</span><span class="sxs-lookup"><span data-stu-id="d5c63-106">**Error ID:** BC30663</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d5c63-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d5c63-107">To correct this error</span></span>

1. <span data-ttu-id="d5c63-108">Asegúrese de que el atributo solo se aplica una vez.</span><span class="sxs-lookup"><span data-stu-id="d5c63-108">Make sure the attribute is only applied once.</span></span>

2. <span data-ttu-id="d5c63-109">Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar su `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5c63-109">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>

```vb
<AttributeUsage(AllowMultiple := True)>
```

## <a name="see-also"></a><span data-ttu-id="d5c63-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5c63-110">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="d5c63-111">Crear atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="d5c63-111">Creating Custom Attributes</span></span>](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="d5c63-112">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="d5c63-112">AttributeUsage</span></span>](../../programming-guide/concepts/attributes/attributeusage.md)
