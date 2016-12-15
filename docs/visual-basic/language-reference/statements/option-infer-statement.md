---
title: "Option Infer (instrucci&#243;n) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.OptionInfer"
  - "vb.Infer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declarar variables, inferidas"
  - "Infer (palabra clave)"
  - "declaración inferida de variables"
  - "Option Infer (instrucción)"
  - "variables [Visual Basic], declarar"
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: 72
caps.handback.revision: 72
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Infer (instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Permite el uso de la inferencia de tipo de variable local en la declaración de variables.  
  
## Sintaxis  
  
```  
Option Infer { On | Off }  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`On`|Opcional.  Habilita la inferencia de tipo de variable local.|  
|`Off`|Opcional.  Deshabilita la inferencia de tipo de variable local.|  
  
## Comentarios  
 Para establecer `Option Infer` en un archivo, escriba `Option Infer On` o `Option Infer Off` en la parte superior del archivo, antes de cualquier otro código fuente.  Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.  
  
 Al establecer `Option Infer` en `On`, puede declarar variables locales sin especificar explícitamente un tipo de datos.  El compilador deduce el tipo de datos de una variable a partir del tipo de su expresión de inicialización.  
  
 En la siguiente ilustración, `Option Infer` está activado.  La variable de la declaración `Dim someVar = 2` se declara como un entero mediante la inferencia de tipo.  
  
 ![Vista IntelliSense de la declaración.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")  
IntelliSense cuando Option Infer está activado  
  
 En la siguiente ilustración, `Option Infer` está desactivado.  La variable de la declaración `Dim someVar = 2` se declara como un `Object` mediante la inferencia de tipo.  En este ejemplo, **Option Strict** está configurado en **Off** en [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  
  
 ![Vista IntelliSense de la declaración.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")  
IntelliSense cuando Option Infer está desactivado  
  
> [!NOTE]
>  Cuando una variable se declara como un `Object`, el tipo de tiempo de ejecución puede cambiar mientras se ejecuta el programa.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] realiza operaciones llamadas *boxing* y *unboxing* para realizar una conversión entre un `Object` y un tipo de valor, lo que ralentiza la ejecución.  Para obtener información sobre las conversiones boxing y unboxing, consulte [Especificación del lenguaje de Visual Basic](../../../visual-basic/reference/language-specification.md).  
  
 La inferencia de tipo se aplica en el nivel de procedimiento, y no se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz.  
  
 Para obtener información adicional, vea [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## Cuando la instrucción Option Infer no está presente  
 Si el código fuente no contiene una instrucción `Option Infer`, se utiliza la configuración **Option Infer** de [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  Si se utiliza el compilador de línea de comandos, se usa la opción del compilador [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md).  
  
#### Cómo establecer Option Infer en el IDE  
  
1.  En el **Explorador de soluciones**, seleccione un proyecto.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/es-es/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Haga clic en la pestaña **Compilar**.  
  
3.  Establezca el valor en el cuadro **Option Infer**.  
  
 Al crear un proyecto nuevo, el ajuste **Option Infer** de la ficha **Compilar** se establece en el ajuste **Option Infer** del cuadro de diálogo **Valores predeterminados de VB**.  Para acceder al cuadro de diálogo **Valores predeterminados de VB**, en el menú **Herramientas**, haga clic en **Opciones**.  En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, a continuación, haga clic en **Valores predeterminados de VB**.  El valor predeterminado inicial de **Valores predeterminados de VB** es `On`.  
  
#### Cómo establecer Option Infer en la línea de comandos  
  
-   Incluya la opción del compilador [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) en el comando **vbc**.  
  
## Tipos de datos y valores predeterminados  
 En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.  
  
|||||  
|-|-|-|-|  
|¿Tipo de datos especificado?|¿Inicializador especificado?|Ejemplo|Resultado|  
|No|No|`Dim qty`|Si `Option Strict` está desactivado \(valor predeterminado\), la variable se establece en `Nothing`.<br /><br /> Si `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|No|Sí|`Dim qty = 5`|Si `Option Infer` está activado \(valor predeterminado\), la variable toma el tipo de datos del inicializador.  Vea [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.|  
|Sí|No|`Dim qty As Integer`|La variable se inicializa con el valor predeterminado del tipo de datos.  Para obtener más información, vea [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Sí|Sí|`Dim qty  As Integer = 5`|Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.|  
  
## Ejemplo  
 Los ejemplos siguientes muestran cómo la instrucción `Option Infer` habilita la inferencia de tipo local.  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## Ejemplo  
 El siguiente ejemplo demuestra que el tipo en tiempo de ejecución puede ser diferente cuando una variable se identifica como un `Object`.  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## Vea también  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Compare \(Instrucción\)](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Option Explicit \(Instrucción\)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones \(Cuadro de diálogo\)](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Conversión boxing y conversión unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)