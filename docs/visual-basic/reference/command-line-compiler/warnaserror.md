---
title: /warnaserror (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 28f232b1ad8200455550f2f4c1204818c8b143ab
ms.lasthandoff: 03/13/2017

---
# <a name="warnaserror-visual-basic"></a>/warnaserror (Visual Basic)
Hace que el compilador trate la primera aparición de una advertencia como un error.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|+ &#124; -|Opcional. De forma predeterminada, `/warnaserror-` está en vigor; advertencias no impiden que el compilador genera un archivo de salida. El `/warnaserror` opción, que es el mismo como `/warnaserror+`, hace que las advertencias se traten como errores.|  
|`numberList`|Opcional. Lista delimitada por comas del identificador de advertencia de números para que los `/warnaserror` opción se aplica. Si no se especifica ningún identificador de advertencia, el `/warnaserror` opción se aplica a todas las advertencias.|  
  
## <a name="remarks"></a>Comentarios  
 El `/warnaserror` opción trata todas las advertencias como errores. Los mensajes que normalmente se mostrarían como advertencias se muestran como errores. El compilador notifica las apariciones posteriores de la misma advertencia como advertencias.  
  
 De forma predeterminada, `/warnaserror-` está en efecto, que hace que las advertencias sean sólo informativas. El `/warnaserror` opción, que es el mismo como `/warnaserror+`, hace que las advertencias se traten como errores.  
  
 Si desea que sólo se traten como errores algunas advertencias concretas, puede especificar una lista separada por comas de números de advertencia que se va a tratar como errores.  
  
> [!NOTE]
>  El `/warnaserror` opción controla cómo se muestran las advertencias. Utilice la [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) opción para deshabilitar las advertencias.  
  
|Para establecer /warnaserror trate todas las advertencias como errores en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **compilar** ficha.<br />3.  Asegúrese de que el **deshabilitar todas las advertencias** casilla de verificación está desactivada.<br />4.  Compruebe el **tratar todas las advertencias como errores** casilla de verificación.|  
  
|Para establecer /warnaserror a tratar advertencias concretas como errores en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**.<br />2.  Haga clic en el **compilar** ficha.<br />3.  Asegúrese de que el **deshabilitar todas las advertencias** casilla de verificación está desactivada.<br />4.  Asegúrese de que el **tratar todas las advertencias como errores** casilla de verificación está desactivada.<br />5.  Seleccione **Error** desde el **notificación** columna adyacente a la advertencia que se debe tratar como un error.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y hace que el compilador muestre un error de la primera aparición de cada advertencia.  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y trata sólo la advertencia para las variables locales no utilizadas (42024) como un error.  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)
