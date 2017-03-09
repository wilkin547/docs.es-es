---
title: "Double (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Double"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "# (carácter de tipo identificador)"
  - "caracteres 0, finales"
  - "tipos de datos [Visual Basic], asignar"
  - "Double (tipo de datos)"
  - "Double (tipo de datos) [Visual Basic]"
  - "números de precisión doble"
  - "números de punto flotante, Double (tipo de datos)"
  - "caracteres de tipo identificador, #"
  - "caracteres de tipo literal, R"
  - "R (carácter de tipo literal)"
  - "números reales"
  - "caracteres 0 finales"
  - "ceros finales"
  - "ceros, finales"
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Double (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Contiene números IEEE de punto flotante de doble precisión de 64 bits \(8 bytes\) que van de un valor de –1,79769313486231570E\+308 a –4,94065645841246544E\-324 para números negativos y de 4,94065645841246544E\-324 a 1,79769313486231570E\+308 para números positivos.  Los números de doble precisión almacenan aproximaciones de números reales.  
  
## Comentarios  
 El tipo de datos `Double` proporciona las magnitudes mayores y menores posibles para un número.  
  
 El valor predeterminado de `Double` es 0.  
  
## Sugerencias de programación  
  
-   **Precisión.** Cuando trabaje con números de punto flotante, tenga presente que no siempre tienen una representación precisa en memoria.  Esto podría conducir a resultados inesperados en ciertas operaciones, como la comparación de valores y el operador `Mod`.  Para obtener más información, vea [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Ceros finales.** Los tipos de datos de punto flotante no tienen representación interna de caracteres cero finales.  Por ejemplo, no distinguen entre 4,2000 y 4,2.  Por consiguiente, los caracteres cero finales no aparecen cuando muestra o imprime valores de punto flotante.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `R` a un literal, el tipo de datos se convierte al tipo de datos `Double`.  Por ejemplo, si `R` sigue a un valor entero, el valor se cambia a `Double`.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     Si se agrega el carácter de tipo identificador `#` a cualquier identificador, se convierte su tipo de datos al tipo `Double`.  En el ejemplo siguiente, la variable `num` es de tipo `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Double?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Double?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Decimal \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/decimal-data-type.md)   
 [Single \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/single-data-type.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)