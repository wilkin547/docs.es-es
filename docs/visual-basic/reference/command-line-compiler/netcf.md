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
ms.openlocfilehash: d7c3bcba8e62d62904ed778a48d0e8ae6738ce00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794008"
---
# <a name="-netcf"></a>-netcf

Establece el compilador con destino en [!INCLUDE[Compact](~/includes/compact-md.md)].

## <a name="syntax"></a>Sintaxis

```
-netcf
```

## <a name="remarks"></a>Comentarios

El `-netcf` opción hace que el compilador de Visual Basic al destino la [!INCLUDE[Compact](~/includes/compact-md.md)] en lugar de completo [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Funcionalidad del lenguaje que solo está presente en el completo [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] está deshabilitado.

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

El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](~/includes/compact-md.md)], utilizando las versiones de mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminada de la [!INCLUDE[Compact](~/includes/compact-md.md)] en la unidad C:. Normalmente, se usa la versión más reciente de la [!INCLUDE[Compact](~/includes/compact-md.md)].

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
