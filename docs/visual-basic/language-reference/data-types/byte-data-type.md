---
title: "Byte (Tipo de datos, Visual Basic) | Microsoft Docs"
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
  - "vb.Byte"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Byte (tipo de datos)"
  - "tipos de datos [Visual Basic], asignar"
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Byte (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene enteros de 8 bits sin signo \(1 bytes\) que se sitúan en el intervalo entre 0 y 255.  
  
## Comentarios  
 Utilice el tipo de datos `Byte` para contener datos binarios.  
  
 El valor predeterminado de `Byte` es 0.  
  
## Sugerencias de programación  
  
-   **Números negativos.** Dado que `Byte` es un tipo sin signo, no puede representar un número negativo.  Si utiliza el operador menos \(`-`\) unario en una expresión que produce un resultado del tipo `Byte`, Visual Basic convierte primero la expresión a `Short`.  
  
-   **Conversiones de formato.** Cuando Visual Basic lee o escribe archivos o cuando llama a archivos DLL, métodos y propiedades, puede convertir automáticamente entre los formatos de datos.  Los datos binarios almacenados en variables `Byte` y matrices se conservan durante estas conversiones de formato.  No debería utilizar una variable `String` para datos binarios, ya que su contenido puede dañarse durante la conversión entre los formatos ANSI y Unicode.  
  
-   **Ampliación.** El tipo de datos `Byte` se amplía a `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` o `Double`.  Esto significa que se puede convertir `Byte` en cualquiera de estos tipos sin encontrar un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** `Byte` no tiene caracteres de tipo literal ni caracteres de tipo identificador.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Byte?displayProperty=fullName>.  
  
## Ejemplo  
 En el ejemplo siguiente, `b` es una variable `Byte`.  Las instrucciones muestran el intervalo de la variable y la aplicación de operadores de desplazamiento de bits a ella.  
  
 [!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  
  
## Vea también  
 <xref:System.Byte?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)