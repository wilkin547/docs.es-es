---
title: "UShort (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ushort"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], integrales"
  - "números enteros"
  - "enteros, tipos de datos"
  - "enteros, tipos"
  - "tipos de datos integrales"
  - "caracteres de tipo literal, US"
  - "números, enteros"
  - "números, enteros"
  - "US (caracteres de tipo literal)"
  - "UShort (tipo de datos)"
  - "números enteros"
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# UShort (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Contiene enteros de 16 bits sin signo \(2 bytes\) que se sitúan en el intervalo entre 0 y 65.535.  
  
## Comentarios  
 Utilice el tipo de datos `UShort` para contener datos binarios demasiado grandes para `Byte`.  
  
 El valor predeterminado de `UShort` es 0.  
  
## Sugerencias de programación  
  
-   **Números negativos.** Dado que `UShort` es un tipo sin signo, no puede representar un número negativo.  Si utiliza el operador menos \(`-`\) unario en una expresión que produce un resultado del tipo `UShort`, Visual Basic convierte primero la expresión a `Integer`.  
  
-   **Compatibilidad con CLS.** El tipo de datos `UShort` no forma parte de [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.  
  
-   **Ampliación.** El tipo de datos `UShort` se amplía a `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` y `Double`.  Esto significa que se puede convertir `UShort` en cualquiera de estos tipos sin encontrar un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** Al agregar los caracteres de tipo literal `US` a un literal, el tipo de datos se convierte al tipo de datos `UShort`.  `UShort` no tiene caracteres de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt16?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.UInt16>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Cómo: Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)