---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: 469e22aef9d746fc55e04ba884d17d60d8baa85a
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583072"
---
# <a name="-optionstrict"></a>-optionstrict

Aplica la semántica estricta de tipos para restringir las conversiones de tipos implícitas.

## <a name="syntax"></a>Sintaxis

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a>Argumentos

`+` &#124; `-`  
Opcional. La opción `-optionstrict+` restringe la conversión implícita de tipos. El valor predeterminado para esta opción es `-optionstrict-`. La opción `-optionstrict+` es la misma que la `-optionstrict`. Puede usar ambos para la semántica de tipos permisiva.

`custom`  
Requerido. Advertir cuando no se respete la semántica estricta del lenguaje.

## <a name="remarks"></a>Comentarios

Cuando `-optionstrict+` está en vigor, solo se pueden realizar implícitamente conversiones de tipos de ampliación. Las conversiones de tipos de restricción implícitas, como la asignación de un objeto de tipo `Decimal` a un objeto de tipo entero, se muestran como errores.

Para generar advertencias para las conversiones de tipos de restricción implícitas, use `-optionstrict:custom`. Use `-nowarn:numberlist` para omitir advertencias concretas y `-warnaserror:numberlist` para tratar advertencias concretas como errores.

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Para Set-OptionStrict en el IDE de Visual Studio

1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **proyecto** , haga clic en **propiedades.**

2. Haga clic en la pestaña **Compilar**.

3. Modifique el valor en el cuadro **Option Strict** .

### <a name="to-set--optionstrict-programmatically"></a>Para establecer-OptionStrict mediante programación

Consulte [Option Strict (instrucción](../../../visual-basic/language-reference/statements/option-strict-statement.md)).

## <a name="example"></a>Ejemplo

El código siguiente compila `Test.vb` mediante la semántica estricta de tipos.

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [-warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Valores predeterminados de Visual Basic, Proyectos, Cuadro de diálogo Opciones](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
