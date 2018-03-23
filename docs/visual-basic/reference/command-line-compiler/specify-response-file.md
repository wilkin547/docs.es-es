---
title: '@ (Especificar archivo de respuesta, Visual Basic)'
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af66000208dee0896792892a52dc6acdf5cb1e37
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-specify-response-file-visual-basic"></a>@ (Especificar archivo de respuesta, Visual Basic)
Especifica un archivo que contiene opciones del compilador y archivos de código fuente para compilar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>Argumentos  
 `response_file`  
 Requerido. Un archivo que enumera las opciones del compilador o archivos de código fuente para compilar. Ponga el nombre de archivo entre comillas ("") si contiene un espacio.  
  
## <a name="remarks"></a>Comentarios  
 El compilador procesa las opciones del compilador y archivos de código fuente especificados en un archivo de respuesta como si se hubieran especificado en la línea de comandos.  
  
 Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta, como el siguiente.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 En una respuesta del archivo, varias opciones del compilador y archivos de código fuente pueden aparecer en una sola línea. Una especificación de opción del compilador solo debe aparecer en una línea (no puede abarcar varias líneas). Archivos de respuesta pueden contener comentarios que comienzan por la `#` símbolos.  
  
 Puede combinar opciones especificadas en la línea de comandos con las opciones especificadas en uno o varios archivos de respuesta. El compilador procesa las opciones de comando a medida que los encuentra. Por lo tanto, los argumentos de línea de comandos pueden invalidar las opciones enumeradas anteriormente en archivos de respuesta. Por el contrario, opciones en un archivo de respuesta invalidan las opciones enumeradas en la línea de comandos o en otros archivos de respuesta.  
  
 Visual Basic proporciona el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe. El archivo Vbc.rsp se incluye de forma predeterminada a menos que el `-noconfig` se utiliza la opción. Para obtener más información, consulte [- noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).  
  
> [!NOTE]
>  El `@` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 Las líneas siguientes proceden de un archivo de respuesta de ejemplo.  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `@` opción con el archivo de respuesta denominado `File1.rsp`.  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
