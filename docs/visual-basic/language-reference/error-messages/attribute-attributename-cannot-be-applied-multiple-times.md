---
title: Atributo &#39; &lt;attributename&gt; &#39; no se puede aplicar varias veces
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: df97a4e391406661db98eb1c958c0e12e45b6c49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584864"
---
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>Atributo &#39; &lt;attributename&gt; &#39; no se puede aplicar varias veces
El atributo solo puede aplicarse una vez. El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.  
  
 **Id. de error:** BC30663  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el atributo solo se aplica una vez.  
  
2.  Si se usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar su `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.AttributeUsageAttribute>  
 [Creación de atributos personalizados](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
