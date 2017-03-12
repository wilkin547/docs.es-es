---
title: "/warnaserror (Visual Basic) | Microsoft Docs"
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
  - "/warnaserror (opción del compilador) [Visual Basic]"
  - "warnaserror (opción del compilador) [Visual Basic]"
  - "-warnaserror (opción del compilador) [Visual Basic]"
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /warnaserror (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Hace que el compilador trate la primera instancia de una advertencia como un error.  
  
## Sintaxis  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|\+ &#124; \-|Opcional.  De manera predeterminada está activada la opción `/warnaserror-`, para que las advertencias no impidan que el compilador genere un archivo de salida.  La opción `/warnaserror` , que es equivalente a `/warnaserror+`, hace que las advertencias se traten como errores.|  
|`numberList`|Opcional.  Lista delimitada por comas de los números de Id. de advertencia a los que se aplica la opción `/warnaserror`.  Si no se especifica ningún Id. de la advertencia, la opción `/warnaserror` se aplica a todas las advertencias.|  
  
## Comentarios  
 La opción `/warnaserror` trata todas las advertencias como errores.  Los mensajes que normalmente se considerarían como advertencias se consideran como errores.  El compilador informa sobre la repetición posterior de la misma advertencia como advertencias.  
  
 De manera predeterminada, `/warnaserror-` está activado, lo que hace que las advertencias sean sólo informativas.  La opción `/warnaserror` , que es equivalente a `/warnaserror+`, hace que las advertencias se traten como errores.  
  
 Si desea que sólo se traten como errores algunas advertencias concretas, puede especificar sus números en una lista separada por comas.  
  
> [!NOTE]
>  La opción `/warnaserror` no controla cómo se muestran advertencias.  Utilice la opción [\/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) para deshabilitar las advertencias.  
  
||  
|-|  
|Para establecer \/warnaserror a fin de que trate todas las advertencias como errores en el IDE de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Compilar**.<br />3.  Asegúrese de que la casilla **Deshabilitar todas las advertencias** esté deshabilitada.<br />4.  Active la casilla **Considerar todas las advertencias como errores**.|  
  
||  
|-|  
|Para establecer \/warnaserror a fin de que trate determinadas advertencias como errores en el IDE de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.<br />2.  Haga clic en la ficha **Compilar**.<br />3.  Asegúrese de que la casilla **Deshabilitar todas las advertencias** esté deshabilitada.<br />4.  Asegúrese de que la casilla **Considerar todas las advertencias como errores** esté deshabilitada.<br />5.  Seleccione **Error** en la columna **Notificación** adyacente a la advertencia que se debería tratar como un error.|  
  
## Ejemplo  
 El código siguiente compila `In.vb` y hace que el compilador muestre un error cuando se produzca la primera aparición de cada advertencia.  
  
```  
vbc /warnaserror in.vb  
```  
  
## Ejemplo  
 El código siguiente compila `T2.vb` y trata sólo la advertencia para las variables locales no utilizadas \(42024\) como un error.  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic)