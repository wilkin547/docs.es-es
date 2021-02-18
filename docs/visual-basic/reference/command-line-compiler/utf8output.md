---
description: Más información sobre -utf8output (Visual Basic)
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 317c1be3f18150ae88bb8e95927d9f5faf0e4f3c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461897"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)

Muestra los resultados del compilador en codificación UTF-8.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  

 `+` &#124; `-`  
 Opcional. El valor predeterminado para esta opción es `-utf8output-`, lo que significa que la salida del compilador no usa la codificación UTF-8. Especificar `-utf8output` es lo mismo que especificar `-utf8output+`.  
  
## <a name="remarks"></a>Comentarios  

 En algunas configuraciones internacionales, el resultado del compilador no puede mostrarse correctamente en la consola. En tales situaciones, use `-utf8output` y redirija la salida del compilador a un archivo.  
  
> [!NOTE]
> La opción `-utf8output` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  

 En el código siguiente se compila `In.vb` y se indica al compilador que muestre el resultado con la codificación UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
