---
title: "/sdkpath | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "sdkpath"
  - "/sdkpath"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/sdkpath (opción del compilador) [Visual Basic]"
  - "sdkpath (opción del compilador) [Visual Basic]"
  - "-sdkpath (opción del compilador) [Visual Basic]"
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /sdkpath
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica la ubicación de Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
## Sintaxis  
  
```  
/sdkpath:path  
```  
  
## Argumentos  
 `path`  
 Directorio que contiene las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll que se utilizarán para la compilación.  Esta ruta de acceso no se comprueba hasta cargarse.  Escriba el nombre de directorio entre comillas \(" "\) si contiene espacios.  
  
## Comentarios  
 Esta opción indica al compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] que cargue los archivos Mscorlib.dll y Microsoft.VisualBasic.dll desde una ubicación no predeterminada.  La opción `/sdkpath`  se ha diseñado para ser utilizada con [\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).  [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] usa versiones diferentes de estas bibliotecas de compatibilidad para evitar el uso de tipos y características del lenguaje que no se encuentran en los dispositivos.  
  
> [!NOTE]
>  La opción `/sdkpath` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  La opción `/sdkpath` se establece cuando se carga un proyecto de dispositivo de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Puede especificar que el compilador debe compilar sin ninguna referencia a la Biblioteca en tiempo de ejecución de Visual Basic mediante la opción del compilador `/vbruntime`.  Para obtener más información, vea [\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## Ejemplo  
 En el código siguiente se compila `Myfile.vb` con [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)], usando las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll que se encuentran en el directorio de instalación predeterminado de [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] en la unidad C.  Normalmente, se usa la versión más reciente de [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)   
 [\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)