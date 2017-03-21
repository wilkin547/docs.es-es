---
title: "Cómo: definir varias versiones de un procedimiento (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 0228083ce00a0f552227fd7ae8f0f5a24f65148e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Cómo: Definir varias versiones de un procedimiento (Visual Basic)
Puede definir un procedimiento en varias versiones por *sobrecarga* que, con el mismo nombre pero con una lista de parámetros distinta para cada versión. El propósito de sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que distinguirlas por su nombre.  
  
 Para obtener más información, consulte [sobrecarga de procedimientos](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Para definir varias versiones de un procedimiento  
  
1.  Escribir una `Sub` o `Function` instrucción de declaración para cada versión del procedimiento que desee definir. Utilice el mismo nombre de procedimiento en cada declaración.  
  
2.  Preceder a la `Sub` o `Function` palabra clave en cada declaración con la [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) (palabra clave). Se puede omitir `Overloads` en las declaraciones, pero si se incluyen en cualquiera de las declaraciones, debe incluirlo en cada declaración.  
  
3.  Después de cada instrucción de declaración, escriba el código de procedimiento para controlar el caso donde el código de llamada proporciona argumentos que coinciden con la lista de parámetros de la versión. No es necesario que probar los parámetros que el código llamado ha suministrado. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]pasa el control a la versión correspondiente de su procedimiento.  
  
4.  Finalice cada versión del procedimiento con el `End Sub` o `End Function` instrucción según corresponda.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un `Sub` procedimiento para registrar una transacción en el saldo de un cliente. Utiliza la `Overloads` (palabra clave) para definir dos versiones del procedimiento, una que acepta el cliente por nombre y el otro por número de cuenta.  
  
 [!code-vb[VbVbcnProcedures&#72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 El código de llamada puede obtener la identificación del cliente como un `String` o `Integer`y, a continuación, utilice la misma instrucción llamada en ambos casos.  
  
 Para obtener información sobre cómo llamar a estas versiones de la `post` procedimiento, consulte [Cómo: llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que cada una de las versiones sobrecargadas tiene el mismo nombre de procedimiento pero una lista de parámetros distinta.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Procedimientos de solución de problemas](./troubleshooting-procedures.md)   
 [Cómo: sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)   
 [Resolución de sobrecargas](./overload-resolution.md)
