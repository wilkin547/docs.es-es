---
title: Errores en códigos declarativos/imperativos mixtos (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: f12b1ab4-bb92-4b92-a648-0525e45b3ce7
ms.openlocfilehash: e5526a64805b19ea293d3ef28636738923d03662
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84361078"
---
# <a name="mixed-declarative-codeimperative-code-bugs-linq-to-xml-visual-basic"></a>Errores de código declarativo/imperativo mixto (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] incluye numerosos métodos que le permiten modificar directamente un árbol XML. Puede agregar elementos, eliminarlos, cambiar sus contenidos, agregar atributos, etc. Esta interfaz de programación se describe en [modificar árboles XML (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md). Si está llevando a cabo una iteración por uno de los ejes, como puede ser <xref:System.Xml.Linq.XContainer.Elements%2A>, y está modificando el árbol XML a medida que recorre el eje, es posible que acabe encontrando errores extraños.  
  
 En ocasiones, a este problema se le conoce como "El problema de Halloween".  
  
## <a name="definition-of-the-problem"></a>Definición del problema  
 Cuando se escribe cierto código utilizando LINQ para iterar por una colección, se utiliza un código de estilo declarativo. Es un método que se aproxima más a definir *qué* es lo que quiere, en vez de especificar *cómo* quiere hacerlo. Si escribe un código que 1) obtenga el primer elemento, 2) lo compruebe con una cierta condición, 3) lo modifique y 4) lo coloque nuevamente en la lista, entonces se trata de un código imperativo. Le está indicando al ordenador *cómo* hacer lo que quiere.  
  
 Si se combinan ambos estilos de código en una misma operación, es cuando aparecen los problemas. Considere el siguiente caso:  
  
 Suponga que tiene una lista vinculada que contiene tres elementos (a, b y c):  
  
 `a -> b -> c`  
  
 Ahora, suponga que desea recorrer la lista vinculada y añadir tres nuevos elementos (a', b' y c'). Desea que la lista vinculada resultante tenga el siguiente aspecto:  
  
 `a -> a' -> b -> b' -> c -> c'`  
  
 De forma que escribe un código que recorre la lista y, que para cada elemento, añade uno nuevo justo después. Lo que ocurrirá es que el código encontrará primero el elemento `a` e insertará `a'` justo después. Ahora, el código pasará al siguiente nodo de la lista, que en este momento será `a'` Entonces agregará un nuevo elemento a la lista, `a''`.  
  
 ¿Cómo se puede resolver esto en un caso real? Una opción es realizar una copia de la lista vinculada original y crear una lista completamente nueva. O bien, si únicamente está escribiendo un código imperativo, puede encontrar el primer elemento, añadir el nuevo y, a continuación, avanzar dos elementos en la lista, pasando así por encima del elemento recién agregado.  
  
## <a name="adding-while-iterating"></a>Agregar a medida que se va iterando  
 Suponga, por ejemplo, que desea escribir un cierto código que, para cada elemento de un árbol, cree un elemento duplicado:  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements()  
    root.Add(New XElement(e.Name, e.Value))  
Next  
```  
  
 Este código entrará en un bucle infinito. La instrucción `foreach` lleva a cabo una iteración a lo largo del eje `Elements()`, agregando nuevos elementos al elemento `doc`. Al final, acaba realizando dicha iteración por los elementos que se acaban de agregar. Y, dado que coloca los nuevos objetos en cada una de las iteraciones del bucle, llegará un momento en el que consuma toda la memoria disponible.  
  
 Puede resolver este problema almacenando en memoria la colección mediante el operador de consulta estándar <xref:System.Linq.Enumerable.ToList%2A>, de la siguiente forma:  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements().ToList()  
    root.Add(New XElement(e.Name, e.Value))  
Next  
Console.WriteLine(root)  
```  
  
 Ahora el código funciona correctamente. El árbol XML resultante es como sigue:  
  
```xml  
<Root>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
## <a name="deleting-while-iterating"></a>Eliminar a medida que se va iterando  
 Si desea eliminar todos los nodos que se encuentren en un cierto nivel, podría tener la tentación de escribir un código como el que sigue:  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements()  
    e.Remove()  
Next  
Console.WriteLine(root)  
```  
  
 Sin embargo, no realiza la tarea que deseaba. En esta situación, tras eliminar el primer elemento (A), éste se elimina del árbol XML contenido en la raíz, con lo que el código del método Elements encargado de la iteración no podrá encontrar el siguiente elemento.  
  
 Este código anterior genera el siguiente resultado:  
  
```xml  
<Root>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
 De nuevo, la solución pasa por llamar a <xref:System.Linq.Enumerable.ToList%2A> para materializar la colección, de la siguiente forma:  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements().ToList()  
    e.Remove()  
Next  
Console.WriteLine(root)  
```  
  
 Esto genera el siguiente resultado:  
  
```xml  
<Root />  
```  
  
 Como alternativa, puede eliminar la iteración entera llamando a <xref:System.Xml.Linq.XElement.RemoveAll%2A> en el elemento primario:  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
root.RemoveAll()  
Console.WriteLine(root)  
```  
  
## <a name="why-cant-linq-automatically-handle-this"></a>¿Por qué LINQ no puede controlar este comportamiento?  
 Una posible aproximación sería trasladar todo a memoria en vez de realizar evaluaciones diferidas. No obstante, esto resultaría muy costoso en términos de rendimiento y de utilización de la memoria. De hecho, si LINQ y (LINQ to XML) utilizaran este método, no sería viable en situaciones reales.  
  
 Otra posible aproximación consiste en utilizar una cierta sintaxis transaccional en LINQ y hacer que el compilador intente analizar el código para determinar si es necesario materializar alguna colección en particular. Sin embargo, puede resultar extremadamente complejo analizar todo el código que pueda tener efectos secundarios. Observe el código siguiente:  
  
```vb  
Dim z = _  
    From e In root.Elements() _  
    Where (TestSomeCondition(e)) _  
    Select DoMyProjection(e)  
```  
  
 Un código de análisis así necesitaría analizar los métodos TestSomeCondition y DoMyProjection, así como todos los métodos a los que llaman, con el fin de determinar si existe código con efectos secundarios. Pero no bastaría con que el código de análisis buscara código que tuviera efectos secundarios. Solo debería seleccionar aquel código que tuviera efectos secundarios sobre los elementos secundarios de `root` en este caso en particular.  
  
 LINQ to XML no realiza ese tipo de análisis.  
  
 Es responsabilidad del programador evitar este tipo de problemas.  
  
## <a name="guidance"></a>Orientación  
 Primeramente, no mezcle código imperativo con código declarativo.  
  
 Incluso en el caso de que conozca con precisión la semántica de las colecciones y de los métodos que modifican el árbol XML y escriba un código que evite este tipo de problemas, éste deberá ser mantenido por otros desarrolladores en un futuro, y es posible que éstos no estén al tanto de esos problemas. Si mezcla estilos de programación declarativa e imperativa, el código resultará más complicado.  
  
 Si escribe código que materialice una colección de forma que se eviten todos estos problemas, incluya en él comentarios de forma que los programadores encargados de su mantenimiento puedan comprender la problemática.  
  
 En segundo lugar, si el rendimiento y otras consideraciones lo permiten, utilice únicamente código declarativo. No modifique el árbol XML existente. Genere uno nuevo.  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
Dim newRoot As XElement = New XElement("Root", _  
    root.Elements(), root.Elements())  
Console.WriteLine(newRoot)  
```  
  
## <a name="see-also"></a>Consulte también

- [Programación de LINQ to XML avanzada (Visual Basic)](advanced-linq-to-xml-programming.md)
