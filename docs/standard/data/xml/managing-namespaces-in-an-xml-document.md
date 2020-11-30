---
title: Administrar espacios de nombres en un documento XML
description: Aprenda a administrar espacios de nombres en un documento XML. Los espacios de nombres XML asocian nombres de elementos y de atributos de un documento XML con identificadores URI personalizados y predefinidos.
ms.date: 03/30/2017
ms.assetid: 682643fc-b848-4e42-8c0d-50deeaeb5f2a
ms.openlocfilehash: 120493de430c2372f3f71d1d1498ba880feda3d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720157"
---
# <a name="managing-namespaces-in-an-xml-document"></a>Administrar espacios de nombres en un documento XML

Los espacios de nombres XML asocian nombres de elementos y de atributos de un documento XML con identificadores URI personalizados y predefinidos. Para crear estas asociaciones, puede definir los prefijos de los URI del espacio de nombres y usar dichos prefijos para calificar los nombres de los elementos y de los atributos en los datos XML. Los espacios de nombres evitan conflictos de nombres de elementos y atributos y permiten que los elementos y atributos con el mismo nombre se traten y se validen de forma diferente.  
  
<a name="declare"></a>

## <a name="declaring-namespaces"></a>Declarar espacios de nombres  

 Para declarar un espacio de nombres en un elemento, puede usar el atributo `xmlns:`:  
  
 `xmlns:<name>=<"uri">`  
  
 Donde `<name>` es el prefijo de espacio de nombres y `<"uri">` es el URI que identifica el espacio de nombres. Después de declarar el prefijo, puede usarlo para calificar elementos y atributos de un documento XML y asociarlos al identificador URI del espacio de nombres. Como el prefijo de espacio de nombres se utiliza en todo el documento, debe ser corto.  
  
 Este ejemplo define dos elementos `BOOK`. El primer elemento se califica mediante el prefijo del espacio de nombres `mybook` y el segundo elemento se califica con el prefijo `bb`. Cada prefijo se asocia a un URI del espacio de nombres distinto:  
  
```xml  
<mybook:BOOK xmlns:mybook="http://www.contoso.com/books.dtd">  
<bb:BOOK xmlns:bb="urn:blueyonderairlines" />
</mybook>
```  
  
 Para indicar que un elemento es parte de un espacio de nombres en particular, agréguele el prefijo de espacio de nombres. Por ejemplo, si el elemento `Author` pertenece al espacio de nombres `mybook`, se declara como `<mybook:Author>`.  
  
<a name="scope"></a>

## <a name="declaration-scope"></a>Ámbito de la declaración  

 Un espacio de nombres es efectivo desde el momento de su declaración hasta el fin del elemento en el que se ha declarado. En este ejemplo, el espacio de nombres definido en el elemento `BOOK` no se aplica a elementos que estén fuera del elemento `BOOK`, tales como el elemento `Publisher`:  
  
```xml  
<Author>Joe Smith</Author>  
<BOOK xmlns:book="http://www.contoso.com">  
    <title>My Wonderful Day</title>  
      <price>$3.95</price>  
</BOOK>  
<Publisher>  
    <Name>MSPress</Name>  
</Publisher>  
```  
  
 Para usar un espacio de nombres, antes éste se debe declarar, pero no tiene que aparecer al principio del documento XML.  
  
 Si se usan varios espacios de nombres en un documento XML, puede definir un espacio de nombres como predeterminado para crear un documento en el que se mejora la claridad. El espacio de nombres predeterminado se declara en el elemento raíz y se aplica a todos los elementos sin calificar del documento. Los espacios de nombres predeterminados solo se aplican a los elementos, no a los atributos.  
  
 Para usar el espacio de nombres predeterminado, omita el prefijo y los dos puntos de la declaración en el elemento:  
  
```xml  
<BOOK xmlns="http://www.contoso.com/books.dtd">  
...
</BOOK>
```  
  
## <a name="managing-namespaces"></a>Administrar los espacios de nombres  

 La clase <xref:System.Xml.XmlNamespaceManager> almacena una colección de URI del espacio de nombres y sus prefijos y permite buscar, agregar y quitar los espacios de nombres en esta colección. En determinados contextos, esta clase es necesaria para obtener un mejor rendimiento del procesamiento XML. Por ejemplo, la clase <xref:System.Xml.Xsl.XsltContext> usa <xref:System.Xml.XmlNamespaceManager> para la compatibilidad con XPath.  
  
 El administrador de espacios de nombres no realiza ninguna validación en los espacios de nombres, pero asume que ya se han comprobado los prefijos y los espacios de nombres y son compatibles con la especificación de [espacios de nombres de W3C](https://www.w3.org/TR/REC-xml-names/).  
  
> [!NOTE]
> LINQ to XML en [C#](../../linq/linq-xml-overview.md) y [Visual Basic](../../linq/linq-xml-overview.md) no utilizan <xref:System.Xml.XmlNamespaceManager> para administrar espacios de nombres. Vea [Working with XML Namespaces (C#)](../../linq/namespaces-overview.md) (Trabajo con espacios de nombres XML [C#]) y [Working with XML Namespaces (Visual Basic)](../../linq/namespaces-overview.md) (Trabajo con espacios de nombres XML [Visual Basic]) en la documentación de LINQ para obtener información sobre cómo administrar los espacios de nombres al usar LINQ to XML.  
  
 A continuación se detallan algunas de las tareas de administración y búsqueda que puede realizar con la clase <xref:System.Xml.XmlNamespaceManager>. Para obtener más información y ejemplos, siga los vínculos a la página de referencia para cada método o propiedad.  
  
|En|Usar|  
|--------|---------|  
|Agregar un espacio de nombres|Método <xref:System.Xml.XmlNamespaceManager.AddNamespace%2A>|  
|Eliminar un espacio de nombres|Método <xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A>|  
|Encontrar el URI del espacio de nombres predeterminado|Propiedad<xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A>|  
|Encontrar el URI de un prefijo de espacio de nombres|Método <xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A>|  
|Encontrar el prefijo de un URI del espacio de nombres|Método <xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A>|  
|Obtener una lista de espacios de nombres del nodo actual|Método <xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A>|  
|Asignar un ámbito a un espacio de nombres|Métodos <xref:System.Xml.XmlNamespaceManager.PushScope%2A> y <xref:System.Xml.XmlNamespaceManager.PopScope%2A>|  
|Comprobar si un prefijo está definido en el ámbito actual|Método <xref:System.Xml.XmlNamespaceManager.HasNamespace%2A>|  
|Obtener la tabla de nombres usada para buscar prefijos e identificadores URI|Propiedad<xref:System.Xml.XmlNamespaceManager.NameTable%2A>|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlNamespaceManager>
- [Documentos y datos XML](index.md)
