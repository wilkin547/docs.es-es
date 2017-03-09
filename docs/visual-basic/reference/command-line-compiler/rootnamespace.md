---
title: "/rootnamespace | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/rootnamespace"
  - "rootnamespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/rootnamespace (opción del compilador) [Visual Basic]"
  - "rootnamespace (opción del compilador) [Visual Basic]"
  - "-rootnamespace (opción del compilador) [Visual Basic]"
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# /rootnamespace
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica un espacio de nombres para todas las declaraciones de tipos.  
  
## Sintaxis  
  
```  
/rootnamespace:namespace  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`namespace`|Nombre del espacio de nombres en el que se desean englobar todas las declaraciones de tipos para este proyecto.|  
  
## Comentarios  
 Si utiliza el archivo ejecutable de Visual Studio \(Devenv.exe\) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, utilice `/rootnamespace` para especificar el valor de la propiedad <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>.  Para obtener más información, consulte [Modificadores de línea de comandos para Devenv](/visual-studio/ide/reference/devenv-command-line-switches).  
  
 Utilice el desensamblador MSIL de Common Language Runtime \(I`ldasm.exe`\) para ver los nombres de espacios de nombres del archivo de salida.  
  
||  
|-|  
|Para establecer \/rootnamespace en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Aplicación**.<br />3.  Modifique el valor en el cuadro **Espacio de nombres de la raíz**.|  
  
## Ejemplo  
 La siguiente línea compila `In.vb` y engloba todas las declaraciones de tipos en el espacio de nombres `mynamespace`:  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ildasm.exe \(IL Disassembler\)](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)