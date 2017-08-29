---
title: '@ (Opciones del compilador de C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 219c12e4e3c9b847400f00a135d58506c72d2e7f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-c-compiler-options"></a>@ (Opciones del compilador de C#)
La opción @ le permite especificar un archivo que contiene opciones del compilador y archivos de código fuente para compilar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>Argumentos  
 `response_file`  
 Un archivo que enumera las opciones del compilador o los archivos de código fuente que se compilarán.  
  
## <a name="remarks"></a>Comentarios  
 El compilador procesará las opciones del compilador y los archivos de código fuente como si se hubieran especificado en la línea de comandos.  
  
 Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta. Por ejemplo:  
  
```  
@file1.rsp @file2.rsp  
```  
  
 En un archivo de respuesta, puede haber varias opciones del compilador y archivos de código fuente en una sola línea. Una sola especificación de opción del compilador debe aparecer en una línea (no puede abarcar varias líneas). Los archivos de respuesta pueden tener comentarios que comiencen con el símbolo #.  
  
 Especificar opciones del compilador desde un archivo de respuesta es igual que enviar esos comandos en la línea de comandos. Vea [Compilar desde la línea de comandos](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) para obtener más información.  
  
 El compilador procesa las opciones de comando a medida que se encuentran. Por tanto, los argumentos de línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta. Por el contrario, las opciones en un archivo de respuesta reemplazarán las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.  
  
 C# proporciona el archivo csc.rsp, que se encuentra en el mismo directorio que el archivo csc.exe. Vea [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) para obtener más información sobre csc.rsp.  
  
 No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.  
  
## <a name="example"></a>Ejemplo  
 Estas son algunas líneas de un archivo de respuesta de ejemplo:  
  
```console  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)

