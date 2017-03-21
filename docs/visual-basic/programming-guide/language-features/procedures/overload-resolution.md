---
title: "Resolución de sobrecarga (Visual Basic) | Documentos de Microsoft"
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
- Visual Basic code, procedures
- overload resolution
- procedures, overloading
- procedures, calling
- procedure overloading, overload resolution
- signatures, procedure
- overloads, resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
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
ms.openlocfilehash: 0de3a603fa84a72018a566f6e7182b45e53ec89e
ms.lasthandoff: 03/13/2017

---
# <a name="overload-resolution-visual-basic"></a>Resolución de sobrecarga (Visual Basic)
Cuando el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador encuentra una llamada a un procedimiento que está definido en varias versiones sobrecargadas, el compilador debe decidir a qué sobrecarga tiene que llamar. Para ello, realice los siguientes pasos:  
  
1.  **Accesibilidad.** Elimina cualquier sobrecarga con un nivel de acceso que impide que el código de llamada de llamarlo.  
  
2.  **Número de parámetros.** Elimina cualquier sobrecarga que defina un número de parámetros que se suministran en la llamada.  
  
3.  **Tipos de datos de parámetro.** El compilador da preferencia de métodos de instancia con respecto a los métodos de extensión. Si se encuentra cualquier método de instancia que requiere sólo conversiones de ampliación que coincida con la llamada de procedimiento, se quitan todos los métodos de extensión y el compilador sigue con sólo los candidatos del método de instancia. Si este método de instancia no se encuentra, continúa con la instancia y los métodos de extensión.  
  
     En este paso elimina cualquier sobrecarga para que los tipos de datos de los argumentos de llamada no se puede convertir a los tipos definidos en la sobrecarga.  
  
4.  **Conversiones de restricción.** Elimina cualquier sobrecarga que requiera una conversión de restricción de los tipos de argumento de llamada a los tipos de parámetros. Esto es cierto si el tipo modificador de comprobación ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On` o `Off`.  
  
5.  **Ampliación mínima.** El compilador considera las sobrecargas restantes en parejas. Para cada pareja, compara los tipos de datos de los parámetros definidos. Si los tipos en una de las sobrecargas se amplían a los tipos correspondientes en el otro, el compilador elimina la última. Es decir, conserva la sobrecarga que requiere la menor cantidad de ampliación.  
  
6.  **Candidata única.** Continúa Considerando las sobrecargas por partes hasta que sólo una sobrecarga permanece y resuelve la llamada a esa sobrecarga. Si el compilador no puede reducir las sobrecargas a una sola candidata, genera un error.  
  
 La siguiente ilustración muestra el proceso que determina qué conjunto de versiones sobrecargadas llamar.  
  
 ![Diagrama de flujo del proceso de resolución de sobrecarga](./media/overloadres.gif "OverloadRes")  
Resolver entre versiones sobrecargadas  
  
 En el ejemplo siguiente se muestra este proceso de resolución de sobrecarga.  
  
 [!code-vb[VbVbcnProcedures&#62;](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#63;](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 En la primera llamada, el compilador elimina la primera sobrecarga porque el tipo del primer argumento (`Short`) se restringe al tipo del parámetro correspondiente (`Byte`). A continuación, elimina la tercera sobrecarga porque cada argumento de tipo en la segunda sobrecarga (`Short` y `Single`) se amplía al tipo correspondiente en la tercera sobrecarga (`Integer` y `Single`). La segunda sobrecarga requiere una ampliación menor, por lo que el compilador utiliza para la llamada.  
  
 En la segunda llamada, el compilador no puede eliminar ninguna de las sobrecargas sobre la base de restricción. Elimina la tercera sobrecarga por la misma razón que en la primera llamada, porque se puede llamar a la segunda sobrecarga con menos ampliación de los tipos de argumento. Sin embargo, el compilador no puede resolver entre la primera y la segunda sobrecarga. Cada uno tiene un tipo de parámetro definido que se amplía al tipo correspondiente en el otro (`Byte` a `Short`, pero `Single` a `Double`). Por lo tanto, el compilador genera un error de resolución de sobrecarga.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Opcionales sobrecargados y ParamArray (argumentos)  
 Si dos sobrecargas de un procedimiento tienen firmas idénticas, salvo que se declara el último parámetro [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) en uno y [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) en la otra, el compilador resuelve una llamada a ese procedimiento como sigue:  
  
|Si la llamada suministra el último argumento como|El compilador resuelve la llamada a la sobrecarga declarando el último argumento como|  
|---|---|  
|Ningún valor (argumento omitido)|`Optional`|  
|Un valor único|`Optional`|  
|Dos o más valores en una lista separada por comas|`ParamArray`|  
|Una matriz de cualquier longitud (incluida una matriz vacía)|`ParamArray`|  
  
## <a name="see-also"></a>Vea también  
 [Parámetros opcionales](./optional-parameters.md)   
 [Matrices de parámetros](./parameter-arrays.md)   
 [Sobrecarga de procedimientos](./procedure-overloading.md)   
 [Procedimientos de solución de problemas](./troubleshooting-procedures.md)   
 [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)   
 [Cómo: sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)   
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Métodos de extensión](./extension-methods.md)
