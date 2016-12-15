---
title: "Boolean (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.FALSE"
  - "vb.TRUE"
  - "vb.Boolean"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean (tipo de datos)"
  - "valores booleanos, False (palabra clave)"
  - "valores booleanos, True (palabra clave)"
  - "False (palabra clave) [Visual Basic]"
  - "True (palabra clave) [Visual Basic]"
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Boolean (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene valores que pueden ser sólo `True` o `False`.  Las palabras clave `True` y `False` corresponden a los dos estados de las variables `Boolean`.  
  
## Comentarios  
 Utilice [Boolean Data Type \(Visual Basic\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) para contener valores de dos estados como verdadero\/falso, sí\/no o activado\/desactivado.  
  
 El valor predeterminado de `Boolean` es `False`.  
  
 Los valores `Boolean` no se almacenan como números y los valores almacenados no se consideran equivalentes a números.  No debe escribir código que se base en los valores numéricos equivalentes de `True` y `False`.  Siempre que sea posible, debe restringir el uso de variables `Boolean` a los valores lógicos para los que se han diseñado.  
  
## Conversiones de tipo  
 Cuando Visual Basic convierte los valores de tipos de datos numéricos en `Boolean`, 0 pasa a ser `False` y todos los otros valores, `True`.  Cuando Visual Basic convierte los valores `Boolean` en tipos numéricos, `False` pasa a  ser 0 y `True`, \-1.  
  
 Al convertir entre valores `Boolean` y tipos de datos numéricos, recuerde que los métodos de conversión de .NET Framework no siempre producen los mismos resultados que las palabras clave de conversión de Visual Basic.  Esto se debe a que la conversión de Visual Basic conserva un comportamiento compatible con versiones anteriores.  Para obtener más información, vea la sección sobre cómo el tipo Boolean no se convierte al tipo numérico correctamente en [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Sugerencias de programación  
  
-   **Números negativos.** `Boolean` no es un tipo numérico y no puede representar un valor negativo.  En cualquier caso, no debería utilizar `Boolean` para contener valores numéricos.  
  
-   **Caracteres de tipo.** `Boolean` no tiene ningún carácter de tipo literal o de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Boolean?displayProperty=fullName>.  
  
## Ejemplo  
 En el ejemplo siguiente, `runningVB` es una variable `Boolean` que almacena un único parámetro de tipo sí\/no.  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## Vea también  
 <xref:System.Boolean?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [CType \(Función\)](../../../visual-basic/language-reference/functions/ctype-function.md)