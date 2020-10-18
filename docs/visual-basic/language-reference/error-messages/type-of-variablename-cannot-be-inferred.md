---
title: No se puede inferir el tipo de '<variablename>' porque los límites del bucle y la variable step no se convierten en el mismo tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 1330cbd6567b69df9bd811ced49c6df2e120a0b2
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161214"
---
# <a name="bc30982-type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a>BC30982: \<variablename> no se puede inferir el tipo de ' ' porque los límites del bucle y la variable Step no se amplían al mismo tipo

Ha escrito un `For...Next` bucle en el que el compilador no puede inferir un tipo de datos para la variable de control de bucle, ya que se cumplen las condiciones siguientes:

- El tipo de datos de la variable de control de bucle no se especifica con una cláusula `As` .

- Los límites del bucle y la variable step contienen al menos dos tipos de datos.

- No existe ninguna conversión estándar entre los tipos de datos.

 Por consiguiente, el compilador no puede inferir el tipo de datos de la variable de control de un bucle.

 En el ejemplo siguiente, la variable de paso es un carácter y los límites del bucle son ambos enteros. Dado que no hay ninguna conversión estándar entre los caracteres y los enteros, se genera este error.

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

**Identificador de error:** BC30982

## <a name="to-correct-this-error"></a>Para corregir este error

- Cambie los tipos de los límites del bucle y la variable Step según sea necesario para que al menos uno de ellos sea un tipo al que se amplíen los demás. En el ejemplo anterior, cambie el tipo de `stepVar` a `Integer` .

  ```vb
  Dim stepVar = 1
  ```

  o bien

  ```vb
  Dim stepVar As Integer = 1
  ```

- Use funciones de conversión explícitas para convertir los límites del bucle y la variable de paso en los tipos adecuados. En el ejemplo anterior, aplique la `Val` función a `stepVar` .

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [Instrucción For...Next](../statements/for-next-statement.md)
- [Conversiones implícitas y explícitas](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Inferencia de tipo de variable local](../../programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer (instrucción)](../statements/option-infer-statement.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
