---
title: CType (Función) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 4a0391b0a5d76f36803b433369d4832c02b05e09
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592095"
---
# <a name="ctype-function-visual-basic"></a>CType (Función) (Visual Basic)

Devuelve el resultado de convertir explícitamente una expresión en un tipo de datos, objeto, estructura, clase o interfaz especificados.

## <a name="syntax"></a>Sintaxis

```vb
CType(expression, typename)
```

## <a name="parts"></a>Elementos

`expression` cualquier expresión válida. Si el valor de `expression` está fuera del intervalo permitido por `typename`, Visual Basic produce una excepción.

`typename` cualquier expresión válida dentro de una cláusula `As` en una instrucción @no__t 2, es decir, el nombre de cualquier tipo de datos, objeto, estructura, clase o interfaz.

## <a name="remarks"></a>Comentarios

> [!TIP]
> También puede utilizar las siguientes funciones para realizar una conversión de tipos:
>
> - Funciones de conversión de tipos como `CByte`, `CDbl` y `CInt` que realizan una conversión a un tipo de datos específico. Para obtener más información, vea [funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md).
> - [Operador DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) o [TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md). Estos operadores requieren que un tipo herede de o implemente el otro tipo. Pueden proporcionar un rendimiento algo mejor que `CType` al convertir a y desde el tipo de datos `Object`.

`CType` se compila en línea, lo que significa que el código de conversión forma parte del código que evalúa la expresión. En algunos casos, el código se ejecuta más rápido porque no se llama a ningún procedimiento para realizar la conversión.

Si no se define ninguna conversión de `expression` a `typename` (por ejemplo, de `Integer` a `Date`), Visual Basic muestra un mensaje de error en tiempo de compilación.

Si se produce un error en la conversión en tiempo de ejecución, se produce la excepción adecuada. Si se produce un error en una conversión de restricción, un <xref:System.OverflowException> es el resultado más común. Si la conversión no está definida, se produce una excepción <xref:System.InvalidCastException>. Por ejemplo, esto puede ocurrir si `expression` es de tipo `Object` y su tipo en tiempo de ejecución no tiene ninguna conversión a `typename`.

Si el tipo de datos de `expression` o `typename` es una clase o estructura que ha definido, puede definir @no__t 2 en esa clase o estructura como operador de conversión. Esto hace que `CType` actúe como un *operador sobrecargado*. Si lo hace, puede controlar el comportamiento de las conversiones hacia y desde la clase o estructura, incluidas las excepciones que se pueden producir.

## <a name="overloading"></a>Sobrecarga

El operador `CType` también se puede sobrecargar en una clase o estructura definida fuera del código. Si el código se convierte en o desde una clase o estructura de este tipo, asegúrese de que comprende el comportamiento de su operador `CType`. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Convertir objetos dinámicos

Las conversiones de tipos de objetos dinámicos se realizan mediante conversiones dinámicas definidas por el usuario que utilizan los métodos <xref:System.Dynamic.DynamicObject.TryConvert%2A> o <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>. Si está trabajando con objetos dinámicos, utilice el método <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> para convertir el objeto dinámico.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa la función `CType` para convertir una expresión al tipo de datos `Single`.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Para obtener más ejemplos, vea [conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>Vea también

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Funciones de conversión](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Cómo: Definir un operador de conversión @ no__t-0
- [Conversión de tipos en .NET Framework](../../../standard/base-types/type-conversion.md)
