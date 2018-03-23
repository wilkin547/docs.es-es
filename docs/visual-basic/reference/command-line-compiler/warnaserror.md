---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ae8ed68045529e626f2788f854d8e6a6933e7e2
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
Hace que el compilador trate la primera aparición de una advertencia como un error.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|---|---|  
|+ &#124; -|Opcional. De forma predeterminada, `-warnaserror-` está en vigor; las advertencias no impiden que el compilador produce un archivo de salida. El `-warnaserror` opción, que es el mismo como `-warnaserror+`, hace que las advertencias se traten como errores.|  
|`numberList`|Opcional. Lista delimitada por comas de Id. de la advertencia números a la que el `-warnaserror` opción se aplica. Si se especifica ningún identificador de advertencia, el `-warnaserror` opción se aplica a todas las advertencias.|  
  
## <a name="remarks"></a>Comentarios  
 El `-warnaserror` opción trata todas las advertencias como errores. Los mensajes que normalmente se mostrarían como advertencias en su lugar se notifican como errores. El compilador informa de las siguientes apariciones de la misma advertencia como advertencias.  
  
 De forma predeterminada, `-warnaserror-` está en vigor, lo que hace que las advertencias es sólo informativo. El `-warnaserror` opción, que es el mismo como `-warnaserror+`, hace que las advertencias se traten como errores.  
  
 Si desea que sólo se traten como errores algunas advertencias concretas, puede especificar una lista separada por comas de números de advertencia que se tratarán como errores.  
  
> [!NOTE]
>  El `-warnaserror` opción no controla cómo se muestran las advertencias. Use la [- nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) opción para deshabilitar las advertencias.  
  
|Para establecer - warnaserror para tratar todas las advertencias como errores en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Asegúrese de que el **deshabilitar todas las advertencias** casilla de verificación está desactivada.<br />4.  Compruebe el **tratar todas las advertencias como errores** casilla de verificación.|  
  
|Para establecer - warnaserror para tratar advertencias específicas como errores en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.<br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Asegúrese de que el **deshabilitar todas las advertencias** casilla de verificación está desactivada.<br />4.  Asegúrese de que el **tratar todas las advertencias como errores** casilla de verificación está desactivada.<br />5.  Seleccione **Error** desde el **notificación** columna adyacente a la advertencia que se debe tratar como un error.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` e indica al compilador que muestre un error para la primera aparición de cada advertencia.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y trata sólo la advertencia para las variables locales no utilizadas (42024) como un error.  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
