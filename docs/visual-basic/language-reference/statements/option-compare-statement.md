---
title: "Option Compare (Instrucci&#243;n) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Compare"
  - "vb.OptionCompare"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comparación binaria"
  - "comparación binaria, Option Compare (instrucción)"
  - "Binary (palabra clave), Option Compare (instrucción)"
  - "distinción de mayúsculas y minúsculas, Option Compare (instrucción)"
  - "Compare (palabra clave)"
  - "Option Compare (instrucción)"
  - "comparación de cadenas [Visual Basic], Option Compare (instrucción)"
  - "comparación de cadenas [Visual Basic], ordenar datos"
  - "cadenas [Visual Basic], comparar"
  - "cadenas [Visual Basic], devolver desde funciones"
  - "texto [Visual Basic], comparar"
  - "Text (palabra clave), Option Compare (instrucción)"
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: 37
caps.handback.revision: 37
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Compare (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Declara el método de comparación predeterminado que se utiliza al comparar datos de cadena.  
  
## Sintaxis  
  
```  
Option Compare { Binary | Text }  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`Binary`|Opcional.  Genera comparaciones de cadenas basadas en un criterio de ordenación que se deriva de las representaciones binarias internas de los caracteres.<br /><br /> Este tipo de comparación es especialmente útil si las cadenas pueden contener caracteres que no serán interpretados como texto.  En este caso, no conviene desviar las comparaciones con equivalencias alfabéticas, como la no distinción entre mayúsculas y minúsculas.|  
|`Text`|Opcional.  Genera comparaciones de cadenas basadas en un criterio de ordenación de texto sin distinción entre mayúsculas y minúsculas, determinado por la configuración regional del sistema.<br /><br /> Este tipo de comparación es útil si las cadenas contienen todos los caracteres de texto y si desea compararlas teniendo en cuenta equivalencias alfabéticas, como la no distinción entre mayúsculas y minúsculas y las letras estrechamente relacionadas.  Por ejemplo, tal vez le interese considerar que `A` y `a` son iguales, y que `Ä` y `ä` van antes que `B` y `b`.|  
  
## Comentarios  
 Si se utiliza la instrucción `Option Compare`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.  
  
 La instrucción `Option Compare` especifica el método de comparación de cadenas \(`Binary` o `Text`\).  El método de comparación de texto predeterminado es `Binary`.  
  
 Una comparación `Binary` compara el valor numérico de Unicode de cada carácter en cada cadena.  Una comparación `Text` compara cada carácter Unicode basándose en su significado léxico en la referencia cultural actual.  
  
 En Microsoft Windows, el criterio de ordenación viene determinado por la página de código.  Para obtener más información, vea [Páginas de códigos](/visual-cpp/c-runtime-library/code-pages).  
  
 En el ejemplo siguiente, los caracteres de la página de códigos inglés\/europeo \(ANSI 1252\) se ordenan mediante el uso de `Option Compare Binary`, lo que genera un criterio de ordenación binario típico.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Cuando se ordenan los mismos caracteres en la misma página de código mediante el uso de `Option Compare Text`, se genera el siguiente criterio de ordenación de texto.  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## Cuando la instrucción Option Compare no está presente  
 Si el código fuente no contiene una instrucción `Option Compare`, se utiliza la configuración de **Option Compare** de [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  Si utiliza el compilador de línea de comandos, se utiliza la configuración especificada por la opción del compilador [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
#### Cómo establecer Option Compare en el IDE  
  
1.  En el **Explorador de soluciones**, seleccione un proyecto.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/es-es/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Haga clic en la pestaña **Compilar**.  
  
3.  Establezca el valor en el cuadro **Option Compare**.  
  
 Cuando se crea un proyecto, el valor **Option Compare** de la ficha **Compilar** está establecido en el valor **Option Compare** del cuadro de diálogo **Opciones**.  Para cambiar esta configuración, en el menú **Herramientas**, haga clic en **Opciones**.  En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, a continuación, haga clic en **Valores predeterminados de VB**.  El valor predeterminado inicial de **Valores predeterminados de VB** es **Binario**.  
  
#### Cómo establecer Option Compare en la línea de comandos  
  
-   Incluya la opción del compilador [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) en el comando **vbc**.  
  
## Ejemplo  
 El ejemplo siguiente utiliza la instrucción `Option Compare` para establecer la comparación binaria como método predeterminado de comparación de cadenas.  Para utilizar este código, quite el comentario de la instrucción `Option Compare Binary` y colóquelo en la parte superior del archivo de origen.  
  
 [!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]  
  
## Ejemplo  
 El ejemplo siguiente se utiliza la instrucción `Option Compare` para establecer el criterio de ordenación de texto sin distinción entre mayúsculas y minúsculas como método predeterminado de comparación de cadenas.  Para utilizar este código, quite el comentario de la instrucción `Option Compare Text` y colóquelo en la parte superior del archivo de origen.  
  
 [!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>   
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>   
 <xref:Microsoft.VisualBasic.Strings.Replace%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Like \(Operador\)](../../../visual-basic/language-reference/operators/like-operator.md)   
 [Funciones de cadena](../../../visual-basic/language-reference/functions/string-functions.md)   
 [Option Explicit \(Instrucción\)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)