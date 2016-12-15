---
title: "/win32resource | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/win32resource"
  - "win32resource"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/win32resource (opción del compilador) [Visual Basic]"
  - "win32resource (opción del compilador) [Visual Basic]"
  - "-win32resource (opción del compilador) [Visual Basic]"
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /win32resource
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Inserta un archivo de recursos Win32 en el archivo de salida generado.  
  
## Sintaxis  
  
```  
/win32resource:filename  
```  
  
## Argumentos  
 `filename`  
 El nombre del archivo de recursos que se desea agregar al archivo de salida.  Escriba el nombre de archivo entre comillas \(" "\) si contiene espacios.  
  
## Comentarios  
 Puede crear un archivo de recursos de Win32 con el Compilador de recursos de Microsoft Windows \(RC\).  
  
 Un recurso de Win32 puede contener información de la versión o mapas de bits \(icono\) que ayuda identifican la aplicación en **El Explorador de archivos**.  Si no se especifica la opción `/win32resource`, el compilador generará información de versión basada en la versión del ensamblado.  Las opciones `/win32resource` y `/win32icon` se excluyen mutuamente.  
  
 Vea [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md) si desea hacer referencia a un archivo de recursos de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] o vea[\/resource](../../../visual-basic/reference/command-line-compiler/resource.md) si desea adjuntar un archivo de recursos [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
> [!NOTE]
>  La opción `/win32resource` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 La siguiente línea compila `In.vb` y asocia el archivo de recursos de Win32 `Rf.res`:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)