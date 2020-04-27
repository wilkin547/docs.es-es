---
title: Navegación por nodos de espacios de nombres y atributos con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 23975f88-e0af-4b88-93de-9e20e11880ad
ms.openlocfilehash: 6809a2a47a9ca25a16a9be75a0a8a8b03f98a21d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711160"
---
# <a name="attribute-and-namespace-node-navigation-using-xpathnavigator"></a>Navegación por nodos de espacios de nombres y atributos con XPathNavigator
La clase <xref:System.Xml.XPath.XPathNavigator> incluye dos conjuntos de métodos de navegación. El primero, que se encuentra en el tema [Navegación por un conjunto de nodos con XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), se utiliza para navegar por *conjuntos de nodos* en un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>. El segundo, que se describe en este tema, se utiliza para navegar por *nodos de espacios de nombres y atributos* en un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.  
  
## <a name="attribute-node-navigation"></a>Navegación por nodos de atributos  
 Los atributos son propiedades de un elemento, no elementos secundarios de un elemento. Esta distinción es importante debido a los métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que se utilizan para navegar por los nodos secundarios, principales y relacionados.  
  
 Por ejemplo, los métodos <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> no se utilizan para navegar de un elemento a un atributo, ni entre atributos. En su lugar, los atributos tienen métodos de navegación distintos.  
  
 A continuación, se enumeran métodos de navegación por atributos de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNextAttribute%2A>  
  
 Cuando el nodo actual es un elemento, utilice la propiedad <xref:System.Xml.XPath.XPathNavigator.HasAttributes%2A> para ver si hay algún atributo asociado a dicho elemento. Una vez que se sabe que un elemento tiene atributos, existen varios métodos de acceso a atributos. Para recuperar un solo atributo del elemento, utilice el método <xref:System.Xml.XPath.XPathNavigator.GetAttribute%2A>. Para mover <xref:System.Xml.XPath.XPathNavigator> a un atributo concreto, utilice el método <xref:System.Xml.XPath.XPathNavigator.MoveToAttribute%2A>. También puede iterar por cada atributo de un elemento utilizando el método <xref:System.Xml.XPath.XPathNavigator.MoveToFirstAttribute%2A> y, a continuación, realizando varias llamadas al método <xref:System.Xml.XPath.XPathNavigator.MoveToNextAttribute%2A>.  
  
> [!NOTE]
> Cuando el objeto <xref:System.Xml.XPath.XPathNavigator> se encuentra en un nodo de tipo atributo o espacio de nombres, los métodos <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> siempre devolverán `false`, y no afectarán a la posición del <xref:System.Xml.XPath.XPathNavigator>. Las excepciones son los métodos <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>.  
  
## <a name="namespace-node-navigation"></a>Navegación por nodos de espacios de nombres  
 Cada elemento tiene un conjunto de nodos de espacios de nombres asociado, uno para cada prefijo de espacio de nombres distinto que esté ligado a un identificador URI de espacio de nombres en el ámbito del elemento (incluido el prefijo XML ligado al espacio de nombres `http://www.w3.org/XML/1998/namespace`, que se declara de forma implícita en cada documento XML) y uno para el espacio de nombres predeterminado si hay uno en el ámbito del elemento. El elemento es el principal de cada uno de estos nodos de espacio de nombres; sin embargo, un nodo de espacio de nombres no es un elemento secundario de su elemento principal.  
  
 Al igual que en los atributos, los métodos <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> no se utilizan para navegar de un nodo de elementos a un nodo de espacio de nombres, ni entre nodos de espacios de nombres. En su lugar, los nodos de espacios de nombres tienen métodos de navegación distintos.  
  
 A continuación, se enumeran los métodos de navegación por espacios de nombres de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNamespace%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>  
  
 Siempre hay al menos un nodo de espacios de nombres para cualquier elemento de un documento XML. Éste es el nodo de espacios de nombres con el prefijo `xml` y el identificador URI de espacio de nombres `http://www.w3.org/XML/1998/namespace`. Para recuperar un identificador URI de espacio de nombres dado un prefijo concreto, utilice el método <xref:System.Xml.XPath.XPathNavigator.GetNamespace%2A>. Para mover el objeto <xref:System.Xml.XPath.XPathNavigator> a un nodo de espacios de nombres en particular, utilice el método <xref:System.Xml.XPath.XPathNavigator.MoveToNamespace%2A>. También puede iterar por cada nodo de espacios de nombres del ámbito de un elemento utilizando el método <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> y, a continuación, realizando varias llamadas al método <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>.  
  
