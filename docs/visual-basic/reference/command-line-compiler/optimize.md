---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e157fb0e1fcdb3899440eed02a42b16f75541989
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="optimize"></a>/optimize
Habilita o deshabilita las optimizaciones del compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. El `/optimize-` opción deshabilita las optimizaciones del compilador. El `/optimize+` opción habilita las optimizaciones. De forma predeterminada, las optimizaciones están deshabilitadas.|  
  
## <a name="remarks"></a>Comentarios  
 Gracias a las optimizaciones del compilador, el archivo de salida será más pequeño, más rápido y más eficaz. Sin embargo, dado que las optimizaciones causan la reestructuración del código en el archivo de salida, `/optimize+` puede dificultar la depuración.  
  
 Todos los módulos generados con `/target:module` para un ensamblado debe usar la misma `/optimize` configuración que el ensamblado. Para obtener más información, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Puede combinar la `/optimize` y `/debug` opciones.  
  
|Para establecer /optimize en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.<br />     <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en el botón **Avanzada** .<br />4.  Modificar el **habilitar optimizaciones** casilla de verificación.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y habilita las optimizaciones del compilador.  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
