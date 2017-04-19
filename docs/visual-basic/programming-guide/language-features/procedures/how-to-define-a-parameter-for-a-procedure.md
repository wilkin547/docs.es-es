---
title: "Cómo: definir un parámetro para un procedimiento (Visual Basic) | Documentos de Microsoft"
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
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
ms.openlocfilehash: 9fb9ad244499039c1768ff97f071168e0a0842e4
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Cómo: Definir parámetros para un procedimiento (Visual Basic)
Un *parámetro* permite que el código que realiza la llamada pasar un valor al procedimiento cuando éste lo invoca. Declarar cada parámetro de un procedimiento de la misma manera que se declara una variable, especificando su nombre y tipo de datos. También especifica el mecanismo para pasar argumentos, y si el parámetro es opcional.  
  
 Para obtener más información, consulte [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Para definir un parámetro de procedimiento  
  
1.  En la declaración de procedimiento, agregue el nombre de parámetro a la lista de parámetros del procedimiento, separándolo de otros parámetros mediante comas.  
  
2.  Decidir el tipo de datos del parámetro.  
  
3.  Siga el nombre del parámetro con un `As` cláusula para especificar el tipo de datos.  
  
4.  Decida el mecanismo para pasar argumentos que desee para el parámetro. Normalmente se pasa un parámetro por valor, a menos que desee que el procedimiento pueda cambiar su valor en el código de llamada.  
  
5.  Incluya delante del nombre de parámetro con [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para especificar el mecanismo para pasar argumentos. Para obtener más información, consulte [las diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Si el parámetro es opcional, preceder el mecanismo para pasar argumentos [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) y siga el tipo de datos de parámetro con un signo igual (`=`) y un valor predeterminado.  
  
     En el ejemplo siguiente se define el esquema de un `Sub` procedimiento con tres parámetros. Los dos primeros son necesarios y el tercero es opcional. Las declaraciones de parámetros se separan en la lista de parámetros mediante comas.  
  
     [!code-vb[VbVbcnProcedures Nº&33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     El primer parámetro acepta un `customer` objeto, y `updateCustomer` puede actualizar directamente la variable que se pasa a `c` porque el argumento se pasa [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). El procedimiento no puede cambiar los valores de los últimos dos argumentos porque se pasan [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Si el código de llamada no proporciona un valor para el `level` parámetro [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] establece en el valor predeterminado de 0.  
  
     Si el modificador de comprobación de tipo ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `Off`, el `As` cláusula es opcional cuando se define un parámetro. Sin embargo, si utiliza un parámetro una `As` cláusula, todos ellos deben usarlo. Si el modificador de comprobación de tipo es `On`, el `As` cláusula es necesaria para cada definición de parámetro.  
  
     Especificar los tipos de datos para todos los elementos de programación se conoce como *establecimiento inflexible de tipos*. Al establecer `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] exige el establecimiento inflexible de tipos. Esto se recomienda, por los motivos siguientes:  
  
    -   Habilita la compatibilidad con IntelliSense para las variables y parámetros. Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.  
  
    -   Permite que el compilador realice la comprobación de tipo. Esto permite detectar las instrucciones que pueden fallar en tiempo de ejecución debido a errores como el desbordamiento. También detecta llamadas a métodos en objetos que no las admiten.  
  
    -   Da como resultado una ejecución más rápida del código. Un motivo para esto es que, si no especifica un tipo de datos para un elemento de programación, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador asigna el `Object` tipo. El código compilado tendría que realizar conversiones entre `Object` y otros tipos de datos, lo que reduce el rendimiento.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Sub (procedimientos)](./sub-procedures.md)   
 [Function (procedimientos)](./function-procedures.md)   
 [Cómo: pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)   
 [Procedimientos recursivos](./recursive-procedures.md)   
 [Sobrecarga de procedimientos](./procedure-overloading.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Programación orientada a objetos](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
