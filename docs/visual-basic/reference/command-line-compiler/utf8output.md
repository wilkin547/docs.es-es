---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: adcb518cbe8397549c3ae3b3a8ca9f0ecf9dc38e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004658"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Muestra los resultados del compilador en codificación UTF-8.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. El valor predeterminado para esta opción es `-utf8output-`, lo que significa que la salida del compilador no utiliza la codificación UTF-8. Especificar `-utf8output` es lo mismo que especificar `-utf8output+`.  
  
## <a name="remarks"></a>Comentarios  
 En algunas configuraciones internacionales, los resultados del compilador no se pueden mostrar correctamente en la consola. En tales situaciones, use `-utf8output` y redirija el resultado del compilador a un archivo.  
  
> [!NOTE]
> La opción `-utf8output` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se compila `In.vb` y se indica al compilador que muestre la salida mediante la codificación UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
