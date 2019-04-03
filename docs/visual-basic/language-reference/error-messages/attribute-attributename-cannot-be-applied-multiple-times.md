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
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Atributo '\<attributename >' no se puede aplicar varias veces
El atributo solo puede aplicarse una vez. El `AttributeUsage` atributo determina si un atributo se puede aplicar más de una vez.  
  
 **Identificador de error:** BC30663  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el atributo sólo se aplica una vez.  
  
2.  Si usa atributos personalizados desarrollados por usted, considere la posibilidad de cambiar sus `AttributeUsage` atributo para permitir el uso de varios atributos, como en el ejemplo siguiente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.AttributeUsageAttribute>
- [Creación de atributos personalizados](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
