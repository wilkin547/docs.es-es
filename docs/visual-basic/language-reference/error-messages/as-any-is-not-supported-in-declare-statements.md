---
title: '&quot;As Any&quot; no se admite en instrucciones &quot;Declare&quot; | Documentos de Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
dev_langs:
- VB
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fb179ae938d4c132f61e2076248729f7ea15a13f
ms.lasthandoff: 03/13/2017

---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>'As Any' no se admite en instrucciones 'Declare'
El `Any` se utilizó el tipo de datos con `Declare` instrucciones en Visual Basic 6.0 y versiones anteriores para permitir el uso de argumentos que puede contener cualquier tipo de datos. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]admite la sobrecarga, sin embargo y así facilita el `Any` obsoleta de tipo de datos.  
  
 **Id. de error:** BC30828  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Declare los parámetros del tipo específico que desea usar; Por ejemplo.  
  
     [!code-vb[VbVbalrStatements&#95;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Utilice la <xref:System.Runtime.InteropServices.MarshalAsAttribute>atributo para especificar `As Any` cuando `Void*` esperado por el procedimiento que se llama.</xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
     [!code-vb[VbVbalrStatements&#96;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Crear prototipos en código administrado](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)
