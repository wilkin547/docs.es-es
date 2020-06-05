---
title: Procedimiento para usar anotaciones para transformar árboles LINQ to XML en un estilo XSLT
ms.date: 07/20/2015
ms.assetid: 08e91fa2-dac2-4463-9ef1-87b1ac3fa890
ms.openlocfilehash: 099457eaab8c80605138d7e67d7bc2823e316234
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364453"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-visual-basic"></a>Cómo: utilizar anotaciones para transformar LINQ to XML árboles en un estilo XSLT (Visual Basic)

Se puede usar anotaciones para facilitar transformaciones de un árbol XML.

Algunos documentos XML están "basados en el documento con contenido mixto". Con estos documentos no se conoce necesariamente la forma de los nodos secundarios de un elemento. Por ejemplo, un nodo que contiene texto puede tener el siguiente aspecto:

```xml
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>
```

Para cualquier nodo de texto dado puede haber cualquier número de elementos secundarios `<b>` y `<i>`. Este enfoque se extiende a otras situaciones: por ejemplo, las páginas que pueden contener varios elementos secundarios, como párrafos normales, párrafos con viñetas y mapas de bits. Las celdas de una tabla pueden contener texto, listas desplegables o mapas de bits. Una de las características principal del XML centrado en documentos es que no se sabe qué elemento secundario puede tener cualquier elemento particular.

Si desea transformar elementos de un árbol en el que no conoce el elemento secundario de los elementos que desea transformar, entonces este enfoque que usa anotaciones en un enfoque efectivo.

El resumen del enfoque es:

- En primer lugar, anote elementos en el árbol con un elemento de sustitución.

- En segundo lugar, recorra en iteración todo el árbol, creando un nuevo árbol en el que se reemplaza cada elemento son su anotación. Este ejemplo implementa la iteración y la creación de un nuevo árbol en una función con el nombre `XForm`.

En detalle, el enfoque consiste en:

- Ejecutar una o más consultas LINQ to XML que devuelvan el conjunto de elementos que desea transformar de una forma a otra. Para cada elemento de la consulta, agregue un nuevo objeto <xref:System.Xml.Linq.XElement> como anotación al elemento. Este nuevo elemento sustituirá el elemento anotado en el nuevo árbol transformado. Es un código sencillo de escribir, tal como lo demuestra el ejemplo.

- El nuevo elemento que se agrega como anotación puede contener nodos secundarios; puede formar un subárbol con cualquier forma que se desee.

- Existe una regla especial; si un nodo secundario del nuevo elemento está en un espacio de nombres diferente, un espacio de nombres creado con esa finalidad (en este ejemplo, el espacio de nombres es `http://www.microsoft.com/LinqToXmlTransform/2007`), entonces el elemento secundario no se copia al nuevo árbol. En su lugar, si el espacio de nombres es el espacio de nombres especial mencionado anteriormente y el nombre local del elemento es `ApplyTransforms`, los nodos secundarios del elemento del árbol de origen se recorren en iteración y se copian al nuevo árbol (con la excepción que los elementos secundarios anotados se transforman de acuerdo con esas reglas).

- Esto es parecido a la especificación de transformaciones en XSL. La consulta que selecciona un conjunto de nodos es análoga a la expresión XPath para una plantilla. El código para crear el nuevo <xref:System.Xml.Linq.XElement> que se guarda como anotación es análogo al constructor de secuencias en XSL y el elemento `ApplyTransforms` es análogo en función al elemento `xsl:apply-templates` en XSL.

- Una ventaja de este enfoque es que al formular consultas siempre se escriben consultas en el árbol de origen sin modificar. No hay que preocuparse de cómo afectan a las consultas que se están escribiendo las modificaciones del árbol.

## <a name="transforming-a-tree"></a>Transformar un árbol

En este primer ejemplo se cambia el nombre de todos los `Paragraph` nodos a `para` :

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim root As XElement = _
            <Root>
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>
                <Paragraph>More text.</Paragraph>
            </Root>

        ' Replace Paragraph with p.
        For Each el In root...<Paragraph>
            ' same idea as xsl:apply-templates
            el.AddAnnotation( _
                <para>
                    <<%= at %>></>
                </para>)
        Next

        ' The XForm function, shown later in this topic, accomplishes the transform
        Dim newRoot As XElement = XForm(root)
        Console.WriteLine(newRoot)
    End Sub
End Module
```

 Este ejemplo produce el siguiente resultado:

```xml
<Root>
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>
  <para>More text.</para>
</Root>
```

## <a name="a-more-complicated-transform"></a>Una transformación más complicada

El siguiente ejemplo consulta el árbol y calcula la media y la suma de los elementos `Data` y los agrega como nuevos elementos al árbol.

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim data As XElement = _
            <Root>
                <Data>20</Data>
                <Data>10</Data>
                <Data>3</Data>
            </Root>

        ' While adding annotations, you can query the source tree all you want,
        ' as the tree is not mutated while annotating.
        data.AddAnnotation( _
            <Root>
                <<%= at %>/>
                <Average>
                    <%= _
                        String.Format("{0:F4}", _
                        data.Elements("Data") _
                        .Select(Function(z) CDec(z)).Average()) _
                    %>
                </Average>
                <Sum>
                    <%= _
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _
                    %>
                </Sum>
            </Root> _
        )

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(data)
        Console.WriteLine(vbNewLine)

        ' The XForm function, shown later in this topic, accomplishes the transform
        Dim newData As XElement = XForm(data)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newData)
    End Sub
End Module
```

Este ejemplo produce el siguiente resultado:

```console
Before Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
</Root>

After Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
  <Average>11.0000</Average>
  <Sum>33</Sum>
</Root>
```

