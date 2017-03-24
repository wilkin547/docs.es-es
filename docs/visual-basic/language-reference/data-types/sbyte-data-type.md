---
title: "SByte (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.sbyte"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], integrales"
  - "números enteros"
  - "enteros, tipos de datos"
  - "enteros, tipos"
  - "tipos de datos integrales"
  - "números, enteros"
  - "números, enteros"
  - "SByte (tipo de datos)"
  - "números enteros"
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# SByte (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Contiene enteros de 8 bits con signo \(1 bytes\) que se sitúan en el intervalo entre \-128 y 127.  
  
## Comentarios  
 Utilice el tipo de datos `SByte` para incluir valores enteros que no precisen el ancho total de datos de `Integer` ni la mitad del ancho de datos de `Short`.  En algunos casos, Common Language Runtime puede empaquetar las variables `SByte` de forma que se ahorre consumo de memoria.  
  
 El valor predeterminado de `SByte` es 0.  
  
## Sugerencias de programación  
  
-   **Compatibilidad con CLS.** El tipo de datos `SByte` no forma parte de [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.  
  
-   **Ampliación.** El tipo de datos `SByte` se amplía a `Short`, `Integer`, `Long`, `Decimal`, `Single` y `Double`.  Esto significa que se puede convertir `SByte` en cualquiera de estos tipos sin encontrar un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** `SByte` no tiene caracteres de tipo literal ni caracteres de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.SByte?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.SByte?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Short \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Integer \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Long \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)