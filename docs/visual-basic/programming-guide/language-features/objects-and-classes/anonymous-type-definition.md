---
title: Definición de tipos anónimos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 5f6486965d9e44524420975523e10ded32a135b7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755217"
---
# <a name="anonymous-type-definition-visual-basic"></a>Definición de tipos anónimos (Visual Basic)

En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades para el tipo especificadas.

## <a name="compiler-generated-code"></a>Código generado por el compilador

La siguiente definición de `product`, el compilador crea una nueva definición de clase que contiene propiedades `Name`, `Price`, y `OnHand`.

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

La definición de clase contiene las definiciones de propiedad similares al siguiente. Tenga en cuenta que no hay ningún `Set` método para las propiedades de clave. Los valores de las propiedades clave son de solo lectura.

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

Además, las definiciones de tipo anónimo contienen un constructor sin parámetros. No se permiten los constructores que requieren parámetros.

Si una declaración de tipo anónimo contiene al menos una propiedad clave, la definición de tipo invalida tres miembros heredados de <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, y <xref:System.Object.ToString%2A>. Si no se declara ninguna propiedad clave, solo <xref:System.Object.ToString%2A> se reemplaza. Las invalidaciones proporcionan la funcionalidad siguiente:

- `Equals` Devuelve `True` si dos instancias de tipo anónimo son la misma instancia o si cumplen las condiciones siguientes:

  - Tienen el mismo número de propiedades.

  - Las propiedades se declaran en el mismo orden, con los mismos nombres y los mismos tipos deducidos. Las comparaciones de nombres no distinguen mayúsculas de minúsculas.

  - Al menos una de las propiedades es una propiedad clave y el `Key` palabra clave se aplica a las mismas propiedades.

  - Comparación de cada par correspondiente de las propiedades de clave devuelve `True`.

    Por ejemplo, en los ejemplos siguientes, `Equals` devuelve `True` sólo para `employee01` y `employee08`. El comentario antes de cada línea especifica la razón por la nueva instancia no coinciden `employee01`.

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- `GetHashcode` Proporciona un algoritmo GetHashCode único correctamente. El algoritmo usa sólo las propiedades de clave para calcular el código hash.

- `ToString` Devuelve una cadena concatenada de valores de propiedad, como se muestra en el ejemplo siguiente. Clave y propiedades de clave no se incluyen.

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

Propiedades con nombre explícito de un tipo anónimo no pueden entrar en conflicto con estos métodos generados. Es decir, no puede usar `.Equals`, `.GetHashCode`, o `.ToString` a una propiedad de nombre.

Las definiciones de tipo anónimo que incluyen al menos una propiedad de clave también implementan la <xref:System.IEquatable%601?displayProperty=nameWithType> interfaz, donde `T` es el tipo del tipo anónimo.

> [!NOTE]
> Declaraciones de tipos anónimos creación el mismo tipo anónimo sólo si se producen en el mismo ensamblado, sus propiedades tienen los mismos nombres y los mismos tipos deducidos, las propiedades se declaran en el mismo orden y las mismas propiedades se marcan como propiedades de clave.

## <a name="see-also"></a>Vea también

- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Cómo: Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
