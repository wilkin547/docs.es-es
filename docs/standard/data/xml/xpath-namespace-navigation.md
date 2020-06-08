---
title: Navegación por el espacio de nombres XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 06cc7abb-7416-415c-9dd6-67751b8cabd5
ms.openlocfilehash: dce7d81d4249cb40c3be6dee4b8bd25951ccb10a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283213"
---
# <a name="xpath-namespace-navigation"></a><span data-ttu-id="82e08-102">Navegación por el espacio de nombres XPath</span><span class="sxs-lookup"><span data-stu-id="82e08-102">XPath Namespace Navigation</span></span>
<span data-ttu-id="82e08-103">Para usar consultas XPath con documentos XML, debe direccionar correctamente los espacios de nombres XML y los elementos que contienen los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="82e08-103">To use XPath queries with XML documents, you have to correctly address XML namespaces and the elements contained by namespaces.</span></span> <span data-ttu-id="82e08-104">Los espacios de nombres evitan las ambigüedades que pueden producirse cuando los nombres se utilizan en varios contextos; por ejemplo, el nombre `ID` puede referirse a varios identificadores asociados con distintos elementos de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="82e08-104">Namespaces prevent ambiguities that can occur when names are used in more than one context; for example, the name `ID` may refer to more than one identifier associated with different elements of an XML document.</span></span> <span data-ttu-id="82e08-105">La sintaxis de los espacios de nombres especifica los URI, nombres y prefijos que distinguen los elementos de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="82e08-105">Namespace syntax specifies URIs, names, and prefixes that distinguish the elements of an XML document.</span></span>  
  
 <span data-ttu-id="82e08-106">El ejemplo de este tema muestra el uso de los prefijos durante la navegación por un documento XML con <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="82e08-106">The example in this topic demonstrates the use of prefixes in navigating an XML document with <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="82e08-107">Para obtener más información sobre los espacios de nombres y la sintaxis, vea [XML Files: Understanding XML Namespaces](https://docs.microsoft.com/previous-versions/dotnet/articles/bb986013(v=msdn.10)) (Archivos XML: descripción de los espacios de nombres XML).</span><span class="sxs-lookup"><span data-stu-id="82e08-107">For more information about namespaces and syntax, see [XML Files: Understanding XML Namespaces](https://docs.microsoft.com/previous-versions/dotnet/articles/bb986013(v=msdn.10)).</span></span>  
  
## <a name="namespace-declarations"></a><span data-ttu-id="82e08-108">Declaraciones de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="82e08-108">Namespace Declarations</span></span>  
 <span data-ttu-id="82e08-109">Las declaraciones de espacios de nombres permiten distinguir y direccionar los elementos de un documento XML cuando se utiliza una instancia de <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="82e08-109">Namespace declarations make the elements of an XML document distinguishable and addressable when using an instance of <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="82e08-110">Los prefijos de los espacios de nombres proporcionan una sintaxis breve para direccionar los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="82e08-110">Namespace prefixes provide a brief syntax for addressing namespaces.</span></span>  
  
 <span data-ttu-id="82e08-111">Los prefijos se definen mediante el formato: `<e:Envelope xmlns:e=http://schemas.xmlsoap.org/soap/envelope/>.` En esta sintaxis, el prefijo "`e`" es una abreviatura del URI formal del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="82e08-111">Prefixes are defined by the form: `<e:Envelope xmlns:e=http://schemas.xmlsoap.org/soap/envelope/>.` In this syntax the prefix "`e`" is an abbreviation for the formal URI of the namespace.</span></span> <span data-ttu-id="82e08-112">Puede identificar el elemento `Body` como miembro del espacio de nombres `Envelope` mediante el uso de la sintaxis: `e:Body`.</span><span class="sxs-lookup"><span data-stu-id="82e08-112">You can identify the `Body` element as a member of the `Envelope` namespace by using the syntax: `e:Body`.</span></span>  
  
 <span data-ttu-id="82e08-113">En el ejemplo de navegación de la sección siguiente, se hará referencia al documento XML siguiente como `response.xml`.</span><span class="sxs-lookup"><span data-stu-id="82e08-113">The following XML document will be referenced as `response.xml` in the navigation example in the next section.</span></span>  
  
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
  
## <a name="navigation-by-namespace-prefix"></a><span data-ttu-id="82e08-114">Navegación por prefijos de los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="82e08-114">Navigation by Namespace Prefix</span></span>  
 <span data-ttu-id="82e08-115">El código de esta sección utiliza objetos <xref:System.Xml.XPath.XPathNavigator> y <xref:System.Xml.XmlNamespaceManager> para seleccionar el elemento `Search` del documento XML de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="82e08-115">The code in this section uses <xref:System.Xml.XPath.XPathNavigator> and <xref:System.Xml.XmlNamespaceManager> objects to select the `Search` element from the XML document in the previous section.</span></span> <span data-ttu-id="82e08-116">La expresión `xpath` de la consulta incluye los prefijos de los espacios de nombres para cada elemento de la ruta.</span><span class="sxs-lookup"><span data-stu-id="82e08-116">The query `xpath` includes namespace prefixes on each element in the path.</span></span> <span data-ttu-id="82e08-117">El hecho de especificar la identidad precisa de los espacios de nombres que contienen cada elemento garantiza una navegación correcta al elemento `Search` con el método <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>.</span><span class="sxs-lookup"><span data-stu-id="82e08-117">Specifying the precise identity of the namespaces that contain each element assures correct navigation to the `Search` element by the <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> method.</span></span>  
  
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
  
 <span data-ttu-id="82e08-118">La precisión que se logra al usar espacios de nombres completos y nombres completos no se obtiene solo por comodidad.</span><span class="sxs-lookup"><span data-stu-id="82e08-118">The precision of fully qualifying namespaces and names is more than a convenience.</span></span> <span data-ttu-id="82e08-119">Basta con experimentar un poco con la definición del documento y el código de los ejemplos anteriores para comprobar que la navegación sin nombres de elemento completos produce excepciones.</span><span class="sxs-lookup"><span data-stu-id="82e08-119">A little experimentation with the document definition and code in the previous examples will verify that navigation without fully qualified element names throws exceptions.</span></span> <span data-ttu-id="82e08-120">Por ejemplo, la definición del elemento: `<Search xmlns="http://schemas.microsoft.com/v1/Search">` y la consulta: string `xpath = "/s:Envelope/s:Body/Search";` sin el prefijo del espacio de nombres en el elemento `Search` devuelve `null` en lugar del elemento `Search`.</span><span class="sxs-lookup"><span data-stu-id="82e08-120">For example, the element definition: `<Search xmlns="http://schemas.microsoft.com/v1/Search">`, and query: string `xpath = "/s:Envelope/s:Body/Search";` without the namespace prefix on the `Search` element returns `null` instead of the `Search` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e08-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="82e08-121">See also</span></span>

- [<span data-ttu-id="82e08-122">Acceso a datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="82e08-122">Accessing XML Data using XPathNavigator</span></span>](accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="82e08-123">Selección, evaluación y coincidencia de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="82e08-123">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
