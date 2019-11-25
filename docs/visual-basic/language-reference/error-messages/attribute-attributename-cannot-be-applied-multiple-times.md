---
title: No se puede aplicar el atributo '<attributename>' más de una vez
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968223"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>El atributo '\<attributeName > ' no se puede aplicar varias veces

El atributo solo se puede aplicar una vez. El atributo `AttributeUsage` determina si un atributo se puede aplicar más de una vez.  
  
 **Identificador de error:** BC30663  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que el atributo solo se aplica una vez.  
  
2. Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar su `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.AttributeUsageAttribute>
- [Creación de atributos personalizados](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
