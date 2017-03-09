---
title: "UInteger (Tipo de datos) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.uinteger"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], integrales"
  - "números enteros"
  - "enteros, tipos de datos"
  - "enteros, tipos"
  - "tipos de datos integrales"
  - "caracteres de tipo literal, interfaz de usuario"
  - "números, enteros"
  - "números, enteros"
  - "caracteres de tipo literal de interfaz de usuario"
  - "UInteger (tipo de datos)"
  - "números enteros"
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# UInteger (Tipo de datos)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Contiene enteros de 32 bits sin signo \(4 bytes\) que se sitúan en el intervalo entre 0 y 4.294.967.295.  
  
## Comentarios  
 El tipo de datos `UInteger` proporciona el valor sin signo más largo en el ancho de datos más eficaz.  
  
 El valor predeterminado de `UInteger` es 0.  
  
## Sugerencias de programación  
 Los tipos de datos `UInteger` y `Integer` proporcionan un rendimiento óptimo en un procesador de 32 bits, ya que los tipos de enteros más pequeños \(`UShort`, `Short`, `Byte` y `SByte`\), aunque utilizan menos bits, necesitan más tiempo para cargarse, almacenarse y obtenerse.  
  
-   **Números negativos.** Dado que `UInteger` es un tipo sin signo, no puede representar un número negativo.  Si utiliza el operador menos \(`-`\) unario en una expresión que produce un resultado del tipo `UInteger`, Visual Basic convierte primero la expresión a `Long`.  
  
-   **Compatibilidad con CLS.** El tipo de datos `UInteger` no forma parte de [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), por lo que el código conforme a CLS no puede utilizar un componente que lo utiliza.  
  
-   **Consideraciones de interoperabilidad.** Si trabaja con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los tipos como `uint` pueden tener un ancho de datos distinto \(16 bits\) en otros entornos.  Al pasar un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en el código administrado de Visual Basic.  
  
-   **Ampliación.** El tipo de datos `UInteger` se amplía a `Long`, `ULong`, `Decimal`, `Single` y `Double`.  Esto significa que se puede convertir `UInteger` en cualquiera de estos tipos sin encontrar un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** Al agregar los caracteres de tipo literal `UI` a un literal, el tipo de datos se convierte al tipo de datos `UInteger`.  `UInteger` no tiene caracteres de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.UInt32?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.UInt32>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Cómo: Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)