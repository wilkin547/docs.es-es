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
