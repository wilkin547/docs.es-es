---
title: "@ (Especificar archivo de respuesta, Visual Basic) | Microsoft Docs"
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
  - "@ (Especificar archivo de respuesta) (opción del compilador) [Visual Basic]"
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# @ (Especificar archivo de respuesta, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica un archivo que contiene opciones del compilador y archivos de código fuente para compilar.  
  
## Sintaxis  
  
```  
@response_file  
```  
  
## Argumentos  
 `response_file`  
 Obligatorio.  Archivo que especifica opciones del compilador o archivos de código fuente para compilar.  Escriba el nombre de archivo entre comillas \(" "\) si contiene espacios.  
  
## Comentarios  
 El compilador procesa las opciones de compilador y los archivos de código fuente especificados en un archivo de respuesta como si se hubieran especificado en la línea de comandos.  
  
 Para especificar varios archivos de respuesta en una compilación, hay que especificar varias opciones de archivo de respuesta, como las siguientes.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 En una misma línea de un archivo de respuesta, pueden aparecer varias opciones del compilador y archivos de código fuente.  Una especificación de opción del compilador debe aparecer en una única línea \(no puede abarcar varias líneas\).  Los archivos de respuesta pueden contener comentarios que empiezan con el símbolo `#`.  
  
 Se pueden combinar opciones especificadas en la línea de comandos con opciones especificadas en varios archivos de respuesta.  El compilador procesa las opciones de comandos cuando las encuentra.  Por consiguiente, los argumentos de la línea de comandos pueden imponerse a opciones utilizadas anteriormente en archivos de respuesta.  Y, a la inversa, las opciones de un archivo de respuesta pueden imponerse a opciones incluidas previamente en la línea de comandos o en otros archivos de respuesta.  
  
 Visual Basic proporciona el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe.  El archivo Vbc.rsp se incluye de forma predeterminada, a menos que se utilice la opción `/noconfig`.  Para obtener más información, vea [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).  
  
> [!NOTE]
>  La opción `@` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 Las líneas siguientes proceden de un archivo de respuesta de ejemplo.  
  
```  
# build the first output file  
/target:exe   
/out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo se utiliza la opción `@` con el archivo de respuesta denominado `File1.rsp`.  
  
```  
vbc @file1.rsp  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)