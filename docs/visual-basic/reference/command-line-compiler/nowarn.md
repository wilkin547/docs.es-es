---
title: "/nowarn | Microsoft Docs"
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
  - "/nowarn (opción del compilador) [Visual Basic]"
  - "nowarn (opción del compilador) [Visual Basic]"
  - "-nowarn (opción del compilador) [Visual Basic]"
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /nowarn
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Suprime la capacidad del compilador de generar advertencias.  
  
## Sintaxis  
  
```  
/nowarn[:numberList]  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`numberList`|Opcional.  Lista delimitada por comas de los números del identificador de advertencia que el compilador debería suprimir.  Si no se especifican identificadores de advertencia, se eliminan todas las advertencias.|  
  
## Comentarios  
 La opción `/nowarn` hace que el compilador no genere advertencias.  Para suprimir una determinada advertencia, incluya el identificador de advertencia en la opción `/nowarn` después de los dos puntos.  Si hay varios números de advertencia, hay que separarlos mediante comas.  
  
 Sólo hay que especificar la parte numérica del identificador de advertencia.  Por ejemplo, si desea suprimir BC42024, la advertencia de las variables locales no utilizadas, especifique `/nowarn:42024`.  
  
 Para obtener más información sobre los números de identificación de advertencias, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
||  
|-|  
|Para establecer \/nowarn en el entorno integrado de desarrollo \(IDE\) de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Compilar**.<br />3.  Active la casilla **Deshabilitar todas las advertencias** para deshabilitar todas las advertencias.<br />     \-O bien\-<br />     Para deshabilitar una advertencia determinada, haga clic en **Ninguna** en la lista desplegable situada junto a la advertencia.|  
  
## Ejemplo  
 La siguiente línea compila `T2.vb` sin mostrar advertencias.  
  
```  
vbc /nowarn t2.vb  
```  
  
## Ejemplo  
 El código siguiente compila `T2.vb` sin mostrar advertencias para las variables locales no utilizadas \(42024\).  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic)