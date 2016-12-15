---
title: "/optimize | Microsoft Docs"
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
  - "/optimize (opción del compilador) [Visual Basic]"
  - "optimización, habilitar"
  - "optimize (opción del compilador) [Visual Basic]"
  - "-optimize (opción del compilador) [Visual Basic]"
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /optimize
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Habilita o deshabilita las optimizaciones del compilador.  
  
## Sintaxis  
  
```  
/optimize[ + | - ]  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`+`  &#124; `-`|Opcional.  La opción `/optimize-` deshabilita las optimizaciones del compilador.  La opción `/optimize+` habilita las optimizaciones.  De forma predeterminada, las optimizaciones están deshabilitadas.|  
  
## Comentarios  
 Las optimizaciones del compilador hacen que el archivo de salida sea más pequeño, rápido y eficaz.  Sin embargo, como las optimizaciones producen la reorganización del código en el archivo de salida, `/optimize+` puede dificultar la depuración.  
  
 Todos los módulos generados con `/target:module` para un ensamblado deben utilizar la misma configuración de `/optimize` que el ensamblado.  Para obtener más información, vea [\/target](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Puede combinar las opciones `/optimize` y `/debug`.  
  
||  
|-|  
|Para establecer \/optimize en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.<br />     Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Compilar**.<br />3.  Haga clic en el botón **Avanzadas**.<br />4.  Modifique la casilla **Habilitar optimizaciones**.|  
  
## Ejemplo  
 La siguiente línea compila `T2.vb` y habilita las optimizaciones del compilador.  
  
```  
vbc t2.vb /optimize  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)