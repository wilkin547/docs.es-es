---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 753c92cdf2124ee7fb1b471c7bc543b6db6f3daa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653590"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Muestra los resultados del compilador en codificación UTF-8.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. El valor predeterminado para esta opción es `-utf8output-`, lo que significa la salida del compilador no utiliza la codificación UTF-8. Especificar `-utf8output` es lo mismo que especificar `-utf8output+`.  
  
## <a name="remarks"></a>Comentarios  
 En algunas configuraciones internacionales, los resultados del compilador no se muestran correctamente en la consola. En tales casos, use `-utf8output` y redirigir los resultados del compilador a un archivo.  
  
> [!NOTE]
>  El `-utf8output` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y hace que el compilador para mostrar los resultados utilizando la codificación UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
