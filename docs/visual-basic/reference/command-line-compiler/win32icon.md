---
title: "/win32icon | Microsoft Docs"
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
  - "/win32icon (opción del compilador) [Visual Basic]"
  - "win32icon (opción del compilador) [Visual Basic]"
  - "-win32icon (opción del compilador) [Visual Basic]"
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# /win32icon
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Inserta un archivo .ico en el archivo de salida.  Este archivo .ico representa el archivo de salida en **El Explorador de archivos**.  
  
## Sintaxis  
  
```  
/win32icon:filename  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`filename`|El archivo .ico que se desea agregar al archivo de salida.  Escriba el nombre de archivo entre comillas \(" "\) si contiene espacios.|  
  
## Comentarios  
 Puede crear un archivo .ico con el Compilador de recursos de Microsoft Windows \(RC\).  El Compilador de recursos se invoca al compilar un programa de Visual C\+\+; se crea un archivo .ico a partir del archivo .rc.  Las opciones `/win32icon` y `/win32resource` se excluyen mutuamente.  
  
 Vea [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md) si desea hacer referencia a un archivo de recursos de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] o vea[\/resource](../../../visual-basic/reference/command-line-compiler/resource.md) si desea adjuntar un archivo de recursos [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  Vea [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) para importar un archivo .res.  
  
||  
|-|  
|Para establecer \/win32icon en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Aplicación**.<br />3.  Modifique el valor en el cuadro **Icono**.|  
  
## Ejemplo  
 La siguiente línea compila `In.vb` y asocia un archivo .ico rf.ico, `Rf.ico`.  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)