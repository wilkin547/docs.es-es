---
description: Mas información sobre -optionstrict
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: ad58c7775eaa77c1bf693629cf12cc70e4222920
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475908"
---
# <a name="-optionstrict"></a>-optionstrict

Exige la semántica estricta de tipos para restringir las conversiones implícitas de tipos.

## <a name="syntax"></a>Sintaxis

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a>Argumentos

`+` &#124; `-`  
Opcional. La opción `-optionstrict+` restringe la conversión de tipos implícita. El valor predeterminado de esta opción es `-optionstrict-`. La opción `-optionstrict+` equivale a `-optionstrict`. Puede usar las dos para la semántica de tipos permisiva.

`custom`  
Obligatorio. Advertir cuando no se respete la semántica estricta del lenguaje.

## <a name="remarks"></a>Comentarios

Cuando `-optionstrict+` está en vigor, solo se pueden realizar conversiones de ampliación de tipos de forma implícita. Las conversiones de restricción de tipos implícitas, como la asignación de un objeto de tipo `Decimal` a un objeto de tipo entero, se muestran como errores.

Para generar advertencias para las conversiones de restricción de tipos implícitas, use `-optionstrict:custom`. Use `-nowarn:numberlist` para omitir advertencias concretas y `-warnaserror:numberlist` para tratar las advertencias concretas como errores.

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>Para establecer -optionstrict en el IDE de Visual Studio

1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.

2. Haga clic en la pestaña **Compilar**.

3. Modifique el valor del cuadro **Option Strict**.

### <a name="to-set--optionstrict-programmatically"></a>Para establecer -optionstrict mediante programación

Vea [Option Strict (instrucción)](../../language-reference/statements/option-strict-statement.md).

## <a name="example"></a>Ejemplo

El código siguiente compila `Test.vb` mediante la semántica estricta de tipos.

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-optioncompare](optioncompare.md)
- [-optionexplicit](optionexplicit.md)
- [-optioninfer](optioninfer.md)
- [-nowarn](nowarn.md)
- [-warnaserror (Visual Basic)](warnaserror.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Option Strict (instrucción)](../../language-reference/statements/option-strict-statement.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
