---
title: Streaming de fragmentos XML desde un objeto XmlReader (C#)
ms.date: 07/20/2015
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
ms.openlocfilehash: f7914d33622518f983a685dd2e844a25fd3ca15f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714652"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a>Streaming de fragmentos XML desde un objeto XmlReader (C#)

Cuando deba procesar archivos XML grandes quizás no sea factible cargar la totalidad del árbol XML en memoria. En este tema se muestra cómo transmitir por secuencias fragmentos usando <xref:System.Xml.XmlReader>.  
  
 Una de las formas más efectivas de usar <xref:System.Xml.XmlReader> para leer objetos <xref:System.Xml.Linq.XElement> es escribir un método de eje personalizado propio. Un método de eje suele devolver una recopilación como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, tal y como se muestra en el ejemplo de este tema. En el método de eje personalizado, tras crear el fragmento XML llamando al método <xref:System.Xml.Linq.XNode.ReadFrom%2A>, devuelva la recopilación usando `yield return`. Esto proporciona semántica de ejecución aplazada al método de eje personalizado.  
  
 Cuando crea un árbol XML de un objeto <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> debe estar posicionado en un elemento. El método <xref:System.Xml.Linq.XNode.ReadFrom%2A> no vuelve hasta que ha leído la etiqueta de cierre del elemento.  
  
 Si desea crear un árbol parcial, puede crear una instancia de un <xref:System.Xml.XmlReader>, colocar el lector en el nodo que desea convertir a un árbol <xref:System.Xml.Linq.XElement> y después crear el objeto <xref:System.Xml.Linq.XElement>.  
  
El tema [Procedimiento para hacer streaming de fragmentos XML con acceso a la información del encabezado (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) contiene información y un ejemplo sobre cómo hacer streaming de un documento más complejo.
  
 El tema [Procedimiento para realizar una transformación de streaming de documentos XML grandes (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un ejemplo del uso de LINQ to XML para transformar documentos XML extremadamente grandes manteniendo una superficie de memoria pequeña.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo crea un método de eje personalizado. Puede consultarlo usando una consulta de LINQ. El método de eje personalizado, `StreamRootChildDoc`, es un método que está específicamente diseñado para leer un documento que tiene un elemento `Child` que se repite.  
  
```csharp  
static IEnumerable<XElement> StreamRootChildDoc(StringReader stringReader)  
{  
    using (XmlReader reader = XmlReader.Create(stringReader))  
    {  
        reader.MoveToContent();  
        // Parse the file and display each of the nodes.  
        while (reader.Read())  
        {  
            switch (reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    if (reader.Name == "Child") {  
                        XElement el = XElement.ReadFrom(reader) as XElement;  
                        if (el != null)  
                            yield return el;  
                    }  
                    break;  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    string markup = @"<Root>  
      <Child Key=""01"">  
        <GrandChild>aaa</GrandChild>  
      </Child>  
      <Child Key=""02"">  
        <GrandChild>bbb</GrandChild>  
      </Child>  
      <Child Key=""03"">  
        <GrandChild>ccc</GrandChild>  
      </Child>  
    </Root>";  
  
    IEnumerable<string> grandChildData =  
        from el in StreamRootChildDoc(new StringReader(markup))  
        where (int)el.Attribute("Key") > 1  
        select (string)el.Element("GrandChild");  
  
    foreach (string str in grandChildData) {  
        Console.WriteLine(str);  
    }  
}  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
bbb  
ccc  
```  
  
 En este ejemplo el documento de origen es muy pequeño. No obstante, aunque hubiera millones de elementos `Child`, este ejemplo seguiría teniendo una superficie de memoria pequeña.  
