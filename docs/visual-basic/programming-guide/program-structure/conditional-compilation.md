---
title: "Compilaci&#243;n condicional en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "compilación, condicional"
  - "compilación condicional, acerca de la compilación condicional"
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Compilaci&#243;n condicional en Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En la *compilación condicional*, se compilan de forma selectiva bloques determinados del código de un programa mientras que otros se omiten.  
  
 Por ejemplo, podría interesarle escribir instrucciones de depuración que comparen la velocidad de varios enfoques de la misma tarea de programación o quizá desee adaptar una aplicación en varios idiomas.  Las instrucciones de compilación condicional se han concebido para su ejecución en tiempo de compilación, no durante la ejecución.  
  
 Los bloques de código que se compilarán de forma condicional se denotan con la directiva `#If...Then...#Else`.  Por ejemplo, para crear versiones en francés y alemán de la misma aplicación a partir del mismo código fuente, incruste segmentos de código específicos de la plataforma correspondiente en instrucciones `#If...Then`, por medio de las constantes predefinidas `FrenchVersion` y `GermanVersion`.  En el ejemplo siguiente se explica cómo hacerlo:  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 Si establece el valor de la constante de compilación condicional `FrenchVersion` en `True` en tiempo de compilación, se compila el código condicional de la versión en francés.  Si define el valor de la constante `GermanVersion` como `True`, el compilador usa la versión en alemán.  Si ninguna de las dos está establecida en `True`, se ejecuta el código del último bloque `Else`.  
  
> [!NOTE]
>  Autocompletar no funcionará al editar código y utiliza directivas de compilación condicional si el código no forma parte de la bifurcación actual.  
  
## Declarar constantes de compilación condicional  
 Existen tres métodos para definir las constantes de compilación condicional:  
  
-   En el **Diseñador de proyectos**  
  
-   En la línea de comandos, cuando se utiliza el compilador de la línea de comandos.  
  
-   En el código.  
  
 Las constantes de compilación condicional tienen un ámbito especial y no está permitido el acceso a ellas desde el código estándar.  El ámbito de una constante de compilación condicional depende de cómo se ha definido.  En la tabla siguiente se muestra una lista del ámbito de las constantes declaradas siguiendo los tres métodos antes mencionados.  
  
|||  
|-|-|  
|Método de definición de la constante|Ámbito de la constante|  
|**Diseñador de proyectos**|Público para todos los archivos del proyecto|  
|Línea de comandos|Público para todos los archivos que se pasen al compilador de la línea de comandos|  
|Instrucción `#Const` en el código|Privado para el archivo en que se declara|  
  
||  
|-|  
|Para establecer las constantes en el Diseñador de proyectos|  
|-   Antes de crear el archivo ejecutable, defina las constantes en el **Diseñador de proyectos** siguiendo el procedimiento descrito en [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67).|  
  
||  
|-|  
|Para definir constantes en la línea de comandos|  
|-   Use el modificador **\/d** para especificar constantes de compilación condicional, como en el ejemplo siguiente:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     No se requiere un espacio entre el modificador **\/d** y la primera constante.  Para obtener más información, vea [\/define](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Las declaraciones de la línea de comandos reemplazan las especificadas en el **Diseñador de proyectos**, pero no las borran.  Los argumentos definidos en el **Diseñador de proyectos** permanecen activos durante las compilaciones subsiguientes.<br />     A la hora de escribir constantes en el propio código no existen reglas estrictas en cuanto a su ubicación, puesto que su ámbito es el módulo completo en el que se declaran.|  
  
||  
|-|  
|Para definir constantes en el código|  
|-   Sitúe las constantes en el bloque de declaración del módulo en el que se utilicen.  De esta forma se facilitan la organización del código y su lectura.|  
  
## Temas relacionados  
  
|||  
|-|-|  
|Título|Descripción|  
|[Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Ofrece sugerencias para facilitar la lectura y el mantenimiento del código.|  
  
## Referencia  
 [\#Const \(Directiva\)](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)