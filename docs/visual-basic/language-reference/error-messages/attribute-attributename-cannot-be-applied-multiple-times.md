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
# <a name="attribute-39ltattributenamegt39-cannot-be-applied-multiple-times"></a>Atributo &#39; &lt;attributename&gt;&#39; no se puede aplicar varias veces
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
