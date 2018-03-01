---
title: "Definición de tipos anónimos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8b5b7eba55d719c1482b7224ecffc78b776feb00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-definition-visual-basic"></a>Definición de tipos anónimos (Visual Basic)
En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades especificadas para el tipo.  
  
## <a name="compiler-generated-code"></a>Código generado por el compilador  
 En la siguiente definición de `product`, el compilador crea una nueva definición de clase que contiene propiedades `Name`, `Price`, y `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 La definición de clase contiene definiciones de propiedad similares al siguiente. Tenga en cuenta que no hay ningún `Set` método para las propiedades de clave. Los valores de las propiedades de clave son de sólo lectura.  
  
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
  
 Además, las definiciones de tipos anónimos contienen un constructor predeterminado. No se permiten constructores que requieren parámetros.  
  
 Si una declaración de tipo anónimo contiene al menos una propiedad de clave, la definición de tipo invalida tres miembros heredados de <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, y <xref:System.Object.ToString%2A>. Si no se declara ninguna propiedad clave, solo <xref:System.Object.ToString%2A> se invalida. Las invalidaciones proporcionan la funcionalidad siguiente:  
  
-   `Equals`Devuelve `True` si dos instancias de tipo anónimo son la misma instancia o si cumplen las condiciones siguientes:  
  
    -   Tienen el mismo número de propiedades.  
  
    -   Las propiedades se declaran en el mismo orden, con los mismos nombres y los mismos tipos deducidos. Las comparaciones de nombres no distinguen mayúsculas de minúsculas.  
  
    -   Al menos una de las propiedades es una propiedad clave y el `Key` palabra clave se aplica a las mismas propiedades.  
  
    -   Comparación de cada par correspondiente de propiedades de clave devuelve `True`.  
  
     Por ejemplo, en los ejemplos siguientes, `Equals` devuelve `True` sólo para `employee01` y `employee08`. El comentario que precede a cada línea especifica la razón por qué no coincide con la nueva instancia `employee01`.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode`Proporciona un algoritmo GetHashCode único correctamente. El algoritmo utiliza sólo las propiedades de clave para calcular el código hash.  
  
-   `ToString`Devuelve una cadena de valores de propiedad concatenados, como se muestra en el ejemplo siguiente. Clave y propiedades de clave no se incluyen.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 Propiedades con nombre explícito de un tipo anónimo no se pueden entrar en conflicto con estos métodos generados. Es decir, no puede usar `.Equals`, `.GetHashCode`, o `.ToString` a un nombre de propiedad.  
  
 Las definiciones de tipo anónimo que incluyen al menos una propiedad clave también implementan la <xref:System.IEquatable%601?displayProperty=nameWithType> interfaz, donde `T` es el tipo del tipo anónimo.  
  
> [!NOTE]
>  Declaraciones de tipos anónimos crear el mismo tipo anónimo sólo si se producen en el mismo ensamblado, sus propiedades tienen los mismos nombres y los mismos tipos deducidos, las propiedades se declaran en el mismo orden y se marcan las mismas propiedades como propiedades de clave.  
  
## <a name="see-also"></a>Vea también  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
