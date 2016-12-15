---
title: "Single (Tipo de datos, Visual Basic) | Microsoft Docs"
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
  - "vb.Single"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "! (carácter de tipo identificador)"
  - "caracteres 0, finales"
  - "tipos de datos [Visual Basic], asignar"
  - "F (carácter de tipo literal)"
  - "números de punto flotante, Single (tipo de datos)"
  - "caracteres de tipo identificador, !"
  - "caracteres de tipo literal, F"
  - "números, punto flotante"
  - "números, reales"
  - "números reales"
  - "Single (tipo de datos)"
  - "números de precisión sencilla"
  - "caracteres 0 finales"
  - "ceros finales"
  - "ceros, finales"
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Single (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Incluye números IEEE de punto flotante de precisión sencilla de 32 bits \(4 bytes\) con signo cuyos valores van de \-3,4028235E\+38 a \-1,401298E\-45 para números negativos y de 1,401298E\-45 a 3,4028235E\+38 para números positivos.  Los números de precisión sencilla almacenan aproximaciones de números reales.  
  
## Comentarios  
 Utilice el tipo de datos `Single` para incluir valores de punto flotante que no requieren el ancho completo de datos de `Double`.  En algunos casos, Common Language Runtime puede empaquetar las variables `Single` de forma que se ahorre consumo de memoria.  
  
 El valor predeterminado de `Single` es 0.  
  
## Sugerencias de programación  
  
-   **Precisión.** Cuando trabaje con números de punto flotante, tenga presente que no siempre tienen una representación precisa en memoria.  Esto podría conducir a resultados inesperados en ciertas operaciones, como la comparación de valores y el operador `Mod`.  Para obtener más información, vea [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Ampliación.** El tipo de datos `Single` amplía a `Double`.  Esto significa que puede convertir `Single` en `Double` sin encontrar un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Ceros finales.** Los tipos de datos de punto flotante no tienen representación interna de caracteres 0 finales.  Por ejemplo, no distinguen entre 4,2000 y 4,2.  Por consiguiente, los caracteres 0 finales no aparecen cuando muestra o imprime valores de punto flotante.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `F` a un literal, el tipo de datos se convierte al tipo de datos `Single`.  Si se agrega el carácter de tipo identificador `!` a cualquier identificador, se convierte su tipo de datos al tipo `Single`.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Single?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Single?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Decimal \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/decimal-data-type.md)   
 [Double \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/double-data-type.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)