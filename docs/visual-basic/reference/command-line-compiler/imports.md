---
title: "/imports (Visual Basic) | Microsoft Docs"
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
  - "/imports (opción del compilador) [Visual Basic]"
  - "imports (opción del compilador) [Visual Basic]"
  - "-imports (opción del compilador) [Visual Basic]"
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /imports (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Importa espacios de nombres desde un ensamblado especificado.  
  
## Sintaxis  
  
```  
/imports:namespaceList  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`namespaceList`|Obligatorio.  Lista delimitada por comas de espacios de nombres que se van a importar.|  
  
## Comentarios  
 La opción `/imports` permite importar cualquier espacio de nombres definido dentro del conjunto actual de archivos de código fuente o de cualquier ensamblado al que se haga referencia.  
  
 Los miembros de un espacio de nombres especificado con `/imports` están disponibles para todos los archivos de código fuente de la compilación.  Use [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para utilizar un espacio de nombres en un único archivo de código fuente.  
  
||  
|-|  
|Para establecer \/imports en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Referencias**.<br />3.  Escriba el nombre del espacio de nombres en el cuadro situado junto al botón **Agregar importación del usuario**.<br />4.  Haga clic en el botón **Agregar importación del usuario**.|  
  
## Ejemplo  
 Las siguientes líneas de código compilan cuando se especifica `/imports:system`.  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)