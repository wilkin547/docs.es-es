---
title: Navegación por el espacio de nombres XPath
ms.date: 03/30/2017
ms.assetid: 06cc7abb-7416-415c-9dd6-67751b8cabd5
ms.openlocfilehash: 4d2ef71a41d19fd5bb573afab66dc8a15e19c393
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831213"
---
# <a name="xpath-namespace-navigation"></a>Navegación por el espacio de nombres XPath
Para usar consultas XPath con documentos XML, debe direccionar correctamente los espacios de nombres XML y los elementos que contienen los espacios de nombres. Los espacios de nombres evitan las ambigüedades que pueden producirse cuando los nombres se utilizan en varios contextos; por ejemplo, el nombre `ID` puede referirse a varios identificadores asociados con distintos elementos de un documento XML. La sintaxis de los espacios de nombres especifica los URI, nombres y prefijos que distinguen los elementos de un documento XML.  
  
 El ejemplo de este tema muestra el uso de los prefijos durante la navegación por un documento XML con <xref:System.Xml.XPath.XPathNavigator>. Para obtener más información sobre los espacios de nombres y la sintaxis, vea [XML Files: Understanding XML Namespaces](/previous-versions/dotnet/articles/bb986013(v=msdn.10)) (Archivos XML: descripción de los espacios de nombres XML).  
  
## <a name="namespace-declarations"></a>Declaraciones de espacios de nombres  
 Las declaraciones de espacios de nombres permiten distinguir y direccionar los elementos de un documento XML cuando se utiliza una instancia de <xref:System.Xml.XPath.XPathNavigator>. Los prefijos de los espacios de nombres proporcionan una sintaxis breve para direccionar los espacios de nombres.  
  
 Los prefijos se definen mediante el formato: `<e:Envelope xmlns:e=http://schemas.xmlsoap.org/soap/envelope/>.` En esta sintaxis, el prefijo "`e`" es una abreviatura del URI formal del espacio de nombres. Puede identificar el elemento `Body` como miembro del espacio de nombres `Envelope` mediante el uso de la sintaxis: `e:Body`.  
  
 En el ejemplo de navegación de la sección siguiente, se hará referencia al documento XML siguiente como `response.xml`.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<e:Envelope xmlns:e="http://schemas.xmlsoap.org/soap/envelope/">  
  <e:Body>  
    <s:Search xmlns:s="http://schemas.microsoft.com/v1/Search">  
      <r:request xmlns:r="http://schemas.microsoft.com/v1/Search/metadata"
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance">  
      </r:request>  
    </s:Search>  
  </e:Body>  
</e:Envelope>  
```  
  
## <a name="navigation-by-namespace-prefix"></a>Navegación por prefijos de los espacios de nombres  
 El código de esta sección utiliza objetos <xref:System.Xml.XPath.XPathNavigator> y <xref:System.Xml.XmlNamespaceManager> para seleccionar el elemento `Search` del documento XML de la sección anterior. La expresión `xpath` de la consulta incluye los prefijos de los espacios de nombres para cada elemento de la ruta. El hecho de especificar la identidad precisa de los espacios de nombres que contienen cada elemento garantiza una navegación correcta al elemento `Search` con el método <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>.  
  
```csharp  
using (XmlReader reader = XmlReader.Create("response.xml"))  
{  
    XPathDocument doc = new XPathDocument(reader);  
    XPathNavigator nav = doc.CreateNavigator();
  
    XmlNamespaceManager nsmgr = new XmlNamespaceManager(nav.NameTable);  
    nsmgr.AddNamespace("e", @"http://schemas.xmlsoap.org/soap/envelope/");  
    nsmgr.AddNamespace("s", @"http://schemas.microsoft.com/v1/Search");  
    nsmgr.AddNamespace("r", @"http://schemas.microsoft.com/v1/Search/metadata");  
    nsmgr.AddNamespace("i", @"http://www.w3.org/2001/XMLSchema-instance");  
  
    string xpath = "/e:Envelope/e:Body/s:Search";  
  
    XPathNavigator element = nav.SelectSingleNode(xpath, nsmgr);  
  
    Console.WriteLine("Element Prefix:" + element.Prefix +
    " Local name:" + element.LocalName);  
    Console.WriteLine("Namespace URI: " + element.NamespaceURI);  
}  
```  
  
 La precisión que se logra al usar espacios de nombres completos y nombres completos no se obtiene solo por comodidad. Basta con experimentar un poco con la definición del documento y el código de los ejemplos anteriores para comprobar que la navegación sin nombres de elemento completos produce excepciones. Por ejemplo, la definición del elemento: `<Search xmlns="http://schemas.microsoft.com/v1/Search">` y la consulta: string `xpath = "/s:Envelope/s:Body/Search";` sin el prefijo del espacio de nombres en el elemento `Search` devuelve `null` en lugar del elemento `Search`.  
  
## <a name="see-also"></a>Vea también

- [Acceso a datos XML con XPathNavigator](accessing-xml-data-using-xpathnavigator.md)
- [Selección, evaluación y coincidencia de datos XML con XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
