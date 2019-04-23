---
title: Resolución de sobrecarga (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: 4f81c7377423899c142c4270f325bbd7ed20b877
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312246"
---
# <a name="overload-resolution-visual-basic"></a>Resolución de sobrecarga (Visual Basic)
Cuando el compilador de Visual Basic encuentra una llamada a un procedimiento que se define en varias versiones sobrecargadas, el compilador debe decidir cuál de las sobrecargas para llamar a. Para ello, siga estos pasos:  
  
1. **Accesibilidad.** Elimina cualquier sobrecarga con un nivel de acceso que impide que el código de llamada de llamarlo.  
  
2. **Número de parámetros.** Elimina cualquier sobrecarga que define un número diferente de parámetros que se suministran en la llamada.  
  
3. **Tipos de datos de parámetro.** El compilador da preferencia de los métodos de instancia a través de métodos de extensión. Si se encuentra ningún método de instancia que requiere solo las conversiones para que coincida con la llamada al procedimiento de ampliación, se quitan todos los métodos de extensión y el compilador sigue con solo los candidatos de método de instancia. Si no se encuentra ningún método de instancia como ese, continúa con la instancia y métodos de extensión.  
  
     En este paso, elimina cualquier sobrecarga para el que no se puede convertir los tipos de datos de los argumentos de llamada a los tipos de parámetro definidos en la sobrecarga.  
  
4. **Conversiones de restricción.** Elimina cualquier sobrecarga que requiere una conversión de restricción de los tipos de argumento que realiza la llamada a los tipos de parámetro definidas. Esto es cierto si la comprobación de tipo modificador ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On` o `Off`.  
  
5. **Ampliación mínima.** El compilador considera las sobrecargas restantes en parejas. Para cada par, compara los tipos de datos de los parámetros definidos. Si los tipos en una de las sobrecargas todas se amplían a los tipos correspondientes en el otro, el compilador elimina la última. Es decir, conserva la sobrecarga que requiere la menor cantidad de ampliación.  
  
6. **Candidato único.** Sigue considerando las sobrecargas en parejas hasta solo una sobrecarga permanece y resuelve la llamada a esa sobrecarga. Si el compilador no puede reducir las sobrecargas a un único candidato, genera un error.  
  
 La siguiente ilustración muestra el proceso que determina qué conjunto de versiones sobrecargadas para llamar a.  
  
 ![Diagrama de flujo del proceso de resolución de sobrecarga](./media/overload-resolution/determine-overloaded-version.gif "resolver entre versiones sobrecargadas")    
  
 El ejemplo siguiente ilustra este proceso de resolución de sobrecarga.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 En la primera llamada, el compilador elimina la primera sobrecarga porque el tipo del primer argumento (`Short`) se restringe al tipo del parámetro correspondiente (`Byte`). A continuación, elimina la tercera sobrecarga porque cada argumento de tipo en la segunda sobrecarga (`Short` y `Single`) se amplía al tipo correspondiente en la tercera sobrecarga (`Integer` y `Single`). La segunda sobrecarga requiere menos ampliación, por lo que el compilador lo usa para la llamada.  
  
 En la segunda llamada, el compilador no puede eliminar ninguna de las sobrecargas en función de restricción. Elimina la tercera sobrecarga por la misma razón, como se muestra en la primera llamada, porque puede llamar a la segunda sobrecarga con menos ampliación de los tipos de argumento. Sin embargo, el compilador no puede resolver entre la primera y segunda sobrecarga. Cada uno tiene un tipo de parámetro definido que se amplía al tipo correspondiente en el otro (`Byte` a `Short`, pero `Single` a `Double`). Por lo tanto, el compilador genera un error de resolución de sobrecarga.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Opcionales sobrecargados y ParamArray (argumentos)  
 Si las dos sobrecargas de un procedimiento tienen firmas idénticas, salvo que se declara el último parámetro [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) en uno y [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) en el otro, el compilador resuelve una llamada a ese procedimiento como se indica a continuación:  
  
|Si la llamada proporciona el último argumento como|El compilador resuelve la llamada a la sobrecarga declarando el último argumento como|  
|---|---|  
|Ningún valor (argumento omitido)|`Optional`|  
|Un valor único|`Optional`|  
|Dos o más valores en una lista separada por comas|`ParamArray`|  
|Una matriz de cualquier longitud (incluida una matriz vacía)|`ParamArray`|  
  
## <a name="see-also"></a>Vea también

- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Cómo: Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Cómo: Llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Métodos de extensión](./extension-methods.md)
