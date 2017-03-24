---
title: "ULong (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ulong"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], integrales"
  - "números enteros"
  - "enteros, tipos de datos"
  - "enteros, tipos"
  - "tipos de datos integrales"
  - "caracteres de tipo literal, UL"
  - "números, enteros"
  - "números, enteros"
  - "UL (caracteres de tipo literal)"
  - "ULong (tipo de datos)"
  - "números enteros"
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# ULong (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Contiene enteros de 64 bits sin signo \(8 bytes\) que van de un valor de 0 a 18.446.744.073.709.551.615 \(más de 1,84 veces 10 ^ 19\).  
  
## Comentarios  
 Utilice el tipo de datos `ULong` para contener datos binarios demasiado grandes para `UInteger` o valores de enteros sin signo lo más grandes posibles.  
  
 El valor predeterminado de `ULong` es 0.  
  
## Sugerencias de programación  
  
-   **Números negativos.** Dado que `ULong` es un tipo sin signo, no puede representar un número negativo.  Si utiliza el operador menos \(`-`\) unario en una expresión que produce un resultado del tipo `ULong`, Visual Basic convierte primero la expresión a `Decimal`.  
  
-   **Compatibilidad con CLS.** El tipo de datos `ULong` no forma parte de [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.  
  
-   **Consideraciones de interoperabilidad.** Si trabaja con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los tipos como `ulong` pueden tener un ancho de datos distinto \(32 bits\) en otros entornos.  Al pasar un argumento de 32 bits a esos componentes, declárelo como `UInteger` en lugar de `ULong` en el código administrado de Visual Basic.  
  
     Además, la automatización no admite enteros de 64 bits en Windows 95, Windows 98, Windows ME o Windows 2000.  No puede pasar un argumento de Visual Basic `ULong` a un componente de Automatización en estas plataformas.  
  
-   **Ampliación.** El tipo de datos `ULong` se amplía a `Decimal`, `Single` y `Double`.  Esto significa que se puede convertir `ULong` en cualquiera de estos tipos sin encontrar un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** Al agregar los caracteres de tipo literal `UL` a un literal, el tipo de datos se convierte al tipo de datos `ULong`.  `ULong` no tiene caracteres de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt64?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.UInt64>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Cómo: Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)