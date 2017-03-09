---
title: "/doc | Microsoft Docs"
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
  - "/doc (opción del compilador) [Visual Basic]"
  - "doc (opción del compilador) [Visual Basic]"
  - "-doc (opción del compilador) [Visual Basic]"
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /doc
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Procesa los comentarios de documentación generando un archivo XML.  
  
## Sintaxis  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`+`  &#124; `-`|Opcional.  Si se especifica \+, o simplemente `/doc`, el compilador genera información de documentación y la incluye en un archivo XML.  Especificar `-`  equivale a no especificar `/doc`, lo que hace que no se cree ninguna información de documentación.|  
|`file`|Obligatorio si se utiliza `/doc:`.  Especifica el archivo de salida de XML, que se llena con los comentarios de los archivos del código fuente de la compilación.  Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas \(" "\).|  
  
## Comentarios  
 La opción `/doc` controla si el compilador genera un archivo XML que contiene los comentarios de documentación.  Si utiliza la sintaxis `/doc:``file`, el parámetro `file` especifica el nombre del archivo XML.  Si utiliza `/doc` o `/doc+`, el compilador toma el nombre del archivo XML del archivo ejecutable o biblioteca que el compilador está creando.  Si utiliza `/doc-` o no especifica la opción `/doc`, el compilador no crea un archivo XML.  
  
 En archivos de código fuente, los comentarios de documentación pueden preceder a las definiciones siguientes:  
  
-   Tipos definidos por el usuario, como una [clase](../../../visual-basic/language-reference/statements/class-statement.md) o [interfaz](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Miembros, como un campo, [evento](../../../visual-basic/language-reference/statements/event-statement.md), [propiedad](../../../visual-basic/language-reference/statements/property-statement.md), [función](../../../visual-basic/language-reference/statements/function-statement.md) o [subrutina](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Para utilizar el archivo XML generado con la característica [IntelliSense](/visual-studio/ide/using-intellisense) de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)], el nombre de archivo XML debe ser el mismo que el ensamblado que desea compatibilizar.  Asegúrese de que el archivo XML esté en el mismo directorio que el ensamblado de modo que cuando se haga referencia a éste último en el proyecto de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)], se encuentre también el archivo .xml.  Los archivos de documentación XML no son necesarios para que IntelliSense funcione para un código dentro de un proyecto o dentro de proyectos a los que hace referencia un proyecto.  
  
 A menos que compile con `/target:module`, el archivo XML contiene etiquetas `<assembly></assembly>`.  Estas etiquetas especifican el nombre del archivo que contiene el manifiesto del ensamblado para el archivo de salida de la compilación.  
  
 Vea [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) para conocer modos de generar documentación a partir de los comentarios del código.  
  
||  
|-|  
|Para establecer \/doc en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Compilar**.<br />3.  Establezca el valor en el cuadro **Generar archivo de documentación XML**.|  
  
## Ejemplo  
 Vea [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) para obtener un ejemplo.  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Documentar el código con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)