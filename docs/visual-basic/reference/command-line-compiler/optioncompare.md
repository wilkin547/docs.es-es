---
description: Mas información sobre -optioncompare
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: 9be4867c75cc16a8f699cf492dc41e9d08b96495
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475934"
---
# <a name="-optioncompare"></a>-optioncompare

Especifica la forma en que se realizan las comparaciones de cadenas.

## <a name="syntax"></a>Sintaxis

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a>Comentarios

Puede especificar `-optioncompare` de una de las dos formas siguientes: `-optioncompare:binary` para usar comparaciones de cadenas binarias y `-optioncompare:text` para usar comparaciones de cadenas de texto. De forma predeterminada, el compilador utiliza `-optioncompare:binary`.

En Microsoft Windows, la página de códigos actual determina el criterio de ordenación binario. Un criterio de ordenación binario típico es el siguiente:

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

Las comparaciones de cadenas basadas en texto siguen un criterio de ordenación de texto sin distinción de mayúsculas y minúsculas determinado por la configuración regional del sistema. Un criterio de ordenación de texto típico es el siguiente:

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>Para establecer -optioncompare en el IDE de Visual Studio

1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.

2. Haga clic en la pestaña **Compilar**.

3. Modifique el valor del cuadro **Option Compare**.

### <a name="to-set--optioncompare-programmatically"></a>Para establecer -optioncompare mediante programación

Consulte [Option Compare (instrucción)](../../language-reference/statements/option-compare-statement.md)

## <a name="example"></a>Ejemplo

El código siguiente compila `ProjFile.vb` y utiliza comparaciones de cadenas binarias.

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-optionexplicit](optionexplicit.md)
- [-optionstrict](optionstrict.md)
- [-optioninfer](optioninfer.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Option Compare (instrucción)](../../language-reference/statements/option-compare-statement.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
