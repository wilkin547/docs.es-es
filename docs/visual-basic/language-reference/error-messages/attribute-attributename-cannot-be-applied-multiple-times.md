---
title: No se puede aplicar el atributo '<attributename>' más de una vez
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 14145f165adf5ccd20298a70ca5596488b488b0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409964"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>No se puede aplicar el atributo '\<attributename>' más de una vez

El atributo solo se puede aplicar una vez. El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.  
  
 **Identificador de error:** BC30663  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que el atributo solo se aplica una vez.  
  
2. Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar su `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.AttributeUsageAttribute>
- [Crear atributos personalizados](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../programming-guide/concepts/attributes/attributeusage.md)
