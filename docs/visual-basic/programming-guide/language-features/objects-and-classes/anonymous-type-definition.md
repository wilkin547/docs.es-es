---
title: "Definici&#243;n de tipos an&#243;nimos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos anónimos [Visual Basic], definición de tipo"
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Definici&#243;n de tipos an&#243;nimos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades especificadas del tipo.  
  
## Código generado por compilador  
 En la siguiente definición de `product`, el compilador crea una nueva definición de clase que contiene las propiedades `Name`, `Price` y `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 La definición de clase contiene definiciones de propiedad similares a la siguiente.  Observe que no hay ningún método `Set` para las propiedades de clave.  Los valores de las propiedades de clave son de sólo lectura.  
  
```vb#  
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
  
 Además, las definiciones de tipos anónimos contienen un constructor predeterminado.  No se permiten los constructores que requieran parámetros.  
  
 Si una declaración de tipos anónimos contiene al menos una propiedad de clave, la definición de tipos invalida tres miembros heredados de <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A> y <xref:System.Object.ToString%2A>.  Si no se declara ninguna propiedad de clave, sólo se invalida <xref:System.Object.ToString%2A>.  Las invalidaciones proporcionan la funcionalidad siguiente:  
  
-   `Equals` devuelve `True` si dos instancias de tipo anónimo son la misma instancia o si cumplen las condiciones siguientes:  
  
    -   Tienen el mismo número de propiedades.  
  
    -   Las propiedades se declaran en el mismo orden, con los mismos nombres y los mismos tipos deducidos.  Las comparaciones de nombres no distinguen mayúsculas de minúsculas.  
  
    -   Al menos una de las propiedades es una propiedad de clave y la palabra clave `Key` se aplica a las mismas propiedades.  
  
    -   La comparación de cada par correspondiente de propiedades de clave devuelve `True`.  
  
     Por ejemplo, en los ejemplos siguientes, `Equals` devuelve `True` sólo para `employee01` y `employee08`.  El comentario situado delante de que cada línea especifica la razón por la que la nueva instancia no coincide con `employee01`.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode` proporciona un algoritmo GetHashCode único correctamente.  El algoritmo utiliza sólo las propiedades de clave para calcular el código hash.  
  
-   `ToString` devuelve una cadena de valores de propiedad concatenados, como se muestra en el ejemplo siguiente.  Se incluyen tanto las propiedades de clave como las que no lo son.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 Explícitamente las propiedades con nombre de un tipo anónimo no pueden estar en conflicto con estos métodos generados.  Es decir, no puede utilizar `.Equals`, `.GetHashCode`ni `.ToString` para asignar un nombre a una propiedad.  
  
 Las definiciones de tipo anónimas que incluyen por lo menos una propiedad de clave también implementan la interfaz <xref:System.IEquatable%601?displayProperty=fullName>, donde `T` es el tipo del tipo anónimo.  
  
> [!NOTE]
>  Las declaraciones de tipos anónimas crean el mismo tipo anónimo sólo si producen en el mismo ensamblado, sus propiedades tienen los mismos nombres y los mismos tipos deducidos, las propiedades se declaran en el mismo orden y se marcan las mismas propiedades como propiedades de clave.  
  
## Vea también  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Cómo: Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)