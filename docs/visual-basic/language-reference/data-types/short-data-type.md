---
title: "Short (Tipo de datos, Visual Basic) | Microsoft Docs"
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
  - "vb.Short"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], integrales"
  - "números enteros"
  - "enteros, tipos de datos"
  - "enteros, tipos"
  - "tipos de datos integrales"
  - "caracteres de tipo literal, S"
  - "números, enteros"
  - "números, enteros"
  - "S (carácter de tipo literal)"
  - "Short (tipo de datos)"
  - "números enteros"
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Short (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene enteros de 16 bits con signo \(2 bytes\) que se sitúan en el intervalo entre \-32,768 y 32,767.  
  
## Comentarios  
 Utilice el tipo de datos `Short` para incluir valores enteros que no requieren el ancho completo de datos de `Integer`.  En algunos casos, Common Language Runtime puede empaquetar las variables `Short` para ahorrar consumo de memoria.  
  
 El valor predeterminado de `Short` es 0.  
  
## Sugerencias de programación  
  
-   **Ampliación.** El tipo de datos `Short` se amplía a `Integer`, `Long`, `Decimal`, `Single` o `Double`.  Esto indica que `Short` se puede convertir en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `S` a un literal, el tipo de datos se convierte al tipo de datos `Short`.  `Short` no tiene caracteres de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int16?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Int16?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Integer \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Long \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)