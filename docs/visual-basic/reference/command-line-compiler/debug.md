---
title: -debug
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: df65d1c095f5a22d562d78e15baf750a20ec2556
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716774"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)

Hace que el compilador genere información de depuración y la coloque en los archivos de salida.

## <a name="syntax"></a>Sintaxis

```console
-debug[+ | -]
```

o

```console
-debug:[full | pdbonly]
```

## <a name="arguments"></a>Argumentos

|Término|de esquema JSON|
|---|---|
|`+` &#124; `-`|Opcional. Al especificar `+` o `-debug`, el compilador genera información de depuración y la coloca en un archivo. pdb. Especificar `-` tiene el mismo efecto que no especificar `-debug`.|
|`full` &#124; `pdbonly`|Opcional. Especifica el tipo de información de depuración generado por el compilador. Si no especifica `-debug:pdbonly`, el valor predeterminado es `full`, lo que le permite asociar un depurador al programa en ejecución. El argumento `pdbonly` permite la depuración del código fuente cuando el programa se inicia en el depurador, pero solo muestra código de lenguaje de ensamblado cuando el programa en ejecución está asociado al depurador.|

## <a name="remarks"></a>Notas

Use esta opción para crear versiones de depuración. Si no especifica `-debug`, `-debug+`o `-debug:full`, no podrá depurar el archivo de salida del programa.

De forma predeterminada, no se emite información de depuración (`-debug-`). Para emitir información de depuración, especifique `-debug` o `-debug+`.

Para obtener información sobre cómo configurar el rendimiento de depuración de una aplicación, consulte [Facilitar la depuración de una imagen](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).

|Para Set-debug en el entorno de desarrollo integrado de Visual Studio|
|---|
|1. con un proyecto seleccionado en **Explorador de soluciones**, en el menú **proyecto** , haga clic en **propiedades**. <br />2. Haga clic en la pestaña **compilar** .<br />3. Haga clic en **Opciones de compilación avanzadas**.<br />4. modifique el valor en el cuadro **generar información de depuración** .|

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se coloca información de depuración en el archivo de salida `App.exe`.

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
