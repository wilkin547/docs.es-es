---
title: "/libpath | Microsoft Docs"
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
  - "/libpath (opción del compilador) [Visual Basic]"
  - "libpath (opción del compilador) [Visual Basic]"
  - "-libpath (opción del compilador) [Visual Basic]"
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /libpath
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica la ubicación de ensamblados a los que se hace referencia.  
  
## Sintaxis  
  
```  
/libpath:dirList  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`dirList`|Obligatorio.  Lista de directorios delimitados por punto y coma para que el compilador busque en caso de que no se encuentre un ensamblado al que se hace referencia en el directorio de trabajo actual \(el directorio desde el que se invoca el compilador\) o en el directorio del sistema de Common Language Runtime.  Si el nombre de directorio contiene un espacio, incluya el nombre entre comillas \(" "\).|  
  
## Comentarios  
 La opción `/libpath` especifica la ubicación de ensamblados a los que se hace referencia mediante la opción [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md).  
  
 El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:  
  
1.  Directorio actual de trabajo.  Es el directorio desde donde se invoca al compilador.  
  
2.  Directorio del sistema de Common Language Runtime.  
  
3.  Directorios especificados por `/libpath`.  
  
4.  Directorios especificados por la variable de entorno LIB.  
  
 La opción  `/libpath` es aditiva; si se especifica más de una vez, se agregan nuevos valores a los ya existentes.  
  
 Utilice `/reference` para especificar una referencia a un ensamblado.  
  
||  
|-|  
|Para establecer \/libpath en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Referencias**.<br />3.  Haga clic en el botón **Rutas de acceso de referencia**.<br />4.  En el cuadro de diálogo **Rutas de acceso de referencia**, escriba el nombre de directorio en el cuadro **Carpeta:**.<br />5.  Haga clic en **Agregar carpeta**.|  
  
## Ejemplo  
 El código siguiente compila `T2.vb` para crear un archivo .exe.  El compilador busca referencias a ensamblados en el directorio de trabajo, en el directorio raíz de la unidad C: y en el directorio New Assemblies de la unidad C:.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## Vea también  
 [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)