---
title: Procedimiento para controlar prefijos de espacios de nombres (C#) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: 9f43c0804d8c830fa75f1e1390cb578c5f5d5106
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141385"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a><span data-ttu-id="0db13-102">Procedimiento para controlar prefijos de espacios de nombres (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="0db13-102">How to control namespace prefixes (C#) (LINQ to XML)</span></span>
<span data-ttu-id="0db13-103">En este tema se describe cómo puede controlar los prefijos de espacios de nombres al serializar un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="0db13-103">This topic describes how you can control namespace prefixes when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="0db13-104">En muchas situaciones, no es necesario controlar los prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0db13-104">In many situations, it is not necessary to control namespace prefixes.</span></span>  
  
 <span data-ttu-id="0db13-105">Sin embargo, ciertas herramientas de programación XML requieren un control específico de los prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0db13-105">However, certain XML programming tools require specific control of namespace prefixes.</span></span> <span data-ttu-id="0db13-106">Por ejemplo, es posible que esté manipulando una hoja de estilos XSLT o un documento XAML que contenga expresiones XPath incrustadas que hagan referencia a prefijos de espacios de nombres; en ese caso, es importante serializar el documento con dichos prefijos.</span><span class="sxs-lookup"><span data-stu-id="0db13-106">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes; in this case, it is important that the document be serialized with those specific prefixes.</span></span>  
  
 <span data-ttu-id="0db13-107">Esta es la razón más común para controlar los prefijos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0db13-107">This is the most common reason for controlling namespace prefixes.</span></span>  
  
 <span data-ttu-id="0db13-108">Otro motivo habitual para controlar prefijos de espacios de nombres se basa en permitir que los usuarios editen el documento XML manualmente y crear prefijos de fácil escritura.</span><span class="sxs-lookup"><span data-stu-id="0db13-108">Another common reason for controlling namespace prefixes is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="0db13-109">Por ejemplo, tal vez esté generando un documento XSD.</span><span class="sxs-lookup"><span data-stu-id="0db13-109">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="0db13-110">Las convenciones de los esquemas sugieren el uso de `xs` o `xsd` como prefijo para el espacio de nombres de esquema.</span><span class="sxs-lookup"><span data-stu-id="0db13-110">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>  
  
 <span data-ttu-id="0db13-111">Para controlar los prefijos de espacios de nombre, inserta atributos que declaran dichos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0db13-111">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="0db13-112">Si declara los espacios de nombres con prefijos específicos, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] intentará respetar los prefijos durante la serialización.</span><span class="sxs-lookup"><span data-stu-id="0db13-112">If you declare the namespaces with specific prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will attempt to honor the namespace prefixes when serializing.</span></span>  
  
 <span data-ttu-id="0db13-113">Para crear un atributo que declara un espacio de nombres con un prefijo, puede crear un atributo donde el espacio de nombres del nombre del atributo es <xref:System.Xml.Linq.XNamespace.Xmlns%2A> y el nombre del atributo es el prefijo del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0db13-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="0db13-114">El valor del atributo es el URI del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0db13-114">The value of the attribute is the URI of the namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0db13-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0db13-115">Example</span></span>  
 <span data-ttu-id="0db13-116">Este ejemplo declara dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0db13-116">This example declares two namespaces.</span></span> <span data-ttu-id="0db13-117">Especifica que el espacio de nombres `http://www.adventure-works.com` tiene el prefijo `aw` y que el espacio de nombres `www.fourthcoffee.com` tiene el prefijo `fc`.</span><span class="sxs-lookup"><span data-stu-id="0db13-117">It specifies that the `http://www.adventure-works.com` namespace has the prefix of `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="0db13-118">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0db13-118">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0db13-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0db13-119">See also</span></span>

- [<span data-ttu-id="0db13-120">Información general sobre los espacios de nombres (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0db13-120">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
