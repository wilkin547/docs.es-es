---
description: Mas información sobre -netcf
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
ms.openlocfilehash: 053e177d8d7008b10bfa552ee60cbbd2d5dda565
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434919"
---
# <a name="-netcf"></a>-netcf

Establece que el compilador tenga como destino el entorno .NET Compact Framework.

## <a name="syntax"></a>Sintaxis

```console
-netcf
```

## <a name="remarks"></a>Comentarios

La opción `-netcf` hace que el compilador de Visual Basic tenga como destino el entorno .NET Compact Framework en lugar del .NET Framework completo. Se deshabilita la funcionalidad de lenguaje que solo está presente en el componente .NET Framework completo.

La opción `-netcf` está diseñada para usarse con [-sdkpath](sdkpath.md). Las características de lenguaje deshabilitadas por `-netcf` son las mismas características de lenguaje que no están presentes en los archivos de destino de `-sdkpath`.

> [!NOTE]
> La opción `-netcf` no está disponible en el entorno de desarrollo de Visual Studio; solo lo está cuando se compila desde la línea de comandos. La opción `-netcf` se establece cuando se carga un proyecto de dispositivo de Visual Basic.

La opción `-netcf` cambia las características de lenguaje siguientes:

- La palabra clave [End \<keyword>Statement](../../language-reference/statements/end-keyword-statement.md), que finaliza la ejecución de un programa, queda deshabilitada. El siguiente programa se compila y ejecuta sin `-netcf`, pero produce un error en tiempo de compilación con `-netcf`.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- Se deshabilita el enlace en tiempo de ejecución en todos los formularios. Se generan errores en tiempo de compilación cuando se encuentran escenarios de enlace en tiempo de ejecución reconocidos. El siguiente programa se compila y ejecuta sin `-netcf`, pero produce un error en tiempo de compilación con `-netcf`.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- Se deshabilitan los modificadores [Auto](../../language-reference/modifiers/auto.md), [Ansi](../../language-reference/modifiers/ansi.md) y [Unicode](../../language-reference/modifiers/unicode.md). La sintaxis de la [instrucción Declare](../../language-reference/statements/declare-statement.md) también se modifica en `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. En el código siguiente se muestra el efecto de `-netcf` en una compilación.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- El uso de palabras clave de Visual Basic 6.0 que se quitaron de Visual Basic genera un error diferente cuando se usa `-netcf`. Esto afecta a los mensajes de error de las palabras clave siguientes:

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

El código siguiente compila `Myfile.vb` con .NET Compact Framework, mediante las versiones de mscorlib.dll y Microsoft.VisualBasic.dll que se encuentran en el directorio de instalación predeterminado de .NET Compact Framework en la unidad C. Normalmente, se usaría la versión más reciente de .NET Compact Framework.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [-sdkpath](sdkpath.md)
