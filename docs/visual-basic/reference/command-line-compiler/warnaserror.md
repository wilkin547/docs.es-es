---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 2c243b05b7e819691165ef20996691c0bd38ae4a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098870"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)

Causa que el compilador trate como un error la primera ocurrencia de una advertencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|+ &#124; -|Opcional. De forma predeterminada, se aplica `-warnaserror-`; las advertencias no impiden que el compilador genere un archivo de salida. La opción `-warnaserror`, que es la misma que `-warnaserror+`, causa que las advertencias se traten como errores.|  
|`numberList`|Opcional. Lista delimitada por comas de los números de identificadores de advertencia a los que se aplica la opción `-warnaserror`. Si no se especifica ningún identificador de advertencia, la opción `-warnaserror` se aplica a todas las advertencias.|  
  
## <a name="remarks"></a>Comentarios  

 La opción `-warnaserror` trata todas las advertencias como errores. Todos los mensajes que, por norma general, deberían notificarse como advertencias, en su lugar se registran como errores. El compilador notifica como advertencias las ocurrencias posteriores de la misma advertencia.  
  
 De forma predeterminada, se aplica `-warnaserror-`, que da lugar a que las advertencias tengan solo carácter informativo. La opción `-warnaserror`, que es la misma que `-warnaserror+`, causa que las advertencias se traten como errores.  
  
 Si desea que solo algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencias que se deben tratar como errores.  
  
> [!NOTE]
> La opción `-warnaserror` no controla cómo se muestran las advertencias. Use la opción [-nowarn](nowarn.md) para deshabilitar las advertencias.  
  
|Para establecer -warnaserror a fin de tratar todas las advertencias como errores en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Asegúrese de que la casilla **Deshabilitar todas las advertencias** está desactivada.<br />4.  Active la casilla **Tratar todas las advertencias como errores**.|  
  
|Para establecer - warnaserror a fin de tratar advertencias específicas como errores en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.<br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Asegúrese de que la casilla **Deshabilitar todas las advertencias** está desactivada.<br />4.  Asegúrese de que la casilla **Tratar todas las advertencias como errores** está desactivada.<br />5.  Seleccione **Error** en la columna **Notificación** adyacente a la advertencia que se debe tratar como un error.|  
  
## <a name="example"></a>Ejemplo  

 El siguiente código compila `In.vb` y ordena al compilador que muestre un error para la primera ocurrencia de cada advertencia que encuentra.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Ejemplo  

 El siguiente código compila `T2.vb` y trata como un error solo la advertencia para las variables locales no utilizadas (42024).  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