> [!NOTE]
> Cuando el objeto <xref:System.Xml.XPath.XPathNavigator> se encuentra en un nodo de tipo atributo o espacio de nombres, los métodos <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> siempre devolverán `false`, y no afectarán a la posición del <xref:System.Xml.XPath.XPathNavigator>. Las excepciones son los métodos <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>.  
  
### <a name="the-xpathnamespacescope-enumeration"></a>Enumeración XPathNamespaceScope  
 Al navegar por nodos de espacios de nombres, es posible llamar a los métodos <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> con un parámetro <xref:System.Xml.XPath.XPathNamespaceScope>. Estos métodos se comportan de forma diferente a sus equivalentes que se llaman sin ningún parámetro. La enumeración <xref:System.Xml.XPath.XPathNamespaceScope> tiene valores de <xref:System.Xml.XPath.XPathNamespaceScope.All>, <xref:System.Xml.XPath.XPathNamespaceScope.ExcludeXml> o <xref:System.Xml.XPath.XPathNamespaceScope.Local>.  
  
 Los siguientes ejemplos muestran qué espacios de nombres devuelven los métodos <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> en diversos ámbitos de un documento XML.  
  
```xml  
<root>  
    <element1 xmlns="http://www.contoso.com" xmlns:books="http://www.contoso.com/books">  
        <element2 />  
    </element1>  
</root>  
```  
  
 Ésta es la secuencia de espacios de nombres (el espacio de nombres en el que está situado <xref:System.Xml.XPath.XPathNavigator> después de llamar al método <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> y realizar, a continuación, una serie de llamadas al método <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>).  
  
- Cuando está situado en `element2`: `xmlns:books="http://www.contoso.com/books"`, `xmlns="http://www.contoso.com"` y `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- Cuando está situado en `element1`: `xmlns:books="http://www.contoso.com/books"`, `xmlns="http://www.contoso.com"` y `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- Cuando está situado en `root`: `xmlns:xml="http://www.w3.org/XML/1998/namespace".`  
  
> [!NOTE]
> La clase <xref:System.Xml.XPath.XPathNavigator> devuelve nodos de espacios de nombres en el orden inverso del documento. Por lo tanto, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> se desplaza básicamente al último nodo de espacios de nombres del ámbito actual.  
  
 Los siguientes ejemplos muestran qué espacios de nombres devuelven los métodos <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> y <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A> con la enumeración <xref:System.Xml.XPath.XPathNamespaceScope> especificada en diversos ámbitos de un documento XML.  
  
```xml  
<root xmlns="http://www.contoso.com" xmlns:a="http://www.contoso.com/a" xmlns:b="http://www.contoso.com/b">  
    <child1 xmlns="" xmlns:a="urn:a">  
        <child2 xmlns:c="urn:c" />  
    </child1>  
</root>  
```  
  
 Cuando está situado en `child2`, ésta es la secuencia de espacios de nombres (el espacio de nombres en el que está situado <xref:System.Xml.XPath.XPathNavigator> después de llamar al método <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> y realizar, a continuación, una serie de llamadas al método <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>).  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.All>: `xmlns:c="urn:c"`, `xmlns:a="urn:a"`, `xmlns=""`, `xmlns:b="http://www.contoso.com/b"`, `xmlns:a="http://www.contoso.com/a"`, `xmlns="http://www.contoso.com"` y `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.ExcludeXml>: `xmlns:c="urn:c"`, `xmlns:a="urn:a"`, `xmlns=""`, `xmlns:b="http://www.contoso.com/b"`, `xmlns:a="http://www.contoso.com/a"` y `xmlns="http://www.contoso.com"`.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.Local>: `xmlns:c="urn:c"`.  
  
> [!NOTE]
> La clase <xref:System.Xml.XPath.XPathNavigator> devuelve nodos de espacios de nombres en el orden inverso del documento. Por lo tanto, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> se desplaza básicamente al último nodo de espacios de nombres del ámbito actual.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Navegación por un conjunto de nodos con XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)
- [Extracción de datos XML con XPathNavigator](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)
- [Acceso a datos XML fuertemente tipados utilizando XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
