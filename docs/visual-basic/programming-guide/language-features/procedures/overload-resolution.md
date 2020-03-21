---
title: Overload Resolution
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
ms.openlocfilehash: 84d52bbbfb34c2e5d67ed6a1810ab3e32fafda22
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266877"
---
# <a name="overload-resolution-visual-basic"></a>Resolución de sobrecarga (Visual Basic)
Cuando el compilador de Visual Basic encuentra una llamada a un procedimiento que se define en varias versiones sobrecargadas, el compilador debe decidir cuál de las sobrecargas llamar. Para ello, realiza los pasos siguientes:  
  
1. **Accesibilidad.** Elimina cualquier sobrecarga con un nivel de acceso que impide que el código de llamada lo llame.  
  
2. **Número de parámetros.** Elimina cualquier sobrecarga que defina un número diferente de parámetros que se proporcionan en la llamada.  
  
3. **Tipos de datos de parámetros.** El compilador da preferencia a los métodos de instancia sobre los métodos de extensión. Si se encuentra algún método de instancia que solo requiera ampliar las conversiones para que coincida con la llamada al procedimiento, se quitan todos los métodos de extensión y el compilador continúa solo con los candidatos al método de instancia. Si no se encuentra ningún método de instancia de este tipo, continúa con los métodos de instancia y extensión.  
  
     En este paso, elimina cualquier sobrecarga para la que los tipos de datos de los argumentos de llamada no se pueden convertir a los tipos de parámetro definidos en la sobrecarga.  
  
4. **Restringir conversiones.** Elimina cualquier sobrecarga que requiera una conversión de restricción de los tipos de argumento de llamada a los tipos de parámetro definidos. Esto es cierto si el modificador de `On` comprobación `Off`de tipos ( Option[Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es o .  
  
5. **Menos ensanchamiento.** El compilador considera las sobrecargas restantes en pares. Para cada par, compara los tipos de datos de los parámetros definidos. Si los tipos de una de las sobrecargas se amplían a los tipos correspondientes en el otro, el compilador elimina este último. Es decir, conserva la sobrecarga que requiere la menor cantidad de ensanchamiento.  
  
6. **Candidato único.** Continúa considerando sobrecargas en pares hasta que solo queda una sobrecarga y resuelve la llamada a esa sobrecarga. Si el compilador no puede reducir las sobrecargas a un único candidato, genera un error.  
  
 En la ilustración siguiente se muestra el proceso que determina cuál de un conjunto de versiones sobrecargadas se va a llamar.  
  
 ![Diagrama de flujo de proceso de resolución de sobrecarga](./media/overload-resolution/determine-overloaded-version.gif "Resolver entre versiones sobrecargadas")
  
 En el ejemplo siguiente se muestra este proceso de resolución de sobrecarga.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 En la primera llamada, el compilador elimina la primera sobrecarga`Short`porque el tipo del primer`Byte`argumento ( ) se limita al tipo del parámetro correspondiente ( ). A continuación, elimina la tercera sobrecarga porque cada`Short` `Single`tipo de argumento de la segunda sobrecarga`Integer` `Single`( y ) se amplía al tipo correspondiente en la tercera sobrecarga ( y ). La segunda sobrecarga requiere menos ampliación, por lo que el compilador la usa para la llamada.  
  
 En la segunda llamada, el compilador no puede eliminar ninguna de las sobrecargas en función del estrechamiento. Elimina la tercera sobrecarga por el mismo motivo que en la primera llamada, porque puede llamar a la segunda sobrecarga con menos ampliación de los tipos de argumento. Sin embargo, el compilador no puede resolver entre la primera y la segunda sobrecarga. Cada uno tiene un tipo de parámetro definido que`Byte` se `Short`amplía `Single` `Double`al tipo correspondiente en el otro ( a , pero a ). Por lo tanto, el compilador genera un error de resolución de sobrecarga.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Argumentos opcionales sobrecargados y ParamArray  
 Si dos sobrecargas de un procedimiento tienen firmas idénticas excepto que el último parámetro se declara [Opcional](../../../../visual-basic/language-reference/modifiers/optional.md) en uno y [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) en el otro, el compilador resuelve una llamada a ese procedimiento de la siguiente manera:  
  
|Si la llamada proporciona el último argumento como|El compilador resuelve la llamada a la sobrecarga declarando el último argumento como|  
|---|---|  
|Sin valor (argumento omitido)|`Optional`|  
|Un valor único|`Optional`|  
|Dos o más valores en una lista separada por comas|`ParamArray`|  
|Una matriz de cualquier longitud (incluida una matriz vacía)|`ParamArray`|  
  
## <a name="see-also"></a>Consulte también

- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Procedimientos de solución de problemas](./troubleshooting-procedures.md)
- [Cómo: Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Cómo: Llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Métodos de extensión](./extension-methods.md)
