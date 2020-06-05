---
title: Diferencias entre la modificación del árbol XML en memoria y Construcción funcional (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: d91c4ebf-6549-43cc-9961-26d4a82f722b
ms.openlocfilehash: efdbf51efa0f502ac9991d520defe45bb95678b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397614"
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml-visual-basic"></a>Modificación del árbol XML en memoria frente a la construcción funcional (LINQ to XML) (Visual Basic)
Modificar un árbol XML directamente es un enfoque tradicional para cambiar la forma de un documento XML. Una aplicación típica carga un documento en un almacén de datos como DOM o [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]; utiliza una interfaz de programación para insertar nodos, eliminar nodos o cambiar el contenido de los nodos y, a continuación, guarda el XML en un archivo o lo transmite a través de una red.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]habilita otro enfoque que es útil en muchos escenarios *: construcción funcional*. La construcción funcional trata la modificación de datos como un problema de transformación en lugar de una manipulación detallada de un almacén de datos. Si puede tomar una representación de datos y transformarla eficientemente de una a otra, el resultado es el mismo que si ha tomado un almacén de datos y lo ha manipulado de alguna manera para que tome otra forma. Un aspecto fundamental del enfoque de construcción funcional es pasar los resultados de las consultas a los constructores <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>.  
  
 En muchos casos puede escribir el código de transformación en una fracción del tiempo que tardaría en manipular el almacén de datos y ese código es más eficaz y fácil de mantener. En esos casos, aunque el enfoque de transformación puede necesitar más potencia de procesamiento, es una forma más efectiva de modificar datos. Si un desarrollador está familiarizado con el enfoque funcional, el código resultante es en muchos casos más fácil de entender. Resulta sencillo buscar el código que modifica cada parte del árbol.  
  
 El enfoque en el que se modifica un árbol XML directamente es mucho más familiar para muchos programadores de DOM, mientras que el código escrito usando el enfoque funcional puede ser poco familiar para un desarrollador que aún no comprende este enfoque. Si solo tiene que realizar una pequeña modificación en un árbol XML grande, el enfoque en el que se modifica un árbol directamente en muchos casos consumirá menos tiempo de CPU.  
  
 Este tema proporciona un ejemplo que se implementa con ambos enfoques.  
  
## <a name="transforming-attributes-into-elements"></a>Transformar atributos en elementos  
 Para este ejemplo, supongamos que desea modificar el siguiente documento XML sencillo para que los atributos se conviertan en elementos. Este tema primero presenta el enfoque tradicional de modificación directa. Después muestra el enfoque de construcción funcional.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root Data1="123" Data2="456">  
  <Child1>Content</Child1>  
</Root>  
```  
  
### <a name="modifying-the-xml-tree"></a>Modificar el árbol XML  
 Puede escribir código de procedimientos para crear elementos a partir de atributos y después eliminar los atributos de la siguiente manera:  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
For Each att As XAttribute In root.Attributes()  
    root.Add(New XElement(att.Name, att.Value))  
Next  
root.Attributes().Remove()  
Console.WriteLine(root)  
```  
  
 Este código genera el siguiente resultado:  
  
```xml  
<Root>  
  <Child1>Content</Child1>  
  <Data1>123</Data1>  
  <Data2>456</Data2>  
</Root>  
```  
  
### <a name="functional-construction-approach"></a>Enfoque de construcción funcional  
 Por el contrario, un enfoque funcional consta de un código para formar un nuevo árbol, eligiendo y seleccionando elementos y atributos del árbol de origen y transformándolos, según convenga, a medida que se agregan al nuevo árbol. El enfoque funcional tiene el siguiente aspecto:  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim newTree As XElement = _  
    <Root>  
        <%= root.<Child1> %>  
        <%= From att In root.Attributes() _  
            Select New XElement(att.Name, att.Value) %>  
    </Root>  
Console.WriteLine(newTree)  
```  
  
 Este ejemplo produce el mismo XML que el primer ejemplo. No obstante, tenga en cuenta que puede ver realmente la estructura resultante del nuevo XML en el enfoque funcional. Puede ver la creación del elemento `Root`, el código que extrae el elemento `Child1` del árbol de origen y el código que transforma los atributos del árbol de origen a los elementos del nuevo árbol.  
  
 El ejemplo funcional de este caso no es más corto que el primer ejemplo y en realidad no es más sencillo. No obstante, si tiene muchos cambios que realizar a un árbol XML, el enfoque no funcional se hará más complejo y difícil de entender. Por el contrario, cuando se usa el enfoque funcional, se sigue formando el XML deseado, incrustando consultas y expresiones según convenga, para extraer el contenido deseado. El enfoque funcional produce código que es más fácil de mantener.  
  
 Tenga en cuenta que el enfoque funcional probablemente no tendrá un rendimiento tan bueno como la manipulación del árbol. El principal problema es que el enfoque funcional crea objetos de corta duración. No obstante, la compensación es efectiva si el uso del enfoque funcional permite una mayor productividad del programador.  
  
 Éste es un ejemplo muy sencillo, pero sirve para mostrar la diferencia de filosofía entre los dos enfoques. El enfoque funcional ofrece mayores ganancias de productividad para transformar documentos XML de gran tamaño.  
  
## <a name="see-also"></a>Consulte también

- [Modificar árboles XML (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md)
