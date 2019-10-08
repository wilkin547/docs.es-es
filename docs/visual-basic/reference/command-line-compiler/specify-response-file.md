---
title: '@ (Especificar archivo de respuesta, Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: deab111cc669941a1cd7dc143dd699b6521221bb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004992"
---
# <a name="-specify-response-file-visual-basic"></a>@ (Especificar archivo de respuesta, Visual Basic)
Especifica un archivo que contiene las opciones del compilador y los archivos de código fuente que se van a compilar.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a>Argumentos  
 `response_file`  
 Obligatorio. Archivo que muestra las opciones del compilador o los archivos de código fuente que se van a compilar. Escriba el nombre de archivo entre comillas ("") si contiene un espacio.  
  
## <a name="remarks"></a>Comentarios  
 El compilador procesa las opciones del compilador y los archivos de código fuente especificados en un archivo de respuesta como si hubieran sido especificados en la línea de comandos.  
  
 Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta, como las siguientes.  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 En un archivo de respuesta, pueden aparecer varias opciones del compilador y archivos de código fuente en una sola línea. Una única especificación de opción de compilador debe aparecer en una línea (no puede abarcar varias líneas). Los archivos de respuesta pueden tener comentarios que comienzan con el símbolo `#`.  
  
 Puede combinar las opciones especificadas en la línea de comandos con las opciones especificadas en uno o varios archivos de respuesta. El compilador procesa las opciones de comando a medida que las encuentra. Por lo tanto, los argumentos de la línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta. Por el contrario, las opciones de un archivo de respuesta invalidan las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.  
  
 Visual Basic proporciona el archivo Vbc. RSP, que se encuentra en el mismo directorio que el archivo Vbc. exe. El archivo Vbc. rsp se incluye de forma predeterminada a menos que se use la opción `-noconfig`. Para obtener más información, vea [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).  
  
> [!NOTE]
> La opción `@` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
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
 En el ejemplo siguiente se muestra cómo usar la opción `@` con el archivo de respuesta denominado `File1.rsp`.  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
