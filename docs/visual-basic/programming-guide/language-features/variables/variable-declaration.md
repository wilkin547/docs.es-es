---
title: "Declaraci&#243;n de variable en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], declaración"
  - "variables de miembro, declaraciones"
  - "instrucción Dim, declaración de variables"
  - "declarar variables"
  - "variables [Visual Basic], ámbito"
  - "variables [Visual Basic], tipos de datos"
  - "tipos de datos [Visual Basic], declaraciones de variables"
  - "duración, variables"
  - "variables [Visual Basic], duración"
  - "niveles de acceso, variables"
  - "ámbito, instrucciones de declaración"
  - "variables [Visual Basic], nivel de acceso"
  - "variables locales, declaraciones"
  - "ámbito, variables"
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 31
---
# Declaraci&#243;n de variable en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una variable se declara para especificar su nombre y sus características.  La instrucción de declaración para variables es [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md).  Su ubicación y contenido determinan las características de la variable.  
  
 Para las reglas de denominación de variables y consideraciones, consulte [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Niveles de declaración  
  
### Valor local y variables miembros  
 Una *variable local*  es aquella que se declara dentro de un procedimiento.  Una *variable miembro* es un miembro de un tipo de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]; se declara en el nivel de módulo, dentro de una clase, estructura o módulo, pero no dentro de ningún procedimiento interno de esa clase, estructura o módulo.  
  
### Variables compartidas y de instancias  
 La categoría de una variable miembro, en una clase o estructura, depende de que la variable esté o no compartida.  Si una variable se declara con la palabra clave [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), es una *variable compartida*, y existe en una única copia compartida por todas las instancias de la clase o estructura.  
  
 De lo contrario, es una *variable de instancia*, y se crea una copia independiente de ella para cada instancia de la clase o estructura.  Una copia determinada de una variable de instancia sólo está disponible en la instancia de la clase o estructura en que se creó.  Es independiente de una copia de la variable de instancia en cualquier otra instancia de la clase o estructura.  
  
## Declarar el tipo de datos  
 La cláusula [As](../../../../visual-basic/language-reference/statements/as-clause.md) de la instrucción de declaración permite definir el tipo de datos o de objetos de la variable que se está declarando.  Se puede especificar cualquiera de los siguientes tipos para una variable:  
  
-   Un tipo de datos básico, como `Boolean`, `Long` o `Decimal`.  
  
-   Un tipo de datos compuesto, como una matriz o una estructura.  
  
-   Un tipo de objeto o clase, definido en su aplicación o en otra aplicación  
  
-   Clase de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)], como <xref:System.Windows.Forms.Label> o <xref:System.Windows.Forms.TextBox>  
  
-   Un tipo de interfaz, como <xref:System.IComparable> o <xref:System.IDisposable>  
  
 Se pueden declarar varias declarar distintas variables en la misma instrucción sin necesidad de repetir el tipo de datos.  En las instrucciones siguientes, las variables `i`, `j`y `k` se declaran como tipo `Integer`, `l` y `m` como `Long`, y `x` e `y` como `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Para obtener más información acerca de tipos de datos, consulte [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md).  Para obtener más información sobre objetos, consulte [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) y [Programming with Components](../Topic/Programming%20with%20Components.md).  
  
## Inferencia de tipo de variable local  
 La *inferencia de tipos* se usa para determinar los tipos de datos de las variables locales que se han declarado sin ninguna cláusula `As`.  El compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización.  Esto permite declarar variables sin especificar un tipo de forma explícita.  En el ejemplo siguiente, `num1` y `num2` están fuertemente tipados como enteros.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/variable-declaration_1.vb)]  
  
 Si desea utilizar la inferencia de tipo de variable local, `Option Infer` debe estar establecido en `On`.  Para obtener más información, vea [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) y [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## Características de variables declaradas  
 El *período de duración* de una variable representa el tiempo durante el cual la variable está disponible para que pueda ser utilizada.  En general, una variable existe mientras el elemento que lo declara \(como un procedimiento o clase\) siga existiendo.  Si la variable no necesita seguir existiendo más allá de la duración de su elemento contenedor, no necesita hacer nada especial en la declaración.  Si la variable debe seguir existiendo durante más tiempo que su elemento contenedor, puede incluir la palabra clave `Static` o `Shared` en su instrucción `Dim`.  Para obtener más información, vea [Período de duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 El *ámbito* de una variable está formado por todo código que puede hacer referencia a la variable sin tener que calificar su nombre.  El ámbito de una variable está determinado por la ubicación en la que se haya declarado la variable.  El código de una región determinada puede utilizar las variables definidas en dicha región sin necesidad de especificar los nombres de las variables.  Para obtener más información, vea [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 El *nivel de acceso* de una variable es la extensión de código que tiene permiso para tener acceso a ella.  El modificador de acceso \(como [Public](../../../../visual-basic/language-reference/modifiers/public.md) o [Private](../../../../visual-basic/language-reference/modifiers/private.md)\) que utiliza en la instrucción `Dim` es quien determina esto.  Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Vea también  
 [Cómo: Crear una variable nueva](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)   
 [Cómo: Introducir y extraer los datos de una variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)