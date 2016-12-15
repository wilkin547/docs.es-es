---
title: "/out (Visual Basic) | Microsoft Docs"
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
  - "/out (opción del compilador) [Visual Basic]"
  - "out (opción del compilador) [Visual Basic]"
  - "-out (opción del compilador) [Visual Basic]"
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /out (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica el nombre del archivo de salida.  
  
## Sintaxis  
  
```  
/out:filename  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`filename`|Obligatorio.  El nombre del archivo de salida creado por el compilador.  Si el nombre de archivo contiene un espacio, inclúyalo entre comillas \(""\).|  
  
## Comentarios  
 Especifique el nombre completo y la extensión del archivo que desea crear.  Si no lo hace, el archivo .exe adopta el nombre del archivo de código fuente que contiene el procedimiento `Sub Main` y el archivo .dll adopta el nombre del primer archivo de código fuente.  
  
 Si especifica un nombre de archivo sin una extensión .exe o .dll, el compilador agrega automáticamente la extensión, dependiendo del valor especificado para la opción del compilador `/target`.  
  
||  
|-|  
|Para establecer \/out en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Aplicación**.<br />3.  Modifique el valor en el cuadro **Nombre del ensamblado**.|  
  
## Ejemplo  
 La siguiente línea compila `T2.vb` y crea un archivo de salida `T2.exe`.  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)