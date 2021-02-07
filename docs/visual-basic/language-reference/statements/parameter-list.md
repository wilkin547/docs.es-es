---
description: 'Más información acerca de: lista de parámetros (Visual Basic)'
title: Lista de parámetros
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: f69063fac82887ba4da3119d8ec4fcac11b7f4c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741411"
---
# <a name="parameter-list-visual-basic"></a>Lista de parámetros (Visual Basic)

Especifica los parámetros que un procedimiento espera cuando se llama. Varios parámetros se separan mediante comas. A continuación se encuentra la sintaxis de un parámetro.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a>Partes

`attributelist`  
Opcional. Lista de atributos que se aplican a este parámetro. Debe incluir la [lista de atributos](attribute-list.md) entre corchetes angulares (" `<` " y " `>` ").

`Optional`  
Opcional. Especifica que este parámetro no es necesario cuando se llama al procedimiento.

`ByVal`  
Opcional. Especifica que el procedimiento no puede reemplazar o volver a asignar el elemento variable subyacente al argumento correspondiente en el código de llamada.

`ByRef`  
Opcional. Especifica que el procedimiento puede modificar el elemento variable subyacente en el código de llamada de la misma manera que el propio código de llamada puede.

`ParamArray`  
Opcional. Especifica que el último parámetro de la lista de parámetros es una matriz opcional de elementos del tipo de datos especificado. Esto permite al código de llamada pasar un número arbitrario de argumentos al procedimiento.

`parametername`  
Necesario. Nombre de la variable local que representa el parámetro.

`parametertype`  
Obligatorio si `Option Strict` es `On` . Tipo de datos de la variable local que representa el parámetro.

`defaultvalue`  
Obligatorio para `Optional` los parámetros. Cualquier expresión constante o constante que se evalúe como el tipo de datos del parámetro. Si el tipo es `Object` , o una clase, interfaz, matriz o estructura, el valor predeterminado solo puede ser `Nothing` .

## <a name="remarks"></a>Observaciones

Los parámetros se incluyen entre paréntesis y se separan mediante comas. Un parámetro se puede declarar con cualquier tipo de datos. Si no especifica, el `parametertype` valor predeterminado es `Object` .

Cuando el código de llamada llama al procedimiento, pasa un *argumento* a cada parámetro necesario. Para obtener más información, vea [diferencias entre parámetros y argumentos](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).

El argumento que el código de llamada pasa a cada parámetro es un puntero a un elemento subyacente en el código de llamada. Si este elemento no es *variable* (una constante, un literal, una enumeración o una expresión), es imposible que cualquier código lo cambie. Si es un elemento *variable* (una variable declarada, un campo, una propiedad, un elemento de matriz o un elemento de estructura), el código de llamada puede cambiarlo. Para obtener más información, vea [diferencias entre argumentos modificables y no modificables](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).

Si se pasa un elemento variable `ByRef` , el procedimiento también lo puede cambiar. Para obtener más información, vea [diferencias entre pasar un argumento por valor y por referencia](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).

## <a name="rules"></a>Reglas

- **Paréntesis.** Si especifica una lista de parámetros, debe escribirla entre paréntesis. Si no hay ningún parámetro, todavía puede usar paréntesis que incluyan una lista vacía. Esto mejora la legibilidad del código al aclarar que el elemento es un procedimiento.

- **Parámetros opcionales.** Si utiliza el `Optional` modificador en un parámetro, todos los parámetros subsiguientes de la lista también deben ser opcionales y declararse mediante el `Optional` modificador.

     Cada declaración de parámetro opcional debe proporcionar la `defaultvalue` cláusula.

     Para obtener más información, vea [parámetros opcionales](../../programming-guide/language-features/procedures/optional-parameters.md).

- **Matrices de parámetros.** Debe especificar `ByVal` para un `ParamArray` parámetro.

     No puede utilizar `Optional` y `ParamArray` en la misma lista de parámetros.

     Para obtener más información, consulte [matrices de parámetros](../../programming-guide/language-features/procedures/parameter-arrays.md).

- **Pasando el mecanismo.** El mecanismo predeterminado para cada argumento es `ByVal` , lo que significa que el procedimiento no puede cambiar el elemento variable subyacente. Sin embargo, si el elemento es un tipo de referencia, el procedimiento puede modificar el contenido o los miembros del objeto subyacente, aunque no puede reemplazar o volver a asignar el propio objeto.

- **Nombres de parámetro.** Si el tipo de datos del parámetro es una matriz, siga `parametername` inmediatamente entre paréntesis. Para obtener más información sobre los nombres de parámetros, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un `Function` procedimiento que define dos parámetros.

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Instrucción Function](function-statement.md)
- [Instrucción Sub](sub-statement.md)
- [Declare Statement](declare-statement.md)
- [Structure (Instrucción)](structure-statement.md)
- [Option Strict (instrucción)](option-strict-statement.md)
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
- [Procedimiento Interrupción y combinación de instrucciones en código](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
