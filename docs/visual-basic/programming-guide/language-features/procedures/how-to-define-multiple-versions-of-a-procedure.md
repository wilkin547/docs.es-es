---
title: 'Cómo: Definir varias versiones de un procedimiento (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: a4d0c5bbb07dd5433ff62179fc10a6274bf19364
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649817"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Cómo: Definir varias versiones de un procedimiento (Visual Basic)
Puede definir un procedimiento en varias versiones por *sobrecarga* es decir, utilizando el mismo nombre pero con una lista de parámetros distinta para cada versión. El propósito de sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que distinguirlas por su nombre.  
  
 Para obtener más información, consulte [sobrecarga de procedimientos](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Para definir varias versiones de un procedimiento  
  
1.  Escribir una `Sub` o `Function` instrucción de declaración para cada versión del procedimiento que desee definir. Use el mismo nombre de procedimiento en cada declaración.  
  
2.  Preceden a la `Sub` o `Function` palabra clave en cada declaración con el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave. Se puede omitir `Overloads` en las declaraciones, pero si se incluyen en cualquiera de las declaraciones, debe incluirlo en todas las declaraciones.  
  
3.  Después de cada instrucción de declaración, escriba el código de procedimiento para controlar el caso concreto donde el código de llamada proporciona argumentos que coinciden con la lista de parámetros de la versión. No es necesario que probar los parámetros que el código que realiza la llamada ha suministrado. Visual Basic pasa el control a la versión correspondiente de su procedimiento.  
  
4.  Finalizar cada versión del procedimiento con el `End Sub` o `End Function` instrucción según corresponda.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un `Sub` procedimiento para registrar una transacción en el saldo de un cliente. Usa el `Overloads` palabra clave que se va a definir dos versiones del procedimiento, una que acepta el cliente con nombre y la otra por número de cuenta.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 El código de llamada puede obtener la identificación del cliente como un `String` o `Integer`y, a continuación, utilice la misma instrucción llamada en ambos casos.  
  
 Para obtener información sobre cómo llamar a estas versiones de la `post` procedimiento, consulte [Cómo: llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que cada una de las versiones sobrecargadas tiene el mismo nombre de procedimiento pero una lista de parámetros distinta.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Solución de problemas de procedimientos](./troubleshooting-procedures.md)  
 [Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)  
 [Resolución de sobrecargas](./overload-resolution.md)
