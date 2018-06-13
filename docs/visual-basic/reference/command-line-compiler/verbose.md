---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5f257fce67d8e348b69404411c12ded785cfd68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652134"
---
# <a name="-verbose"></a>-verbose
Hace que el compilador generar mensajes de estado y de error detallados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. Especificar `-verbose` es lo mismo que especificar `-verbose+`, lo que hace que el compilador emita mensajes detallados. El valor predeterminado para esta opción es `-verbose-`.  
  
## <a name="remarks"></a>Comentarios  
 El `-verbose` opción muestra información sobre el número total de errores emitidos por el compilador, notifica qué ensamblados se cargan mediante un módulo y muestra qué archivos se están compilando actualmente.  
  
> [!NOTE]
>  El `-verbose` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y hace que el compilador para mostrar información de estado detallada.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
