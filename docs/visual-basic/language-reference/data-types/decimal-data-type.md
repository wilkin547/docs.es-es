---
title: "Decimal (Tipo de datos, Visual Basic) | Microsoft Docs"
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
  - "vb.Decimal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "@ (carácter de tipo identificador)"
  - "caracteres 0, finales"
  - "D (carácter de tipo literal)"
  - "tipos de datos [Visual Basic], asignar"
  - "Decimal (tipo de datos)"
  - "decimal (palabra clave)"
  - "decimales, Decimal (tipo de datos)"
  - "caracteres de tipo identificador, @"
  - "caracteres de tipo literal, D"
  - "números, reales"
  - "números reales"
  - "caracteres 0 finales"
  - "ceros finales"
  - "números de precisión variable"
  - "ceros, finales"
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Decimal (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene valores de 128 bits \(16 bytes\) con signo que representan enteros de 96 bits \(12 bytes\) ajustados por una potencia variable de 10.  El factor de escala especifica el número de dígitos que hay a la derecha del separador decimal; va de 0 a 28.  Con una escala de 0 \(sin posiciones decimales\), el valor más grande posible es \+\/\-79,228,162,514,264,337,593,543,950,335 \(\+\/\-7.9228162514264337593543950335E\+28\).  Con 28 posiciones decimales, el valor más grande es \+\/\-7.9228162514264337593543950335 y el valor más pequeño distinto de cero es \+\/\-0.0000000000000000000000000001 \(\+\/\-1E\-28\).  
  
## Comentarios  
 El tipo de datos `Decimal` proporciona el número máximo de dígitos significativos para un número.  Admite hasta 29 dígitos significativos y puede representar valores que superan 7.9228 x 10^28.  Es especialmente cómodo para cálculos, por ejemplo, financieros, que requieren un gran número de dígitos pero no puede tolerar errores del redondeo.  
  
 El valor predeterminado de `Decimal` es 0.  
  
## Sugerencias de programación  
  
-   **Precisión.** `Decimal` no es un tipo de datos de punto flotante.  La estructura `Decimal` contiene un valor entero binario, junto con un bit de signo y un factor de ajuste de entero que especifica qué parte del valor es una fracción decimal.  Debido a esto, los números `Decimal` tienen una representación más precisa en la memoria que los tipos de punto flotante \(`Single` y `Double`\).  
  
-   **Rendimiento.** El tipo de datos `Decimal` es el más lento de todos los tipos numéricos.  Debe considerar la importancia de la precisión frente al rendimiento antes de elegir un tipo de datos.  
  
-   **Ampliación.** El tipo de datos `Decimal` se amplía a `Single` o `Double`.  Esto significa que se puede convertir `Decimal` a cualquiera de estos tipos sin encontrar un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Ceros finales.** Visual Basic no almacena los ceros finales en un literal `Decimal`.  Sin embargo, una variable `Decimal` conserva cualquier cero final adquirido de forma computacional.  Esto se ilustra en el siguiente ejemplo:  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     El resultado de `MsgBox` en el ejemplo anterior es el siguiente:  
  
     d1 \= 2.375, d2 \= 1.625, d3 \= 4.000, d4 \= 4  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `D` a un literal, el tipo de datos se convierte al tipo de datos `Decimal`.  Si se agrega el carácter de tipo identificador `@` a cualquier identificador, se convierte su tipo de datos al tipo `Decimal`.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Decimal?displayProperty=fullName>.  
  
## Intervalo  
 Podría necesitar utilizar el carácter de tipo `D` para asignar un valor grande a una variable o constante `Decimal`.  Este requisito es porque el compilador interpreta un literal como `Long` a menos que un carácter de tipo literal siga el literal, como se muestra en el ejemplo siguiente.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 La declaración `bigDec1` no genera un desbordamiento porque el valor asignado que pertenece al intervalo para `Long`.  El valor `Long` se puede asignar a la variable `Decimal` .  
  
 La declaración `bigDec2` genera un error de desbordamiento porque el valor asignado es demasiado grande para `Long`.  Porque el literal numérico no se puede primero interpretar como `Long`, no se puede asignar a la variable `Decimal` .  
  
 Para `bigDec3`, el carácter literal `D` de tipo resuelve el problema forzando el compilador para interpretar el literal como `Decimal` en lugar de como `Long`.  
  
## Vea también  
 <xref:System.Decimal?displayProperty=fullName>   
 <xref:System.Decimal.%23ctor%2A?displayProperty=fullName>   
 <xref:System.Math.Round%2A?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Single \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/single-data-type.md)   
 [Double \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/double-data-type.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)