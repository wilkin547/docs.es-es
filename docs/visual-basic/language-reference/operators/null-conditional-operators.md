---
title: Operadores condicionales null (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 4815fe7ad337634cfb56127fbd24a47a37fdd74b
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65062947"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. ¿y? operadores condicionales null () (Visual Basic)

Comprueba el valor del operando izquierdo es null (`Nothing`) antes de realizar un acceso a miembros (`?.`) o un índice (`?()`) devuelve la operación; `Nothing` si el operando izquierdo se evalúa como `Nothing`. Tenga en cuenta que en las expresiones que devuelven normalmente los tipos de valor, el operador condicional null devuelve un <xref:System.Nullable%601>.

Estos operadores ayudan a escribir menos código para controlar las comprobaciones de valores null, especialmente cuando descender en estructuras de datos. Por ejemplo:

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

Para la comparación, el código alternativo para la primera de estas expresiones sin un operador condicional null es:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

A veces es necesario realizar una acción en un objeto que puede ser null, según el valor de un miembro Boolean en ese objeto (como la propiedad booleana `IsAllowedFreeShipping` en el ejemplo siguiente):

```vb
  Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
  
  If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
   ApplyFreeShippingToOrders(customer)
  End If
```

Puede reducir el código y evitar manualmente la comprobación de null con el operador condicional null como sigue:

```vb
 Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
 
 If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

Los operadores de condición NULL se cortocircuitan.  Si una operación en una cadena de las operaciones de índice y de acceso de miembro condicional devuelve `Nothing`, el resto de se detiene la ejecución de la cadena.  En el ejemplo siguiente, `C(E)` no se evalúa si `A`, `B`, o `C` se evalúa como `Nothing`.

```vb
A?.B?.C?(E);
```

Otro uso de acceso a miembros condicional null es invocar delegados de manera segura para subprocesos con mucho menos código.  El siguiente ejemplo define dos tipos, un `NewsBroadcaster` y un `NewsReceiver`. Elementos de noticias se envían al receptor por la `NewsBroadcaster.SendNews` delegar.

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String) 

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

Si no hay ningún elemento en el `SendNews` lista de invocación, el `SendNews` delegado inicia un <xref:System.NullReferenceException>. Antes de los operadores condicionales null, el código como el siguiente garantiza que la lista de invocaciones del delegado no era `Nothing`:

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

La nueva manera es mucho más sencilla:  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `SendNews` solo una vez, manteniendo el resultado en una variable temporal. Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `SendNews?(String)`.  

## <a name="see-also"></a>Vea también

- [Operadores (Visual Basic)](index.md)
- [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)
- [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)
