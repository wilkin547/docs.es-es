---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 028fa148d0e5622648a5fdfff1789c3d0bfde057
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268284"
---
# <a name="-netcf"></a>-netcf

Establece el compilador para .NET Compact Framework de destino.

## <a name="syntax"></a>Sintaxis

```
-netcf
```

## <a name="remarks"></a>Comentarios

El `-netcf` opción hace que el compilador de Visual Basic para .NET Compact Framework en lugar de la versión completa de .NET Framework de destino. Funcionalidad del lenguaje que solo está presente en la versión completa de .NET Framework está deshabilitada.

El `-netcf` opción está diseñada para usarse con [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Las características del lenguaje deshabilitadas de forma `-netcf` son las mismas características de lenguaje no está presentes en los archivos de destino con `-sdkpath`.

> [!NOTE]
> El `-netcf` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos. El `-netcf` opción se establece cuando se carga un proyecto de dispositivo de Visual Basic.

El `-netcf` opción cambia las características de lenguaje siguientes:

- El [final \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) palabra clave, que finaliza la ejecución de un programa, está deshabilitado. El programa siguiente compila y se ejecuta sin `-netcf` pero se produce un error en tiempo de compilación con `-netcf`.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- Enlace en tiempo de ejecución, en todos los formularios, está deshabilitado. Se generan errores en tiempo de compilación cuando se producen los escenarios de enlace reconocidos. El programa siguiente compila y se ejecuta sin `-netcf` pero se produce un error en tiempo de compilación con `-netcf`.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- El [automática](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), y [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificadores están deshabilitados. La sintaxis de la [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) también se modifica la instrucción en `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. El código siguiente muestra el efecto de `-netcf` en una compilación.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- Con las palabras clave de Visual Basic 6.0 que se quitaron de Visual Basic genera un error diferente cuando `-netcf` se utiliza. Esto afecta a los mensajes de error para las siguientes palabras clave:

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>Ejemplo

El siguiente código compila `Myfile.vb` con .NET Compact Framework, utilizando las versiones de mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminado de .NET Compact Framework en la unidad C:. Normalmente, se usa la versión más reciente de .NET Compact Framework.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
