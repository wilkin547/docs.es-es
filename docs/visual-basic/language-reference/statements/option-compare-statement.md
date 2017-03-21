---
title: "Option Compare (instrucción) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Compare
- vb.OptionCompare
dev_langs:
- VB
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword
- binary comparison
- strings [Visual Basic], returning from functions
- binary comparison, Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword, Option Compare statement
- Binary keyword, Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: 37
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8b1b077a8818315e52ada6b08ff1e1ced9bbd17c
ms.lasthandoff: 03/13/2017

---
# <a name="option-compare-statement"></a>Option Compare (Instrucción)
Declara el método de comparación predeterminado que se utiliza al comparar datos de cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`Binary`|Opcional. Genera comparaciones de cadenas basadas en un criterio de ordenación que se deriva de las representaciones binarias internas de los caracteres.<br /><br /> Este tipo de comparación es especialmente útil si las cadenas pueden contener caracteres que no serán interpretados como texto. En este caso, no conviene desviar las comparaciones con equivalencias alfabéticas, como la no distinción entre mayúsculas y minúsculas.|  
|`Text`|Opcional. Genera comparaciones de cadenas basadas en un criterio de ordenación de texto sin distinción entre mayúsculas y minúsculas, determinado por la configuración regional del sistema.<br /><br /> Este tipo de comparación es útil si las cadenas contienen todos los caracteres de texto y si desea compararlas teniendo en cuenta equivalencias alfabéticas, como la no distinción entre mayúsculas y minúsculas y las letras estrechamente relacionadas. Por ejemplo, tal vez le interese considerar que `A` y `a` son iguales, y que `Ä` y `ä` van antes que `B` y `b`.|  
  
## <a name="remarks"></a>Comentarios  
 Si se utiliza la instrucción `Option Compare`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.  
  
 La instrucción `Option Compare` especifica el método de comparación de cadenas (`Binary` o `Text`).  El método de comparación de texto predeterminado es `Binary`.  
  
 Una comparación `Binary` compara el valor numérico de Unicode de cada carácter en cada cadena. Una comparación `Text` compara cada carácter Unicode basándose en su significado léxico en la referencia cultural actual.  
  
 En Microsoft Windows, el criterio de ordenación viene determinado por la página de código. Para obtener más información, vea [Páginas de códigos](https://docs.microsoft.com/cpp/c-runtime-library/code-pages).  
  
 En el ejemplo siguiente, los caracteres de la página de códigos inglés/europeo (ANSI 1252) se ordenan mediante el uso de `Option Compare Binary`, lo que genera un criterio de ordenación binario típico.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Cuando se ordenan los mismos caracteres en la misma página de código mediante el uso de `Option Compare Text`, se genera el siguiente criterio de ordenación de texto.  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a>Cuando la instrucción Option Compare no está presente  
 Si el código fuente no contiene una `Option Compare` instrucción, el **Option Compare** en el [página compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza. Si utiliza el compilador de línea de comandos, la configuración especificada por el [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) se utiliza la opción del compilador.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a>Cómo establecer Option Compare en el IDE  
  
1.  En **el Explorador de soluciones**, seleccione un proyecto. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [NIB: administrar propiedades del proyecto con el Diseñador de proyectos](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Haga clic en el **compilar** ficha.  
  
3.  Establezca el valor de la **Option Compare** cuadro.  
  
 Cuando se crea un proyecto, el **Option Compare** en el **compilar** ficha se establece en el **Option Compare** en el **opciones** cuadro de diálogo. Para cambiar esta configuración, en la **herramientas** menú, haga clic en **opciones**. En el **opciones** diálogo cuadro, expanda **proyectos y soluciones**y, a continuación, haga clic en **valores predeterminados de VB**. El valor predeterminado inicial de **valores predeterminados de VB** es **binario**.  
  
#### <a name="to-set-option-compare-on-the-command-line"></a>Cómo establecer Option Compare en la línea de comandos  
  
-   Incluir el [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) opción del compilador en el **vbc** comando.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza la instrucción `Option Compare` para establecer la comparación binaria como método predeterminado de comparación de cadenas. Para utilizar este código, quite el comentario de la instrucción `Option Compare Binary` y colóquelo en la parte superior del archivo de origen.  
  
 [!code-vb[VbVbalrStatements nº&45;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se utiliza la instrucción `Option Compare` para establecer el criterio de ordenación de texto sin distinción entre mayúsculas y minúsculas como método predeterminado de comparación de cadenas. Para utilizar este código, quite el comentario de la instrucción `Option Compare Text` y colóquelo en la parte superior del archivo de origen.  
  
 [!code-vb[VbVbalrStatements nº&46;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A></xref:Microsoft.VisualBasic.Strings.InStr%2A>   
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A></xref:Microsoft.VisualBasic.Strings.InStrRev%2A>   
 <xref:Microsoft.VisualBasic.Strings.Replace%2A></xref:Microsoft.VisualBasic.Strings.Replace%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A></xref:Microsoft.VisualBasic.Strings.StrComp%2A>   
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Like (operador)](../../../visual-basic/language-reference/operators/like-operator.md)   
 [Funciones de cadena](../../../visual-basic/language-reference/functions/string-functions.md)   
 [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
