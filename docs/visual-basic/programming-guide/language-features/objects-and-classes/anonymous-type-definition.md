---
title: Definición de tipo anónimo
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 952eb295cc71eab5d0ad6e18f2b697a9b701b434
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404906"
---
# <a name="anonymous-type-definition-visual-basic"></a>Definición de tipos anónimos (Visual Basic)

En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades especificadas para el tipo.

## <a name="compiler-generated-code"></a>Código generado por el compilador

En la siguiente definición de `product` , el compilador crea una nueva definición de clase que contiene las propiedades `Name` , `Price` y `OnHand` .

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

La definición de clase contiene definiciones de propiedades similares a las siguientes. Observe que no hay ningún `Set` método para las propiedades de clave. Los valores de las propiedades de clave son de solo lectura.

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

Además, las definiciones de tipos anónimos contienen un constructor sin parámetros. No se permiten constructores que requieran parámetros.

Si una declaración de tipos anónimos contiene al menos una propiedad de clave, la definición de tipo invalida tres miembros heredados de <xref:System.Object> : <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> y <xref:System.Object.ToString%2A> . Si no se declara ninguna propiedad clave, solo <xref:System.Object.ToString%2A> se invalida. Las invalidaciones proporcionan la siguiente funcionalidad:

- `Equals`Devuelve `True` si dos instancias de tipo anónimo son la misma instancia, o si cumplen las condiciones siguientes:

  - Tienen el mismo número de propiedades.

  - Las propiedades se declaran en el mismo orden, con los mismos nombres y los mismos tipos deducidos. Las comparaciones de nombres no distinguen mayúsculas de minúsculas.

  - Al menos una de las propiedades es una propiedad de clave y la `Key` palabra clave se aplica a las mismas propiedades.

  - La comparación de cada par correspondiente de propiedades de clave devuelve `True` .

    Por ejemplo, en los ejemplos siguientes, `Equals` devuelve `True` solo para `employee01` y `employee08` . El comentario antes de cada línea especifica el motivo por el que la nueva instancia no coincide `employee01` .

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- `GetHashcode`proporciona un algoritmo GetHashCode único y adecuado. El algoritmo solo usa las propiedades de clave para calcular el código hash.

- `ToString`Devuelve una cadena de valores de propiedad concatenados, tal y como se muestra en el ejemplo siguiente. Se incluyen las propiedades de clave y no clave.

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

Las propiedades con nombre explícito de un tipo anónimo no pueden entrar en conflicto con estos métodos generados. Es decir, no puede utilizar `.Equals` , `.GetHashCode` o `.ToString` para asignar un nombre a una propiedad.

Las definiciones de tipos anónimos que incluyen al menos una propiedad de clave también implementan la <xref:System.IEquatable%601?displayProperty=nameWithType> interfaz, donde `T` es el tipo del tipo anónimo.

> [!NOTE]
> Las declaraciones de tipos anónimos crean el mismo tipo anónimo solo si se producen en el mismo ensamblado, sus propiedades tienen los mismos nombres y los mismos tipos inferidos, las propiedades se declaran en el mismo orden y las mismas propiedades se marcan como propiedades de clave.

## <a name="see-also"></a>Consulte también

- [Tipos anónimos](anonymous-types.md)
- [Procedimiento para deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
