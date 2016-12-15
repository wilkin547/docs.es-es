---
title: "Char (Tipo de datos, Visual Basic) | Microsoft Docs"
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
  - "vb.Char"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "C (carácter de tipo literal)"
  - "Char (tipo de datos)"
  - "Char (tipo de datos), literales de caracteres"
  - "tipos de datos [Visual Basic], asignar"
  - "caracteres de tipo literal, C"
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Char (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene puntos de código de 16 bits \(2 bytes\) sin signo cuyo valor oscila entre 0 y 65535.  Cada *punto de código* o código de carácter, representa un carácter Unicode único.  
  
## Comentarios  
 Utilice el tipo de datos `Char` cuando necesite albergar únicamente un carácter individual y no necesite la sobrecarga de `String`.  En algunos casos, puede utilizar `Char()`, una matriz de elementos `Char`, para albergar varios caracteres.  
  
 El valor predeterminado de `Char` es el carácter con el punto de código 0.  
  
## Caracteres Unicode  
 Los primeros 128 puntos de código \(0 a 127\) de Unicode corresponden a las letras y símbolos de un teclado estándar de EE.UU.  teclado.  Estos primeros 128 puntos de código son los mismos que los que el juego de caracteres ASCII define.  Los siguientes 128 puntos de código \(128–255\) representan caracteres especiales, como letras de alfabetos latinos, acentos, símbolos de moneda y fracciones.  Unicode utiliza los puntos de código restantes \(256\-65535\) para albergar una amplia variedad de símbolos, incluidos caracteres de texto de todo el mundo, signos diacríticos y símbolos técnicos y matemáticos.  
  
 Puede utilizar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en una variable `Char` para determinar su clasificación Unicode.  
  
## Conversiones de tipo  
 Visual Basic no realiza conversiones directas entre el tipo `Char` y los tipos numéricos.  Puede usar la función <xref:Microsoft.VisualBasic.Strings.Asc%2A> o <xref:Microsoft.VisualBasic.Strings.AscW%2A> para convertir un valor `Char` en un valor `Integer` que represente su punto de código.  Puede usar la función <xref:Microsoft.VisualBasic.Strings.Chr%2A> o <xref:Microsoft.VisualBasic.Strings.ChrW%2A> para convertir un valor `Integer` en un valor `Char` que tenga ese punto de código.  
  
 Si el modificador de comprobación de tipos \([Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)\) está habilitado, debe agregar el carácter de tipo literal a un literal de cadena de un solo carácter para identificarlo como el tipo de datos `Char`.  Esto se ilustra en el siguiente ejemplo:  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## Sugerencias de programación  
  
-   **Números negativos.** `Char` es un tipo sin signo y no puede representar un valor negativo.  En cualquier caso, no debería utilizar `Char` para albergar valores numéricos.  
  
-   **Consideraciones de interoperabilidad.** Si trabaja con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los tipos de caracteres pueden tener un ancho de datos distinto \(8 bits\) en otros entornos.  Al pasar un argumento de 8 bits a esos componentes, declárelo como `Byte` en lugar de `Char` en el nuevo código de Visual Basic.  
  
-   **Ampliación.** El tipo de datos `Char` amplía a `String`.  Esto significa que puede convertir `Char` a `String` sin que se produzca un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** Al anexar el carácter de tipo literal `C` a un literal de cadena de un solo carácter, se le impone el tipo de datos `Char`.   `Char` no tiene caracteres de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Char?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Char?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [String \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Cómo: Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)