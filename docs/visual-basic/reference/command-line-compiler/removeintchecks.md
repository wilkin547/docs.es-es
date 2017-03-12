---
title: "/removeintchecks | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "removeintchecks"
  - "/removeintchecks"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/removeintchecks (opción del compilador) [Visual Basic]"
  - "removeintchecks (opción del compilador) [Visual Basic]"
  - "-removeintchecks (opción del compilador) [Visual Basic]"
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# /removeintchecks
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Activa o desactiva la comprobación de errores de desbordamiento para operaciones con enteros.  
  
## Sintaxis  
  
```  
/removeintchecks[+ | -]  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`+`  &#124; `-`|Opcional.  La opción de `/removeintchecks-` hace que el compilador para comprobar todos los cálculos enteros para los errores de desbordamiento.  El valor predeterminado es `/removeintchecks-`.<br /><br /> Si se especifican `/removeintchecks` o `/removeintchecks+`, se desactiva la comprobación de errores, lo cual acelera las operaciones de cálculo con enteros.  No obstante, sin la comprobación de errores, se pueden almacenar resultados incorrectos si se sobrepasan las capacidades de los tipos de datos.|  
  
||  
|-|  
|Para establecer \/removeintchecks en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Compilar**.<br />3.  Haga clic en el botón **Avanzadas**.<br />4.  Modifique el valor del cuadro **Quitar comprobaciones de desbordamiento con enteros**.|  
  
## Ejemplo  
 La línea siguiente compila `Test.vb` y desactiva la comprobación de errores de desbordamiento de enteros.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)