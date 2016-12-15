---
title: "/debug (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "/debug (opción del compilador) [Visual Basic]"
  - "debug (opción del compilador) [Visual Basic]"
  - "-debug (opción del compilador) [Visual Basic]"
  - "modificadores del compilador de depuración"
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /debug (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Hace que el compilador genere información de depuración y la incluya en los archivos resultantes.  
  
## Sintaxis  
  
```  
/debug[+ | -]  
' -or-  
/debug:[full | pdbonly]  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`+`  &#124; `-`|Opcional.  Si se especifica `+` o `/debug`, el compilador genera información de depuración y la incluye en un archivo .pdb.  Especificar `-` tiene el mismo efecto que no especificar `/debug`.|  
|`full`  &#124; `pdbonly`|Opcional.  Especifica el tipo de información de depuración generada por el compilador.  Si no especifica `/debug:pdbonly`, el valor predeterminado es `full`, lo que permite adjuntar un depurador al programa en ejecución.  El argumento `pdbonly` permite depurar el código fuente cuando el programa se inicia en el depurador, pero sólo se mostrará el código en lenguaje de ensamblado cuando el programa que se ejecuta está asociado al depurador.|  
  
## Comentarios  
 Utilice esta opción para crear versiones de depuración.  Si no especifica `/debug`, `/debug+` o `/debug:full`, no se podrá depurar el archivo de salida del programa.  
  
 De forma predeterminada, no se incluye información de depuración \(`/debug-`\).  Para emitir la información de depuración, especifique `/debug` o `/debug+`.  
  
 Para obtener información sobre cómo configurar la depuración de una aplicación, vea [Facilitar la depuración de una imagen](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md).  
  
||  
|-|  
|Para establecer \/debug en el entorno integrado de desarrollo \(IDE\) de Visual Studio|  
|1.  Con un proyecto seleccionado en el **Explorador de soluciones**, en el menú **Proyecto** haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Compilar**.<br />3.  Haga clic en **Opciones de compilación avanzadas**.<br />4.  Modifique el valor en el cuadro **Generar información de depuración**.|  
  
## Ejemplo  
 En el siguiente ejemplo se incluye información de depuración en el archivo de salida `App.exe`:  
  
```  
vbc /debug /out:app.exe test.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)