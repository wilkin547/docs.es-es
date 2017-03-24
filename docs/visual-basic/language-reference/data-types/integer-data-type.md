---
title: "Integer (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Integer"
  - "Integer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "% (carácter de tipo identificador)"
  - "tipos de datos [Visual Basic], asignar"
  - "tipos de datos [Visual Basic], integrales"
  - "valores enumerados"
  - "I (carácter de tipo literal)"
  - "caracteres de tipo identificador, %"
  - "Integer (tipo de datos)"
  - "números enteros"
  - "enteros, tipos de datos"
  - "enteros, tipos"
  - "tipos de datos integrales"
  - "caracteres de tipo literal, I"
  - "números, enteros"
  - "números, enteros"
  - "números enteros"
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Integer (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Contiene enteros de 32 bits con signo \(4 bytes\) comprendidos en el intervalo entre \-2.147.483.648 y 2.147.483.647.  
  
## Comentarios  
 El tipo de datos `Integer` proporciona un rendimiento óptimo en un procesador de 32 bits.  Los demás tipos enteros son más lentos a la hora de cargarse y almacenarse en la memoria.  
  
 El valor predeterminado de `Integer` es 0.  
  
## Sugerencias de programación  
  
-   **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para .NET Framework, por ejemplo, objetos de automatización o COM, recuerde que `Integer` tiene un ancho de datos diferente \(16 bits\) en otros entornos.  Al pasar un argumento de 16 bits a esos componentes, declárelo en el código de Visual Basic como `Short` en lugar de como `Integer`.  
  
-   **Ampliación.** El tipo de datos `Integer` se amplía a `Long`, `Decimal`, `Single` o `Double`.  Esto significa que puede convertir un tipo de datos `Integer` en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `I` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Integer`.  Si se agrega el carácter de tipo identificador `%` a cualquier identificador, se convierte forzosamente al tipo `Integer`.  
  
-   **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int32?displayProperty=fullName>.  
  
## Intervalo  
 Si intenta establecer una variable de un tipo entero en un número que está fuera del intervalo correspondiente a ese tipo, se produce un error.  Si intenta establecerlo en una fracción, el número se redondea hacia arriba o hacia abajo al valor entero más cercano.  Si el número está equidistante a dos valores enteros, el valor se redondea al entero par más próximo.  Este comportamiento minimiza los errores de redondeo que se derivan de redondear de forma consistente un valor de punto medio en una dirección única.  En el código siguiente se muestran ejemplos de redondeo.  
  
```  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```  
  
## Vea también  
 <xref:System.Int32?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Long \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Short \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)