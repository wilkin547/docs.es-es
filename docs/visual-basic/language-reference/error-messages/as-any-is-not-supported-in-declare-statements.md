---
title: '&#39;Como cualquier&#39; no se admite en &#39;Declare&#39; instrucciones'
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 560ddc8674718f98f3e1a2f6d4facdb198f5e506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709869"
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39;Como cualquier&#39; no se admite en &#39;Declare&#39; instrucciones
El `Any` se utilizó el tipo de datos con `Declare` instrucciones en Visual Basic 6.0 y versiones anteriores para permitir el uso de argumentos que puede contener cualquier tipo de datos. Visual Basic admite sobrecargas, sin embargo y por lo que facilita la `Any` obsoleto del tipo de datos.  
  
 **Identificador de error:** BC30828  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Declare los parámetros del tipo específico que desea usar; Por ejemplo.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Use la <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo para especificar `As Any` cuando `Void*` se espera que el procedimiento que se llama.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Crear prototipos en código administrado](../../../framework/interop/creating-prototypes-in-managed-code.md)
