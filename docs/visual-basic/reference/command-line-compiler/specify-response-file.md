---
title: '@ (especificar archivo de respuesta)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: c578495bbba0efee79f02da284c7feffb8c12fab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348549"
---
# <a name="-specify-response-file-visual-basic"></a>@ (Especificar archivo de respuesta, Visual Basic)

Especifica un archivo que contiene opciones del compilador y archivos de código fuente para compilar.

## <a name="syntax"></a>Sintaxis

```console
@response_file
```

## <a name="arguments"></a>Argumentos

`response_file`  
Obligatorio. Archivo que enumera las opciones del compilador o los archivos de código fuente que se compilarán. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").

## <a name="remarks"></a>Comentarios

El compilador procesa las opciones del compilador y los archivos de código fuente especificados en un archivo de respuesta como si se hubieran especificado en la línea de comandos.

Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta, como aquí.

```console
@file1.rsp @file2.rsp
```

En un archivo de respuesta, puede haber varias opciones del compilador y archivos de código fuente en una sola línea. Una sola especificación de opción del compilador debe aparecer en una línea (no puede abarcar varias líneas). Los archivos de respuesta pueden tener comentarios que comiencen por el símbolo `#`.

Las opciones especificadas en la línea de comandos se pueden combinar con las opciones especificadas en uno o varios archivos de respuesta. El compilador procesa las opciones de comando a medida que las va encontrando. Por tanto, los argumentos de línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta. Por el contrario, las opciones en un archivo de respuesta reemplazan las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta.

Visual Basic proporciona el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe. El archivo Vbc.rsp se incluye de forma predeterminada, a menos que se use la opción `-noconfig`. Para más información, vea [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).

> [!NOTE]
> La opción `@` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.

## <a name="example"></a>Ejemplo

Las siguientes líneas pertenecen a un archivo de respuesta de ejemplo.

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestra cómo usar la opción `@` junto con el archivo de respuesta `File1.rsp`.

```console
vbc @file1.rsp
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
