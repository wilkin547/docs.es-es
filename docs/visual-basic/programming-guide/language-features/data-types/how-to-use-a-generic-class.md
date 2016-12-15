---
title: "C&#243;mo: Usar clases gen&#233;ricas (Visual Basic) | Microsoft Docs"
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
  - "parámetros de tipo, definir"
  - "argumentos de tipo de datos, definir"
  - "argumentos [Visual Basic], tipos de datos"
  - "Of (palabra clave), usar"
  - "parámetros genéricos"
  - "parámetros de tipo de datos"
  - "genéricos [Visual Basic], acerca de los genéricos"
  - "tipos de datos [Visual Basic], como parámetros"
  - "tipos de datos [Visual Basic], como argumentos"
  - "parámetros, tipo"
  - "tipos [Visual Basic], genéricos"
  - "parámetros, genéricos"
  - "genéricos [Visual Basic], crear tipos genéricos"
  - "argumentos de tipo de datos"
  - "parámetros, tipo de datos"
  - "parámetros de tipo de datos, definir"
  - "argumentos de tipo, definir"
  - "argumentos [Visual Basic], tipo"
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Usar clases gen&#233;ricas (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Las clases que toman *parámetros de tipo* se denominan *clases genéricas*. Si usa una clase genérica, puede generar una *clase construida* a partir de ella proporcionando un *argumento de tipo* para cada uno de estos parámetros. Después, puede declarar una variable del tipo de clase construida, crear una instancia de la clase construida y asignarla a esa variable.  
  
 Además de clases, también puede definir y usar estructuras genéricas, interfaces, procedimientos y delegados.  
  
 En el procedimiento siguiente se toma una clase genérica definida en [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] y se crea una instancia a partir de ella.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Para usar una clase que toma un parámetro de tipo  
  
1.  Al principio de su archivo de origen, incluya una [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para importar el espacio de nombres <xref:System.Collections.Generic?displayProperty=fullName>. Esto le permite hacer referencia a la clase <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> sin tener que usar su nombre completo para diferenciarla de otras clases queue, como <xref:System.Collections.Queue?displayProperty=fullName>.  
  
2.  Cree el objeto de la manera normal, pero agregue `(Of` `type``)` inmediatamente después del nombre de clase.  
  
     En el ejemplo siguiente se usa la misma clase (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) para crear dos objetos queue que contienen elementos de distintos tipos de datos. Agrega elementos al final de cada cola y, después, quita y muestra los elementos de la parte delantera de cada cola.  
  
     [!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)   
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Cómo: Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)