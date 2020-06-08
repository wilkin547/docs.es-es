---
title: -debug
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 60c6e512a648f093bb9c70b5af86d5719e544adc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408730"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)

Da lugar a que el compilador genere información de depuración y la incluya en el archivo o los archivos de salida.

## <a name="syntax"></a>Sintaxis

```console
-debug[+ | -]
```

o

```console
-debug:[full | pdbonly]
```

## <a name="arguments"></a>Argumentos

|Término|Definición|
|---|---|
|`+` &#124; `-`|Opcional. Si se especifica la opción `+` o `-debug`, el compilador generará información de depuración y la almacenará en un archivo .pdb. Especificar `-` tiene el mismo efecto que no especificar `-debug`.|
|`full` &#124; `pdbonly`|Opcional. Especifica el tipo de información de depuración generado por el compilador. Si no especifica `-debug:pdbonly`, el valor predeterminado es `full`, lo cual permite asociar un depurador al programa en ejecución. El argumento `pdbonly` permite la depuración de código fuente cuando el programa se inicia en el depurador, pero muestra código de lenguaje ensamblador solo cuando el programa en ejecución está asociado al depurador.|

## <a name="remarks"></a>Comentarios

Use esta opción para crear versiones de depuración. Si no especifica `-debug`, `-debug+` o `-debug:full`, no podrá depurar el archivo de salida del programa.

De forma predeterminada, no se emite información de depuración (`-debug-`). Para emitir información de depuración, especifique `-debug` o `-debug+`.

Para obtener información sobre cómo configurar el rendimiento de depuración de una aplicación, consulte [Facilitar la depuración de una imagen](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).

|Para establecer -debug en el entorno de desarrollo integrado de Visual Studio|
|---|
|1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Opciones de compilación avanzadas**.<br />4.  Modifique el valor en el cuadro **Generar información de depuración**.|

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se coloca información de depuración en el archivo de salida `App.exe`.

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-bugreport](bugreport.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
