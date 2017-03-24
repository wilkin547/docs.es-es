---
title: "Cómo: agregar métodos personalizados para las consultas LINQ (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a>Cómo: agregar métodos personalizados para las consultas LINQ (Visual Basic)
Puede extender el conjunto de métodos que puede utilizar para las consultas LINQ agregando métodos de extensión para el <xref:System.Collections.Generic.IEnumerable%601>interfaz.</xref:System.Collections.Generic.IEnumerable%601> Por ejemplo, además de la media estándar o el número máximo de operaciones, puede crear un método de agregación personalizado para calcular un valor único de una secuencia de valores. También puede crear un método que funciona como un filtro personalizado o transformación de datos específica para una secuencia de valores y devuelve una nueva secuencia. Ejemplos de tales métodos son <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>y <xref:System.Linq.Enumerable.Reverse%2A>.</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A>  
  
 Si extiende el <xref:System.Collections.Generic.IEnumerable%601>interfaz, puede aplicar los métodos personalizados a cualquier colección enumerable.</xref:System.Collections.Generic.IEnumerable%601> Para obtener más información, consulte [métodos de extensión](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="adding-an-aggregate-method"></a>Agregar un método de agregación  
 Un método de agregación calcula un valor único de un conjunto de valores. LINQ proporciona varios métodos de agregación, incluidos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>y <xref:System.Linq.Enumerable.Max%2A>.</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A> Puede crear su propio método de agregación agregando un método de extensión para el <xref:System.Collections.Generic.IEnumerable%601>interfaz.</xref:System.Collections.Generic.IEnumerable%601>  
  
 En el ejemplo de código siguiente se muestra cómo crear un método de extensión denominado `Median` para calcular el valor medio de una secuencia de números de tipo `double`.  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module LINQExtension  
  
    ' Extension method for the IEnumerable(of T) interface.   
    ' The method accepts only values of the Double type.  
    <Extension()>   
    Function Median(ByVal source As IEnumerable(Of Double)) As Double  
        If source.Count = 0 Then  
            Throw New InvalidOperationException("Cannot compute median for an empty set.")  
        End If  
  
        Dim sortedSource = From number In source   
                           Order By number  
  
        Dim itemIndex = sortedSource.Count \ 2  
  
        If sortedSource.Count Mod 2 = 0 Then  
            ' Even number of items in list.  
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2  
        Else  
            ' Odd number of items in list.  
            Return sortedSource(itemIndex)  
        End If  
    End Function  
End Module  
```  
  
 Llamar a este método de extensión para cualquier colección enumerable de la misma manera que se llama a otros métodos de agregación de la <xref:System.Collections.Generic.IEnumerable%601>interfaz.</xref:System.Collections.Generic.IEnumerable%601>  
  
> [!NOTE]
>  En Visual Basic, puede usar una llamada de método o sintaxis de consulta estándar para la `Aggregate` o `Group By` cláusula. Para obtener más información, consulte [cláusula Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) y [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 En el ejemplo de código siguiente se muestra cómo utilizar el `Median` método para una matriz de tipo `double`.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>La sobrecarga de un método de agregación para que acepte varios tipos  
 Puede sobrecargar el método de agregación para que acepte secuencias de varios tipos. El enfoque estándar es crear una sobrecarga para cada tipo. Otro enfoque consiste en crear una sobrecarga que tomará un tipo genérico y convertirlo a un tipo específico mediante un delegado. También puede combinar ambos enfoques.  
  
#### <a name="to-create-an-overload-for-each-type"></a>Para crear una sobrecarga para cada tipo  
 Puede crear una sobrecarga específica para cada tipo que desea admitir. En el ejemplo de código siguiente se muestra una sobrecarga de la `Median` método para el `integer` tipo.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 Ahora puede llamar a la `Median` sobrecargas para ambos `integer` y `double` tipos, como se muestra en el código siguiente:  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
#### <a name="to-create-a-generic-overload"></a>Para crear una sobrecarga genérica  
 También puede crear una sobrecarga que acepta una secuencia de objetos genéricos. Esta sobrecarga toma a un delegado como parámetro y lo usa para convertir una secuencia de objetos de un tipo genérico en un tipo específico.  
  
 El código siguiente muestra una sobrecarga de la `Median` método que toma el <xref:System.Func%602>delegado como parámetro.</xref:System.Func%602> Este delegado toma un objeto de tipo genérico T y devuelve un objeto del tipo `double`.  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 Ahora puede llamar a la `Median` método para una secuencia de objetos de cualquier tipo. Si el tipo no tiene su propia sobrecarga de método, tiene que pasar un parámetro de delegado. En Visual Basic, puede usar una expresión lambda para este propósito. Además, si utiliza la `Aggregate` o `Group By` cláusula en lugar de la llamada al método, se puede pasar cualquier valor o expresión que está en el ámbito de esta cláusula.  
  
 El ejemplo de código siguiente muestra cómo llamar a la `Median` método para una matriz de enteros y una matriz de cadenas. Para las cadenas, se calcula la media de las longitudes de cadenas en la matriz. En el ejemplo se muestra cómo pasar la <xref:System.Func%602>delegar el parámetro para el `Median` método para cada caso.</xref:System.Func%602>  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
## <a name="adding-a-method-that-returns-a-collection"></a>Agregar un método que devuelve una colección  
 Puede ampliar el <xref:System.Collections.Generic.IEnumerable%601>interfaz con un método de consulta personalizado que devuelve una secuencia de valores.</xref:System.Collections.Generic.IEnumerable%601> En este caso, el método debe devolver una colección de tipo <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> Estos métodos se pueden utilizar para aplicar filtros o transformaciones de datos a una secuencia de valores.  
  
 En el ejemplo siguiente se muestra cómo crear un método de extensión denominado `AlternateElements` que devuelve todos los demás elementos de una colección, empezando por el primer elemento.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 Se puede llamar a este método de extensión para cualquier colección enumerable tal como se llamaría a otros métodos de la <xref:System.Collections.Generic.IEnumerable%601>interfaz, como se muestra en el siguiente código:</xref:System.Collections.Generic.IEnumerable%601>  
  
```vb  
Dim strings() As String = {"a", "b", "c", "d", "e"}  
  
Dim query = strings.AlternateElements()  
  
For Each element In query  
    Console.WriteLine(element)  
Next  
  
' This code produces the following output:  
'  
' a  
' c  
' e  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [Métodos de extensión](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
