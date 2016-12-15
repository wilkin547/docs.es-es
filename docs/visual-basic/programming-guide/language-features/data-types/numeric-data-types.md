---
title: "Tipos de datos num&#233;ricos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], numéricos"
  - "Decimal (tipo de datos), tipos de datos numéricos"
  - "Double (tipo de datos), tipos de datos numéricos"
  - "exponente, de números fraccionarios"
  - "tipos de datos fraccionarios"
  - "fracciones"
  - "Integer (tipo de datos), tipos de datos numéricos"
  - "números enteros"
  - "enteros"
  - "tipos enteros, Visual Basic"
  - "Long (tipo de datos), tipos de datos numéricos de Visual Basic"
  - "mantisas"
  - "mantisas, de números fraccionarios"
  - "números"
  - "números, enteros"
  - "números, enteros"
  - "tipos de datos numéricos, Visual Basic"
  - "Short (tipo de datos), tipos de datos numéricos"
  - "Single (tipo de datos), tipos numéricos"
  - "números enteros"
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tipos de datos num&#233;ricos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona diversos *tipos de datos numéricos* para controlar números en varias representaciones.  Los tipos *integrales* representan sólo números enteros \(positivos, negativos y cero\) y los tipos *no integrales* representan números con partes enteras y fraccionarias.  
  
 Para ver una tabla en la que se muestra una comparación en paralelo de los tipos de datos de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], vea [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## Tipos numéricos integrales  
 Los *tipos de datos integrales* son aquellos que sólo representan números sin partes fraccionarias.  
  
 Los tipos de datos integrales *con signo* son [SByte \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) \(de 8 bits\), [Short \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/short-data-type.md) \(de 16 bits\), [Integer \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/integer-data-type.md) \(de 32 bits\) y [Long \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/long-data-type.md) \(de 64 bits\).  Si una variable almacena siempre enteros en lugar de números fraccionarios, declárela como uno de estos tipos.  
  
 Los tipos enteros *sin signo* son [Byte \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/byte-data-type.md) \(de 8 bits\), [UShort \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) \(de 16 bits\), [UInteger \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) \(de 32 bits\) y [ULong \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) \(de 64 bits\).  Si una variable contiene datos binarios o datos de naturaleza desconocida, declárela como uno de estos tipos.  
  
### Rendimiento  
 Los operadores aritméticos son más rápidos con los tipos enteros que con cualquier otro tipo de datos.  Son más rápidos con los tipos `Integer` y `UInteger` de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### Enteros grandes  
 Si es preciso que contenga un entero mayor que el que es capaz de contener el tipo de datos `Integer`, puede usar en su lugar el tipo de datos `Long`.  Las variables `Long` pueden contener números comprendidos entre \-9.223.372.036.854.775.808 y 9.223.372.036.854.775.807.  Las operaciones con `Long` son ligeramente más lentas que con `Integer`.  
  
 Si necesita valores aun más grandes, puede utilizar [Decimal \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/decimal-data-type.md).  Puede contener números de \-79.228.162.514.264.337.593.543.950,335 a 79.228.162.514.264.337.593.543.950,335 en una variable `Decimal` si no utiliza ninguna posición decimal.  Sin embargo, las operaciones con números `Decimal` son considerablemente más lentas que con cualquier otro tipo de dato numérico.  
  
### Enteros pequeños  
 Si no necesita el intervalo completo del tipo de datos `Integer`, puede utilizar el tipo de datos `Short`, que puede contener enteros comprendidos entre \-32.768 y 32.767.  En el caso del intervalo de enteros más pequeño, el tipo de datos `SByte` contiene los enteros comprendidos entre \-128 y 127.  Si tiene un número muy grande de variables que contienen enteros pequeños, Common Language Runtime puede almacenar a veces las variables `Short` y `SByte` de un modo más eficaz y ahorrar espacio de memoria.  Sin embargo, las operaciones con `Short` y `SByte` son algo más lentas que con `Integer`.  
  
### Enteros sin signo  
 Si sabe que la variable no va a necesitar contener nunca un número negativo, puede utilizar los *tipos sin signo* `Byte`, `UShort`, `UInteger` y `ULong`.  Cada uno de estos tipos de datos puede contener un entero positivo dos veces más grande que su tipo con signo correspondiente \(`SByte`, `Short`, `Integer` y `Long`\).  En lo que se refiere a rendimiento, un tipo sin signo es exactamente tan eficaz como su tipo con signo correspondiente.  En particular, `UInteger` comparte con `Integer` la distinción de ser el más eficaz de todos los tipos de datos numérico básicos.  
  
## Tipos numéricos no integrales  
 Los *tipos de datos no integrales* son aquellos que representan números que contienen tanto partes enteras como decimales.  
  
 Los tipos de datos numéricos no integrales son `Decimal` \(punto fijo de 128 bits\), [Single \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/single-data-type.md) \(punto flotante de 32 bits\) y [Double \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/double-data-type.md) \(punto flotante de 64 bits\).  Todos ellos son tipos con signo.  Si una variable puede contener una fracción, declárela como variable de uno de estos tipos.  
  
 `Decimal`  no es un tipo de datos de punto flotante.  Los números de tipo `Decimal` tienen un valor entero binario y un factor de escala de entero que especifica qué parte del valor es una fracción decimal.  
  
 Puede utilizar las variables de `Decimal` por los valores de moneda.  la ventaja es la precisión de los valores.  El tipo de datos `Double` es más rápido y requiere menos memoria, pero está sujeto a errores de redondeo.  El tipo de datos de `Decimal` proporciona una exactitud total en 28 posiciones decimales.  
  
 Los números con punto flotante \(`Single` y `Double`\) tienen intervalos mayores que los números `Decimal` pero pueden estar sujetos a errores de redondeo.  Los tipos de punto flotante admiten menos dígitos significativos que `Decimal` pero pueden representar valores de mayor magnitud.  
  
 Los valores de números no integrales se pueden expresar como mmmEeee, donde mmm es la *mantisa* \(dígitos significativos\) y eee es el *exponente* \(una potencia de 10\).  Los valores positivos superiores de los tipos no integrales son 7.9228162514264337593543950335E\+28 para `Decimal`, 3.4028235E\+38 para `Single` y 1.79769313486231570E\+308 para `Double`.  
  
### Rendimiento  
 `Double` es el más eficaz de los tipos de datos fraccionarios, porque los procesadores de las plataformas actuales realizan las operaciones de punto flotante en precisión doble.  Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.  
  
### Magnitudes pequeñas  
 Para los números con la magnitud más pequeña posible \(cercana a 0\), las variables `Double` pueden contener números tan pequeños como \-4.94065645841246544E\-324 para valores negativos y 4.94065645841246544E\-324 para valores positivos.  
  
### Números fraccionarios pequeños  
 Si no necesita el intervalo completo del tipo de datos `Double`, puede utilizar el tipo de datos `Single`, que puede contener números de punto flotante comprendidos entre \-3.4028235E\+38 y 3.4028235E\+38.  Las magnitudes más pequeñas para las variables `Single` son \-1.401298E\-45 para valores negativos y 1.401298E\-45 para valores positivos.  Si tiene un número muy grande de variables que contienen números en punto flotante pequeños, Common Language Runtime puede almacenar a veces las variables `Single` de un modo más eficaz y ahorrar espacio de memoria.  
  
## Vea también  
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos de caracteres](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Tipos de datos varios](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Cómo: Llamar a una función de Windows que adopta tipos sin signo](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)