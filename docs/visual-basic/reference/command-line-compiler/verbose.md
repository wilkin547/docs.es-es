---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: e70496b552ced8e07cbe3cde34cda377d94da9f4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188422"
---
# <a name="-verbose"></a>-verbose
Hace que el compilador genere mensajes de estado y de error detallados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. Especificar `-verbose` es lo mismo que especificar `-verbose+`, lo que hace que el compilador emita mensajes detallados. El valor predeterminado para esta opción es `-verbose-`.  
  
## <a name="remarks"></a>Comentarios  
 El `-verbose` opción muestra información sobre el número total de errores emitidos por el compilador, notifica qué ensamblados se cargan mediante un módulo y muestra qué archivos se está compilando actualmente.  
  
> [!NOTE]
>  El `-verbose` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y hace que el compilador para mostrar información de estado detallada.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
