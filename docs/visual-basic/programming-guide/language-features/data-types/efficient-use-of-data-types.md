---
description: 'Más información acerca de: uso eficiente de tipos de datos (Visual Basic)'
title: Uso eficiente de los tipos de datos
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: e7660bbdec530ef18d663975e314d90b64e4b055
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476441"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Uso eficiente de tipos de datos (Visual Basic)

A las variables no declaradas y a las variables declaradas sin un tipo de datos se les asigna el `Object` tipo de datos. Esto facilita la escritura rápida de programas, pero puede hacer que se ejecuten más lentamente.

## <a name="strong-typing"></a>Establecimiento fuerte de tipos

 La especificación de tipos de datos para todas las variables se conoce como *fuertemente* tipados. El uso de tipos fuertemente tipados tiene varias ventajas:

- Habilita la compatibilidad con IntelliSense para las variables. Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.

- Aprovecha la comprobación del tipo de compilador. Esto detecta instrucciones que pueden producir errores en tiempo de ejecución debido a errores como el desbordamiento. También detecta llamadas a métodos en objetos que no las admiten.

- Esto da como resultado una ejecución más rápida del código.

## <a name="most-efficient-data-types"></a>Tipos de datos más eficaces

 En el caso de las variables que nunca contienen fracciones, los tipos de datos enteros son más eficaces que los tipos no enteros. En Visual Basic, `Integer` y `UInteger` son los tipos numéricos más eficaces.

 En el caso de los números fraccionarios, `Double` es el tipo de datos más eficaz, ya que los procesadores de las plataformas actuales realizan operaciones de punto flotante de doble precisión. Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer` .

## <a name="specifying-data-type"></a>Especificar el tipo de datos

 Use la [instrucción Dim](../../../language-reference/statements/dim-statement.md) para declarar una variable de un tipo específico. Puede especificar su nivel de acceso simultáneamente mediante la palabra clave [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)o [Private](../../../language-reference/modifiers/private.md) , como en el ejemplo siguiente.

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a>Conversión de caracteres

 Las `AscW` `ChrW` funciones y funcionan en Unicode. Debe utilizarlos en preferencia a `Asc` y `Chr` , que deben traducirse dentro y fuera de Unicode.

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Tipo de datos](index.md)
- [Tipos de datos numéricos](numeric-data-types.md)
- [Declaración de variable](../variables/variable-declaration.md)
- [Usar IntelliSense](/visualstudio/ide/using-intellisense)