## <a name="effecting-the-transform"></a>Efecto de la transformación

Una pequeña función, `XForm`, crea un nuevo árbol transformado a partir del árbol original anotado.

El pseudocódigo para la función es bastante sencillo:

> La función toma un XElement como argumento y devuelve un XElement.
>
> Si un elemento tiene una anotación XElement, devuelve un nuevo XElement:
>
> - El nombre del nuevo XElement es el nombre del elemento de anotación.
> - Todos los atributos se copian de la anotación al nuevo nodo.
> - Todos los nodos secundarios se copian de la anotación, con la excepción de que se reconoce el nodo especial XF: ApplyTransforms y se recorren en iteración los nodos secundarios del elemento de origen. Si el nodo secundario de origen no es un XElement, se copia en el nuevo árbol. Si el elemento secundario de origen es un XElement, se transforma llamando a esta función de forma recursiva.
>
> Si un elemento no está anotado:
>
> - Devolver un nuevo XElement
>   - El nombre del nuevo XElement es el nombre del elemento de origen.
>   - Todos los atributos se copian del elemento de origen al elemento del destino.
>   - Todos los nodos secundarios se copian del elemento de origen.
>   - Si el nodo secundario de origen no es un XElement, se copia en el nuevo árbol. Si el elemento secundario de origen es un XElement, se transforma llamando a esta función de forma recursiva.

El código siguiente es la implementación de esta función:

```vb
' Build a transformed XML tree per the annotations.
Function XForm(ByVal source As XElement) As XElement
    If source.Annotation(Of XElement)() IsNot Nothing Then
        Dim anno As XElement = source.Annotation(Of XElement)()
        Return _
            <<%= anno.Name.ToString() %>>
                <%= anno.Attributes() %>
                <%= anno.Nodes().Select(Function(n As XNode) _
                    GetSubNodes(n, source)) %>
            </>
    Else
        Return _
            <<%= source.Name %>>
                <%= source.Attributes() %>
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
            </>
    End If
End Function

Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
    Dim annoEl As XElement = TryCast(n, XElement)
    If annoEl IsNot Nothing Then
        If annoEl.Name = at Then
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
        End If
    End If
    Return n
End Function

Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
    Dim e2 As XElement = TryCast(n2, XElement)
    If e2 Is Nothing Then
        Return n2
    Else
        Return XForm(e2)
    End If
End Function
```

## <a name="complete-example"></a>Ejemplo completo

El siguiente código es un ejemplo completo que incluye la función `XForm`. Incluye unos pocos usos típicos de este tipo de transformación:

```vb
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports System.Xml
Imports System.Xml.Linq

Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    ' Build a transformed XML tree per the annotations.
    Function XForm(ByVal source As XElement) As XElement
        If source.Annotation(Of XElement)() IsNot Nothing Then
            Dim anno As XElement = source.Annotation(Of XElement)()
            Return _
                <<%= anno.Name.ToString() %>>
                    <%= anno.Attributes() %>
                    <%= anno.Nodes().Select(Function(n As XNode) _
                        GetSubNodes(n, source)) %>
                </>
        Else
            Return _
                <<%= source.Name %>>
                    <%= source.Attributes() %>
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
                </>
        End If
    End Function

    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
        Dim annoEl As XElement = TryCast(n, XElement)
        If annoEl IsNot Nothing Then
            If annoEl.Name = at Then
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
            End If
        End If
        Return n
    End Function

    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
        Dim e2 As XElement = TryCast(n2, XElement)
        If e2 Is Nothing Then
            Return n2
        Else
            Return XForm(e2)
        End If
    End Function

    Sub Main()
        Dim root As XElement = _
<Root Att1='123'>
    <!--A comment-->
    <Child>1</Child>
    <Child>2</Child>
    <Other>
        <GC>3</GC>
        <GC>4</GC>
    </Other>
    <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
    <AnUnchangedElement>42</AnUnchangedElement>
</Root>

        ' Each of the following serves the same semantic purpose as
        ' XSLT templates and sequence constructors.

        ' Replace Child with NewChild.
        For Each el In root.<Child>
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)
        Next

        ' Replace first GC with GrandChild, add an attribute.
        For Each el In root...<GC>.Take(1)
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)
        Next

        ' Replace Other with NewOther, add new child elements around original content.
        For Each el In root.<Other>
            el.AddAnnotation( _
                <NewOther>
                    <MyNewChild>1</MyNewChild>
                    <<%= at %>></>
                    <ChildThatComesAfter/>
                </NewOther>)
        Next

        ' Change name of element that has mixed content.
        root...<SomeMixedContent>(0).AddAnnotation( _
                <MixedContent><<%= at %>></></MixedContent>)

        ' Replace <b> with <Bold>.
        For Each el In root...<b>
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)
        Next

        ' Replace <i> with <Italic>.
        For Each el In root...<i>
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)
        Next

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(root)
        Console.WriteLine(vbNewLine)
        Dim newRoot As XElement = XForm(root)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newRoot)
    End Sub
End Module
```

Este ejemplo produce el siguiente resultado:

```console
Before Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <Child>1</Child>
  <Child>2</Child>
  <Other>
    <GC>3</GC>
    <GC>4</GC>
  </Other>
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>

After Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <NewChild>1</NewChild>
  <NewChild>2</NewChild>
  <NewOther>
    <MyNewChild>1</MyNewChild>
    <GrandChild ANewAttribute="999">3</GrandChild>
    <GC>4</GC>
    <ChildThatComesAfter />
  </NewOther>
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>
```

## <a name="see-also"></a>Vea también

- [Programación de LINQ to XML avanzada (Visual Basic)](advanced-linq-to-xml-programming.md)
