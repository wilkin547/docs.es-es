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
ms.openlocfilehash: 9b83eba8efc8dfe14b6ec1cbab270984977198e5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071370"
---
# <a name="overload-resolution-visual-basic"></a>Resolución de sobrecarga (Visual Basic)

Cuando el compilador de Visual Basic encuentra una llamada a un procedimiento que está definido en varias versiones sobrecargadas, el compilador debe decidir cuál de las sobrecargas llamar. Para ello, realiza los pasos siguientes:  
  
1. **Accesibilidad.** Elimina cualquier sobrecarga con un nivel de acceso que impida que el código de llamada lo llame.  
  
2. **Número de parámetros.** Elimina cualquier sobrecarga que defina un número diferente de parámetros de los proporcionados en la llamada.  
  
3. **Tipos de datos de parámetros.** El compilador proporciona preferencia de los métodos de instancia sobre los métodos de extensión. Si se encuentra algún método de instancia que requiera que solo las conversiones de ampliación coincidan con la llamada a procedimiento, se quitan todos los métodos de extensión y el compilador continúa solo con los candidatos de método de instancia. Si no se encuentra ningún método de instancia, continúa con los métodos de instancia y de extensión.  
  
     En este paso, se elimina cualquier sobrecarga para la que los tipos de datos de los argumentos de llamada no se puedan convertir en los tipos de parámetro definidos en la sobrecarga.  
  
4. **Conversiones de restricción.** Elimina cualquier sobrecarga que requiera una conversión de restricción de los tipos de argumento que realiza la llamada a los tipos de parámetro definidos. Esto es así si el modificador de comprobación de tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) es `On` o `Off` .  
  
5. **Menor ampliación.** El compilador tiene en cuenta las sobrecargas restantes en pares. Para cada par, compara los tipos de datos de los parámetros definidos. Si los tipos de una de las sobrecargas se amplían a los tipos correspondientes del otro, el compilador elimina el último. Es decir, conserva la sobrecarga que requiere la menor cantidad de ampliación.  
  
6. **Candidato único.** Sigue considerando las sobrecargas en los pares hasta que solo queda una sobrecarga y resuelve la llamada a esa sobrecarga. Si el compilador no puede reducir las sobrecargas a un solo candidato, se genera un error.  
  
 En la ilustración siguiente se muestra el proceso que determina cuál de un conjunto de versiones sobrecargadas se debe llamar.  
  
 ![Diagrama de flujo de proceso de resolución de sobrecarga](./media/overload-resolution/determine-overloaded-version.gif "Resolver entre versiones sobrecargadas")
  
 En el ejemplo siguiente se muestra este proceso de resolución de sobrecarga.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 En la primera llamada, el compilador elimina la primera sobrecarga porque el tipo del primer argumento ( `Short` ) se limita al tipo del parámetro correspondiente ( `Byte` ). A continuación, elimina la tercera sobrecarga porque cada tipo de argumento de la segunda sobrecarga ( `Short` y `Single` ) se amplía al tipo correspondiente en la tercera sobrecarga ( `Integer` y `Single` ). La segunda sobrecarga requiere menos ampliación, por lo que el compilador la usa para la llamada.  
  
 En la segunda llamada, el compilador no puede eliminar ninguna de las sobrecargas en función de la restricción. Elimina la tercera sobrecarga por la misma razón que en la primera llamada, porque puede llamar a la segunda sobrecarga con menos ampliación de los tipos de argumento. Sin embargo, el compilador no puede resolver entre la primera y la segunda sobrecarga. Cada tiene un tipo de parámetro definido que se amplía al tipo correspondiente en el otro ( `Byte` a `Short` , pero `Single` a `Double` ). Por tanto, el compilador genera un error de resolución de sobrecarga.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Argumentos opcionales y ParamArray sobrecargados  

 Si dos sobrecargas de un procedimiento tienen firmas idénticas, salvo que el último parámetro se declara [opcional](../../../language-reference/modifiers/optional.md) en One y [ParamArray](../../../language-reference/modifiers/paramarray.md) en el otro, el compilador resuelve una llamada a ese procedimiento de la manera siguiente:  
  
|Si la llamada proporciona el último argumento como|El compilador resuelve la llamada a la sobrecarga que declara el último argumento como|  
|---|---|  
|Sin valor (argumento omitido)|`Optional`|  
|Un valor único|`Optional`|  
|Dos o más valores en una lista separada por comas|`ParamArray`|  
|Una matriz de cualquier longitud (incluida una matriz vacía)|`ParamArray`|  
  
## <a name="see-also"></a>Vea también

- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Procedimiento para definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedimiento para llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Sobrecargas](../../../language-reference/modifiers/overloads.md)
- [Métodos de extensión](./extension-methods.md)
