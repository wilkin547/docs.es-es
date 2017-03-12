---
title: "/addmodule | Microsoft Docs"
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
  - "/addmodule (opción del compilador) [Visual Basic]"
  - "addmodule (opción del compilador) [Visual Basic]"
  - "-addmodule (opción del compilador) [Visual Basic]"
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# /addmodule
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Hace que el compilador facilite la información de tipos presente en los archivos especificados al proyecto que se compila actualmente.  
  
## Sintaxis  
  
```  
/addmodule:fileList  
```  
  
## Argumentos  
 `fileList`  
 Obligatorio.  Lista delimitada por comas de archivos que contienen los metadatos pero no contienen manifiestos del ensamblado.  Los nombres de archivo que contienen espacios debe incluirse entre comillas \(""\).  
  
## Comentarios  
 Los archivos mostrados por el parámetro `fileList` se deben crear con la opción `/target:module` o con el equivalente de otro compilador a `/target:module`.  
  
 Todos los módulos agregados mediante `/addmodule` deben hallarse en el mismo directorio que el archivo de salida en tiempo de ejecución.  Es decir, se puede especificar un módulo de cualquier directorio en el momento de la compilación, pero el módulo debe encontrarse en el directorio de la aplicación en tiempo de ejecución.  Si no estuviera en este directorio, se producirá un error <xref:System.TypeLoadException>.  
  
 Si específica \(de forma implícita o explícita\) alguna opción [\/target](../../../visual-basic/reference/command-line-compiler/target.md) distinta de `/target:module` con `/addmodule`, los archivos que pase a `/addmodule` pasarán a formar parte del ensamblado del proyecto.  Es necesario un ensamblado para ejecutar un archivo de salida con uno o más archivos agregados mediante `/addmodule`.  
  
 Utilice [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contiene un ensamblado.  
  
> [!NOTE]
>  La opción `/addmodule` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 Las siguientes líneas de código crean un módulo.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/addmodule_1.vb)]  
  
 Las siguientes líneas de código importan los tipos del módulo.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/addmodule_2.vb)]  
  
 Cuando se ejecuta `t1`, produce como resultado `802`.  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)