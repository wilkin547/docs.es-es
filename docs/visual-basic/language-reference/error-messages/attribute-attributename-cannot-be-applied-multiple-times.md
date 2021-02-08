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
# <a name="bc30663-attribute-attributename-cannot-be-applied-multiple-times"></a>BC30663: el atributo ' \<attributename> ' no se puede aplicar varias veces

El atributo solo se puede aplicar una vez. El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.

 **Identificador de error:** BC30663

## <a name="to-correct-this-error"></a>Para corregir este error

1. Asegúrese de que el atributo solo se aplica una vez.

2. Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar su `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.

```vb
<AttributeUsage(AllowMultiple := True)>
```

## <a name="see-also"></a>Vea también

- <xref:System.AttributeUsageAttribute>
- [Crear atributos personalizados](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../programming-guide/concepts/attributes/attributeusage.md)
