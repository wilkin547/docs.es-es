---
title: Tipo de &#39; &lt;variablename&gt; &#39; no se puede inferir porque los límites del bucle y la variable step no se convierten en el mismo tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: d6fdd9445b5336773d150c643c7bf1ca58a0c87a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>Tipo de &#39; &lt;variablename&gt; &#39; no se puede inferir porque los límites del bucle y la variable step no se convierten en el mismo tipo
Ha escrito un `For...Next` bucle en el que el compilador no puede inferir un tipo de datos para la variable de control de bucle porque las condiciones siguientes son ciertas:  
  
-   El tipo de datos de la variable de control de bucle no se especifica con una cláusula `As` .  
  
-   Los límites del bucle y la variable step contienen al menos dos tipos de datos.  
  
-   No existe ninguna conversión estándar entre los tipos de datos.  
  
 Por lo tanto, el compilador no puede inferir el tipo de datos de la variable de control del bucle.  
  
 En el ejemplo siguiente, la variable step es un carácter y los límites del bucle son dos enteros. Porque no hay ninguna conversión estándar entre caracteres y números enteros, se informa de este error.  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 **Id. de error:** BC30982  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar los tipos de los límites del bucle y la variable step según sea necesario para que al menos uno de ellos es un tipo que amplían los demás. En el ejemplo anterior, cambie el tipo de `stepVar` a `Integer`.  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     -O bien-  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   Usar funciones de conversión explícita para convertir los límites del bucle y la variable step a los tipos adecuados. En el ejemplo anterior, se aplica el `Val` función `stepVar`.  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer (instrucción)](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
