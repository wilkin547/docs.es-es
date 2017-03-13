---
title: "Referencias y la instrucci&#243;n Imports (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ensamblados [Visual Basic], espacios de nombres"
  - "ensamblados [Visual Basic], referencias"
  - "Imports (instrucción), hacer referencia a ensamblados"
  - "espacios de nombres, ensamblados"
  - "referencias, ensamblado"
  - "hacer referencia a ensamblados"
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Referencias y la instrucci&#243;n Imports (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Para que el proyecto pueda disponer de objetos externos, elija el comando **Agregar referencia** del menú **Proyecto**.  Las referencias en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos pero contienen más información.  
  
## Instrucción Imports  
 Los ensamblados incluyen uno o varios espacios de nombres.  Cuando se agrega una referencia a un ensamblado, también puede agregarse una instrucción `Imports` a un módulo para controlar la visibilidad de los espacios de nombres del ensamblado dentro del módulo.  La instrucción `Imports` proporciona un contexto de control de ámbito que permite utilizar solamente la parte del espacio de nombres necesaria para suministrar una referencia única.  
  
 La instrucción `Imports` tiene la siguiente sintaxis:  
  
 `Imports` \[         `|` `Aliasname` \=\] `Namespace`  
  
 `Aliasname` hace referencia a un nombre corto que se puede utilizar en el código para referirse a un espacio de nombres importado.  `Namespace` es un espacio de nombres que está disponible mediante una referencia de proyecto, una definición dentro del proyecto o una instrucción `Imports` anterior.  
  
 Un módulo puede contener cualquier número de instrucciones `Imports`.  Éstas deben aparecer detrás de las instrucciones `Option`, si hay alguna, pero antes de cualquier otro código.  
  
> [!NOTE]
>  No hay que confundir las referencias de proyecto con las instrucciones `Imports` o `Declare`.  Las referencias de proyecto hacen que los objetos externos, como los objetos de ensamblados, estén disponibles para los proyectos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  La instrucción `Imports` se utiliza para simplificar el acceso a las referencias de proyecto, pero no facilita el acceso a dichos objetos.  La instrucción `Declare` se utiliza para declarar una referencia a un procedimiento externo de una biblioteca de vínculos dinámicos \(DLL\).  
  
## Utilizar alias con la instrucción Imports  
 La instrucción `Imports` facilita el acceso a los métodos de clases porque elimina la necesidad de escribir explícitamente los nombres completos de las referencias.  Los alias permiten asignar un nombre más descriptivo a una sola parte de un espacio de nombres.  Por ejemplo, la secuencia retorno de carro y avance de línea, que permite mostrar un texto en varias líneas, forma parte del módulo <xref:Microsoft.VisualBasic.ControlChars> del espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=fullName>.  Para utilizar esta constante en un programa que no tenga un alias, debe escribir el siguiente fragmento de código:  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 Las instrucciones `Imports` deben aparecer siempre en las primeras líneas, inmediatamente después de cualquier instrucción `Option` de un módulo.  El fragmento de código siguiente muestra cómo se importa y se asigna un alias al módulo <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>:  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 Las referencias que después se hagan a este espacio de nombres pueden ser mucho más breves:  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Si una instrucción `Imports` no incluye un nombre de alias, los elementos definidos en el espacio de nombres importado pueden utilizarse en el módulo sin calificación.  Si se especifica el nombre del alias, debe utilizarse como calificador de los nombres contenidos en dicho espacio de nombres.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ControlChars>   
 <xref:Microsoft.VisualBasic>   
 [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/es-es/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Cómo: Crear y utilizar ensamblados mediante la línea de comandos](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)   
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)