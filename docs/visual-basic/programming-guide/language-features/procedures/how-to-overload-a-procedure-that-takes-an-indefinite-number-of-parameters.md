---
title: "Cómo: sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic) | Documentos de Microsoft"
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
- procedures, parameters
- procedure overloading, indefinite number of parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters
- procedures, overloading
- procedures, multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
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
ms.openlocfilehash: c7e09bd482e35c7ce7f28a6cc7de0379b7cc89f6
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic)
Si un procedimiento tiene un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro, no se puede definir una versión sobrecargada que tome una matriz unidimensional para la matriz de parámetros. Para obtener más información, vea "Implícita sobrecargas de un parámetro ParamArray" en [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Para sobrecargar un procedimiento que toma un número variable de parámetros  
  
1.  Comprobar que el procedimiento y llamar a los beneficios de la lógica de código desde sobrecargado versiones más de un `ParamArray` parámetro. Vea "Sobrecargas y matrices de parámetros" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
2.  Determinar qué número de valores proporcionados debe aceptar el procedimiento en la parte variable de la lista de parámetros. Esto puede incluir el caso de ningún valor y podrían incluir el caso de una matriz unidimensional.  
  
3.  Para cada número aceptable de valores proporcionados, escribir una `Sub` o `Function` instrucción de declaración que define la lista de parámetros correspondiente. No usar la `Optional` o `ParamArray` (palabra clave) en esta versión sobrecargada.  
  
4.  En cada declaración, anteponga la `Sub` o `Function` palabra clave con la [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) (palabra clave).  
  
5.  Después de cada declaración, escriba el código de procedimiento que debería ejecutarse cuando el código de llamada proporcione los valores correspondientes a la lista de parámetros de esa declaración.  
  
6.  Finalizar cada procedimiento con el `End Sub` o `End Function` instrucción según corresponda.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un procedimiento definido con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro y, a continuación, un conjunto equivalente de procedimientos sobrecargados.  
  
 [!code-vb[VbVbcnProcedures&#69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 No se puede sobrecargar un procedimiento con una lista de parámetros que toma una matriz unidimensional para la matriz de parámetros. Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas. Las siguientes declaraciones ilustran esto.  
  
 [!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 El código de las versiones sobrecargadas no tiene que comprobar si el código de llamada proporciona uno o más valores para la `ParamArray` parámetro, o si es así, ¿cuántos. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]pasa el control a la versión correspondiente de la lista de argumentos de llamada.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Dado que un procedimiento con un `ParamArray` parámetro es equivalente a un conjunto de versiones sobrecargadas, no se puede sobrecargar un procedimiento con una lista de parámetros que se corresponda con alguna de estas sobrecargas implícitas. Para obtener más información, consulte [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Si se trabaja con una matriz que puede ser excesivamente grande, hay un riesgo de saturar alguna capacidad interna de la aplicación. Si acepta una matriz de parámetros, debe comprobar la longitud de la matriz que se pasa el código de llamada y seguir los pasos adecuados si es demasiado grande para la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Parámetros opcionales](./optional-parameters.md)   
 [Matrices de parámetros](./parameter-arrays.md)   
 [Sobrecarga de procedimientos](./procedure-overloading.md)   
 [Procedimientos de solución de problemas](./troubleshooting-procedures.md)   
 [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)   
 [Cómo: sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Resolución de sobrecargas](./overload-resolution.md)
