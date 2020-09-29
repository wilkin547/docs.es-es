---
description: '@ (Opciones del compilador de C#)'
title: '@ (Opciones del compilador de C#)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: 8f7e222e194fc4ba96159ecd792765f64b4d1c57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193762"
---
# <a name="-c-compiler-options"></a>@ (Opciones del compilador de C#)

La opción @ le permite especificar un archivo que contiene opciones del compilador y archivos de código fuente para compilar.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a>Argumentos  

 `response_file`  
 Un archivo que enumera las opciones del compilador o los archivos de código fuente que se compilarán.  
  
## <a name="remarks"></a>Observaciones  

 El compilador procesará las opciones del compilador y los archivos de código fuente como si se hubieran especificado en la línea de comandos.  
  
 Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta. Por ejemplo:  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 En un archivo de respuesta, puede haber varias opciones del compilador y archivos de código fuente en una sola línea. Una sola especificación de opción del compilador debe aparecer en una línea (no puede abarcar varias líneas). Los archivos de respuesta pueden tener comentarios que comiencen con el símbolo #.  
  
 Especificar opciones del compilador desde un archivo de respuesta es igual que enviar esos comandos en la línea de comandos. Vea [Compilar desde la línea de comandos](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) para obtener más información.  
  
 El compilador procesa las opciones de comando a medida que se encuentran. Por tanto, los argumentos de línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta. Por el contrario, las opciones en un archivo de respuesta reemplazarán las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.  
  
 C# proporciona el archivo csc.rsp, que se encuentra en el mismo directorio que el archivo csc.exe. Vea [-noconfig](./noconfig-compiler-option.md) para saber más sobre csc.rsp.  
  
 No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.  
  
## <a name="example"></a>Ejemplo  

 Estas son algunas líneas de un archivo de respuesta de ejemplo:  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
