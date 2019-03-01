---
title: "'As Any' no se admite en instrucciones 'Declare'"
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: b3fb3f208f3396f454388ec0c10406815fa957d8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974801"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a>'As Any' no se admite en instrucciones 'Declare'
El `Any` se utilizó el tipo de datos con `Declare` instrucciones en Visual Basic 6.0 y versiones anteriores para permitir el uso de argumentos que puede contener cualquier tipo de datos. Visual Basic admite sobrecargas, sin embargo y por lo que facilita la `Any` obsoleto del tipo de datos.  
  
 **Identificador de error:** BC30828  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Declare los parámetros del tipo específico que desea usar; Por ejemplo.  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2.  Use la <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo para especificar `As Any` cuando `Void*` se espera que el procedimiento que se llama.  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Crear prototipos en código administrado](../../../framework/interop/creating-prototypes-in-managed-code.md)
