---
title: "/filealign | Microsoft Docs"
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
  - "/filealign (opción del compilador) [Visual Basic]"
  - "alignment (opción del compilador) [Visual Basic]"
  - "filealign (opción del compilador) [Visual Basic]"
  - "-filealign (opción del compilador) [Visual Basic]"
  - "alineación de sección"
  - "sections (opción del compilador) [Visual Basic]"
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# /filealign
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica dónde alinear las secciones del archivo de salida.  
  
## Sintaxis  
  
```  
/filealign:number  
```  
  
## Argumentos  
 `number`  
 Obligatorio.  Valor que especifica la alineación de las secciones del archivo de salida.  Los valores válidos son 512, 1024, 2048, 4096 y 8192.  Estos valores se miden en bytes.  
  
## Comentarios  
 Puede utilizar la opción `/filealign` para especificar la alineación de las secciones en el archivo de salida.  Las secciones son bloques de memoria contigua en un archivo ejecutable portable \(PE\) que contiene código o datos.  La opción `/filealign` permite compilar la aplicación con una alineación no estándar; la mayoría de los desarrolladores no necesitan utilizar esta opción.  
  
 Cada sección se alinea con un límite que es múltiplo del valor  `/filealign`.  No hay un valor predeterminado fijo.  Si no se especifica `/filealign`, el compilador elige un valor predeterminado en tiempo de compilación.  
  
 Si especifica el tamaño de la sección, puede cambiar el tamaño del archivo de salida.  Puede ser útil modificar el tamaño de sección para programas que se ejecuten en dispositivos más pequeños.  
  
> [!NOTE]
>  La opción `/filealign` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)