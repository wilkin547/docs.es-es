---
title: "Caracteres de tipo (Visual Basic) | Microsoft Docs"
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
  - "! (carácter de tipo identificador)"
  - "# (carácter de tipo identificador)"
  - "$ (carácter de tipo identificador)"
  - "% (carácter de tipo identificador)"
  - "& (carácter de tipo identificador)"
  - "&H (prefijo para valores hexadecimales)"
  - "&O (prefijo para valores octales)"
  - "@ (carácter de tipo identificador)"
  - "C (carácter de tipo literal)"
  - "caracteres, tipo de identificador"
  - "D (carácter de tipo literal)"
  - "tipos de datos [Visual Basic], caracteres de tipo"
  - "tipos literales predeterminados"
  - "predeterminados, tipos literales"
  - "F (carácter de tipo literal)"
  - "literales hexadecimales"
  - "I (carácter de tipo literal)"
  - "caracteres de tipo identificador"
  - "L (carácter de tipo literal)"
  - "caracteres de tipo literal"
  - "tipos literales, predeterminado"
  - "literales, tipos predeterminados"
  - "literales, hexadecimales"
  - "literales, octales"
  - "literales octales"
  - "R (carácter de tipo literal)"
  - "S (carácter de tipo literal)"
  - "caracteres de tipo"
  - "caracteres de tipo, identificador"
  - "caracteres de tipo, literal"
  - "caracteres de tipo literal de interfaz de usuario"
  - "UL (caracteres de tipo literal)"
  - "US (caracteres de tipo literal)"
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Caracteres de tipo (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación con un *carácter de tipo*.  El carácter de tipo debe ir justo después del elemento, sin ningún tipo de carácter intermedio.  
  
 El carácter de tipo no forma parte del nombre del elemento.  Se puede hacer referencia a un elemento definido con un carácter de tipo sin el carácter de tipo.  
  
## Caracteres de tipo identificador  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona un conjunto de *caracteres de tipo identificador* que se pueden utilizar en una declaración para especificar el tipo de datos de una variable o constante.  La tabla siguiente muestra los caracteres de tipo identificador disponibles, con ejemplos de su utilización.  
  
|Carácter de tipo identificador|Tipo de datos|Ejemplo|  
|------------------------------------|-------------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 No existe ningún carácter de tipo identificador para los tipos de datos `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong` o `UShort`, ni para los tipos de datos compuestos como matrices o estructuras.  
  
 En algunos casos, puede anexar el carácter `$` a una función de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], por ejemplo `Left$` en lugar de `Left`, para obtener un valor devuelto de tipo `String`.  
  
 En todos los casos, el carácter de tipo identificador debe ir inmediatamente después del nombre del identificador.  
  
## Caracteres de tipo literal  
 Un *literal* es una representación textual de un valor determinado de un tipo de datos.  
  
### Tipos de literales predeterminados  
 El formato de un literal tal como aparece en el código suele determinar su tipo de datos.  La siguiente tabla muestra estos tipos predeterminados.  
  
|Formato textual de literal|Tipo de datos predeterminado|Ejemplo|  
|--------------------------------|----------------------------------|-------------|  
|Numérico, ninguna parte fraccionaria|`Integer`|`2147483647`|  
|Numérico, ningún parte fraccionaria, demasiado grande para `Integer`|`Long`|`2147483648`|  
|Numérico, parte fraccionaria|`Double`|`1.2`|  
|Entre comillas dobles|`String`|`"A"`|  
|Incluido con signos de número|`Date`|`#5/17/1993 9:32 AM#`|  
  
### Tipo de literales forzados  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona un conjunto de *caracteres de tipo literal*, que puede utilizar para forzar que un literal adopte un tipo de datos distinto del que indica su formato.  Para hacerlo, anexe el carácter al final del literal.  La tabla siguiente muestra los caracteres de tipo literal disponibles, con ejemplos de su utilización.  
  
|Caracteres de tipo literal|Tipo de datos|Ejemplo|  
|--------------------------------|-------------------|-------------|  
|`S`|`Short`|`I = 347S`|  
|`I`|`Integer`|`J = 347I`|  
|`L`|`Long`|`K = 347L`|  
|`D`|`Decimal`|`X = 347D`|  
|`F`|`Single`|`Y = 347F`|  
|`R`|`Double`|`Z = 347R`|  
|`US`|`UShort`|`L = 347US`|  
|`UI`|`UInteger`|`M = 347UI`|  
|`UL`|`ULong`|`N = 347UL`|  
|`C`|`Char`|`Q = "."C`|  
  
 No existe ningún carácter de tipo literal para los tipos de datos `Boolean`, `Byte`, `Date`, `Object`, `SByte` o `String`, ni para los tipos de datos compuestos como matrices o estructuras.  
  
 Los literales también pueden utilizar los caracteres de tipo identificador \(`%`, `&`, `@`, `!`, `#`, `$`\), tal y como lo hacen las variables, constantes y expresiones.  Sin embargo, los caracteres de tipo literal \(`S`, `I`, `L`, `D`, `F`, `R`, `C`\) sólo se pueden utilizar con literales.  
  
 En todos los casos, el carácter de tipo literal debe ir inmediatamente después del valor de literal.  
  
## Literales hexadecimales y octales  
 El compilador traduce normalmente un literal entero para que esté en el sistema numérico decimal \(base 10\).  Puede forzar un literal entero para que sea hexadecimal \(base 16\) con el prefijo `&H` y puede forzarle para que sea octal \(base 8\) con el prefijo `&O`.  Los dígitos que van a continuación del prefijo deben ser adecuados para el sistema numérico.  Esto se muestra en la tabla siguiente:  
  
|Base numérica|Prefijo|Valores de dígitos válidos|Ejemplo|  
|-------------------|-------------|--------------------------------|-------------|  
|Hexadecimal \(base 16\)|`&H`|0\-9 y A\-F|`&HFFFF`|  
|Octal \(base 8\)|`&O`|0\-7|`&O77`|  
  
 Puede agregar a un literal prefijado un carácter de tipo literal.  Esto se muestra en el siguiente ejemplo.  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 En el ejemplo anterior, `counter` tiene el valor decimal de \-32768 y `flags`, el valor decimal de \+32768.  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)