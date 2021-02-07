---
description: 'Más información acerca de: Option Infer (instrucción)'
title: Option Infer (instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
ms.openlocfilehash: d0c3de7bdafb7e9b361da7a8538046e3d76b5ce7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741593"
---
# <a name="option-infer-statement"></a>Option Infer (instrucción)

Permite el uso de la inferencia de tipo de variable local en la declaración de variables.

## <a name="syntax"></a>Sintaxis

```vb
Option Infer { On | Off }
```

## <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`On`|Opcional. Habilita la inferencia de tipo de variable local.|
|`Off`|Opcional. Deshabilita la inferencia de tipo de variable local.|

## <a name="remarks"></a>Observaciones

Para establecer `Option Infer` en un archivo, escriba `Option Infer On` o `Option Infer Off` en la parte superior del archivo, antes de cualquier otro código fuente. Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.

Al establecer `Option Infer` en `On`, puede declarar variables locales sin especificar explícitamente un tipo de datos. El compilador deduce el tipo de datos de una variable a partir del tipo de su expresión de inicialización.

En la siguiente ilustración, `Option Infer` está activado. La variable de la declaración `Dim someVar = 2` se declara como un entero mediante la inferencia de tipo.

En la captura de pantalla siguiente se muestra IntelliSense cuando Option Infer está activada:

![Captura de pantalla que muestra la vista de IntelliSense cuando Option Infer está activada.](./media/option-infer-statement/option-infer-as-integer-on.png)

En la siguiente ilustración, `Option Infer` está desactivado. La variable de la declaración `Dim someVar = 2` se declara como un `Object` mediante la inferencia de tipo. En este ejemplo, el valor **Option Strict** está establecido en **OFF** en la [Página compilar, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).

La captura de pantalla siguiente muestra IntelliSense cuando Option Infer es OFF:

![Captura de pantalla que muestra la vista de IntelliSense cuando Option Infer es OFF.](./media/option-infer-statement/option-infer-as-object-off.png)

> [!NOTE]
> Cuando una variable se declara como un `Object`, el tipo de tiempo de ejecución puede cambiar mientras se ejecuta el programa. Visual Basic realiza operaciones llamadas *Boxing* y *unboxing* para realizar la conversión entre un `Object` y un tipo de valor, lo que hace que la ejecución sea más lenta. Para obtener información sobre las conversiones boxing y unboxing, vea la [especificación del lenguaje Visual Basic](~/_vblang/spec/conversions.md#value-type-conversions).

La inferencia de tipo se aplica en el nivel de procedimiento, y no se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz.

Para obtener más información, consulte [inferencia de tipo de local](../../programming-guide/language-features/variables/local-type-inference.md).

## <a name="when-an-option-infer-statement-is-not-present"></a>Cuando la instrucción Option Infer no está presente

Si el código fuente no contiene una `Option Infer` instrucción, se utiliza la configuración **Option Infer** en la [Página compilar, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Si se usa el compilador de línea de comandos, se usa la opción del compilador [-optioninfer (](../../reference/command-line-compiler/optioninfer.md) .

#### <a name="to-set-option-infer-in-the-ide"></a>Cómo establecer Option Infer en el IDE

1. En el **Explorador de soluciones**, seleccione un proyecto. En el menú **Proyecto**, haga clic en **Propiedades**.

2. Haga clic en la pestaña **Compilar**.

3. Establezca el valor en el cuadro **Option Infer** .

Al crear un nuevo proyecto, el valor **Option Infer** de la pestaña **compilar** se establece en el valor **Option Infer** del cuadro de diálogo **valores predeterminados de VB** . Para tener acceso al cuadro de diálogo **valores predeterminados de VB** , en el menú **herramientas** , haga clic en **Opciones**. En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**. La configuración predeterminada inicial en los **valores predeterminados de VB** es `On` .

#### <a name="to-set-option-infer-on-the-command-line"></a>Cómo establecer Option Infer en la línea de comandos

Incluya la opción del compilador [-optioninfer (](../../reference/command-line-compiler/optioninfer.md) en el comando **VBC** .

## <a name="default-data-types-and-values"></a>Tipos de datos y valores predeterminados

En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.

|¿Tipo de datos especificado?|¿Inicializador especificado?|Ejemplo|Resultado|
|---|---|---|---|
|No|No|`Dim qty`|Si `Option Strict` está desactivado (valor predeterminado), la variable se establece en `Nothing`.<br /><br /> Si `Option Strict` está activado, se produce un error en tiempo de compilación.|
|No|Sí|`Dim qty = 5`|Si `Option Infer` está activado (valor predeterminado), la variable toma el tipo de datos del inicializador. Vea [inferencia de tipo de local](../../programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.|
|Sí|No|`Dim qty As Integer`|La variable se inicializa con el valor predeterminado del tipo de datos. Para obtener más información, vea [Dim (instrucción](dim-statement.md)).|
|Sí|Sí|`Dim qty  As Integer = 5`|Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.|

## <a name="example"></a>Ejemplo

Los ejemplos siguientes muestran cómo la instrucción `Option Infer` habilita la inferencia de tipo local.

[!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]

## <a name="example"></a>Ejemplo

El siguiente ejemplo demuestra que el tipo en tiempo de ejecución puede ser diferente cuando una variable se identifica como un `Object`.

[!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]

## <a name="see-also"></a>Vea también

- [Instrucción Dim](dim-statement.md)
- [Inferencia de tipo de variable local](../../programming-guide/language-features/variables/local-type-inference.md)
- [Option Compare (instrucción)](option-compare-statement.md)
- [Option Explicit (instrucción)](option-explicit-statement.md)
- [Option Strict (instrucción)](option-strict-statement.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [-optioninfer](../../reference/command-line-compiler/optioninfer.md)
- [Conversión boxing y conversión unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
