---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 337cb794ef9a405a178f1998cbe27b5da7709382
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397446"
---
# <a name="-optimize"></a>-optimize
Habilita o deshabilita las optimizaciones del compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. La opción `-optimize-` deshabilita las optimizaciones del compilador. La opción `-optimize+` habilita las optimizaciones del compilador. De forma predeterminada, las optimizaciones están deshabilitadas.|  
  
## <a name="remarks"></a>Comentarios  
 Gracias a las optimizaciones del compilador, el archivo de salida será más pequeño, más rápido y más eficaz. Pero como las optimizaciones causan la reestructuración del código en el archivo de salida, `-optimize+` puede dificultar la depuración.  
  
 Todos los módulos generados con `-target:module` para un ensamblado deben usar la misma configuración de `-optimize` que el ensamblado. Para obtener más información, vea [-target (Visual Basic)](target.md).  
  
 Puede combinar las opciones `-optimize` y `-debug`.  
  
|Para establecer -optimize en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.<br />     <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en el botón **Avanzada** .<br />4.  Modifique la casilla **Habilitar optimizaciones**.|  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `T2.vb` y habilita las optimizaciones del compilador.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-debug (Visual Basic)](debug.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [-target (Visual Basic)](target.md)
