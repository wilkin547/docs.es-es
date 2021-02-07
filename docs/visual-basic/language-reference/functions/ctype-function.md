---
description: 'Más información sobre: función CType (Visual Basic)'
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 9732f52b40e5f762769ba5dc340c000e7e1ba17a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701266"
---
# <a name="ctype-function-visual-basic"></a>CType (Función) (Visual Basic)

Devuelve el resultado de convertir explícitamente una expresión en un tipo de datos, objeto, estructura, clase o interfaz especificados.

## <a name="syntax"></a>Sintaxis

```vb
CType(expression, typename)
```

## <a name="parts"></a>Partes

`expression` Cualquier expresión válida. Si el valor de `expression` está fuera del intervalo permitido por `typename` , Visual Basic produce una excepción.

`typename` Cualquier expresión válida dentro de una `As` cláusula de una `Dim` instrucción, es decir, el nombre de cualquier tipo de datos, objeto, estructura, clase o interfaz.

## <a name="remarks"></a>Observaciones

> [!TIP]
> También puede utilizar las siguientes funciones para realizar una conversión de tipos:
>
> - Funciones de conversión de tipos como `CByte` , `CDbl` y `CInt` que realizan una conversión a un tipo de datos específico. Para obtener más información, vea [Funciones de conversión de tipos](type-conversion-functions.md).
> - [Operador DirectCast](../operators/directcast-operator.md) o [TryCast](../operators/trycast-operator.md). Estos operadores requieren que un tipo herede de o implemente el otro tipo. Pueden proporcionar un rendimiento algo mejor que `CType` al convertir a y desde el `Object` tipo de datos.

`CType` está compilado insertado, lo que significa que el código de conversión forma parte del código que evalúa la expresión. En algunos casos, el código se ejecuta más rápido porque no se llama a ningún procedimiento para realizar la conversión.

Si no se define ninguna conversión de `expression` a `typename` (por ejemplo, de `Integer` a `Date` ), Visual Basic muestra un mensaje de error en tiempo de compilación.

Si se produce un error en la conversión en tiempo de ejecución, se produce la excepción adecuada. Si se produce un error en una conversión de restricción, <xref:System.OverflowException> es el resultado más común. Si la conversión no está definida, se <xref:System.InvalidCastException> produce una excepción. Por ejemplo, esto puede ocurrir si `expression` es de tipo `Object` y su tipo en tiempo de ejecución no tiene ninguna conversión a `typename` .

Si el tipo de datos de `expression` o `typename` es una clase o estructura que ha definido, puede definir `CType` en esa clase o estructura como un operador de conversión. Esto hace `CType` que actúe como un *operador sobrecargado*. Si lo hace, puede controlar el comportamiento de las conversiones hacia y desde la clase o estructura, incluidas las excepciones que se pueden producir.

## <a name="overloading"></a>Sobrecarga

El `CType` operador también se puede sobrecargar en una clase o estructura definida fuera del código. Si el código se convierte en o desde una clase o estructura de este tipo, asegúrese de que comprende el comportamiento de su `CType` operador. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Convertir objetos dinámicos

Las conversiones de tipos de objetos dinámicos se realizan mediante conversiones dinámicas definidas por el usuario que utilizan los <xref:System.Dynamic.DynamicObject.TryConvert%2A> <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> métodos o. Si está trabajando con objetos dinámicos, utilice el <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> método para convertir el objeto dinámico.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se utiliza la `CType` función para convertir una expresión al `Single` tipo de datos.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Para obtener más ejemplos, vea [conversiones implícitas y explícitas](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>Vea también

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [Type Conversion Functions](type-conversion-functions.md)
- [Funciones de conversión](conversion-functions.md)
- [Operator Statement](../statements/operator-statement.md)
- [Procedimiento para definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Conversión de tipos en .NET Framework](../../../standard/base-types/type-conversion.md)
