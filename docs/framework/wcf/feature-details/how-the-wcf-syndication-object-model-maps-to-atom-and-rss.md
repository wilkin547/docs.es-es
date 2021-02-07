---
description: Más información acerca de cómo se asigna el modelo de objetos de distribución de WCF a Atom y RSS
title: Asignación del modelo de objetos de distribución de WCF a Atom y RSS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0365eb37-98cc-4b13-80fb-f1e78847a748
ms.openlocfilehash: d66fb30acde18053e866b8986ebf71a6eed562ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742945"
---
# <a name="how-the-wcf-syndication-object-model-maps-to-atom-and-rss"></a><span data-ttu-id="1cff0-103">Asignación del modelo de objetos de distribución de WCF a Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="1cff0-103">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>

<span data-ttu-id="1cff0-104">Al desarrollar un servicio de distribución de Windows Communication Foundation (WCF), se crean fuentes y elementos con las siguientes clases:</span><span class="sxs-lookup"><span data-stu-id="1cff0-104">When developing a Windows Communication Foundation (WCF) syndication service, you create feeds and items using the following classes:</span></span>  
  
- <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
- <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
- <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
- <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
- <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
- <xref:System.ServiceModel.Syndication.TextSyndicationContent>  
  
- <xref:System.ServiceModel.Syndication.UrlSyndicationContent>  
  
- <xref:System.ServiceModel.Syndication.XmlSyndicationContent>  
  
 <span data-ttu-id="1cff0-105"><xref:System.ServiceModel.Syndication.SyndicationFeed> se puede serializar en cualquier formato para redifusión web para el que está definido un formateador.</span><span class="sxs-lookup"><span data-stu-id="1cff0-105">A <xref:System.ServiceModel.Syndication.SyndicationFeed> can be serialized into any syndication format for which a formatter is defined.</span></span> <span data-ttu-id="1cff0-106">WCF se distribuye con dos formateadores: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> y <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> .</span><span class="sxs-lookup"><span data-stu-id="1cff0-106">WCF ships with two formatters: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> and <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>.</span></span>  
  
 <span data-ttu-id="1cff0-107">El modelo de objetos alrededor de <xref:System.ServiceModel.Syndication.SyndicationFeed> y <xref:System.ServiceModel.Syndication.SyndicationItem> está alineado más estrechamente con la especificación Atom 1.0 que con la especificación RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-107">The object model around <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> is aligned more closely with the Atom 1.0 specification than the RSS 2.0 specification.</span></span> <span data-ttu-id="1cff0-108">Esto se debe a que Atom 1.0 es una especificación más sustancial que define elementos que son ambiguos o que se han omitido de la especificación RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-108">This is because Atom 1.0 is a more substantial specification that defines elements that are ambiguous or omitted from the RSS 2.0 specification.</span></span> <span data-ttu-id="1cff0-109">Por este motivo, muchos elementos del modelo de objetos de distribución de WCF no tienen ninguna representación directa en la especificación RSS 2,0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-109">Because of this, many items in the WCF syndication object model have no direct representation in the RSS 2.0 specification.</span></span> <span data-ttu-id="1cff0-110">Al serializar <xref:System.ServiceModel.Syndication.SyndicationFeed> <xref:System.ServiceModel.Syndication.SyndicationItem> objetos y en RSS 2,0, WCF permite serializar elementos de datos específicos de Atom como elementos de extensión calificados con el espacio de nombres que cumplen con la especificación Atom.</span><span class="sxs-lookup"><span data-stu-id="1cff0-110">When serializing <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> objects into RSS 2.0, WCF allows you to serialize Atom-specific data elements as namespace-qualified extension elements that conform to the Atom specification.</span></span> <span data-ttu-id="1cff0-111">Esto se puede controlar mediante un parámetro pasado al constructor <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="1cff0-111">You can control this with a parameter passed to the <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> constructor.</span></span>  
  
 <span data-ttu-id="1cff0-112">Los ejemplos de código de este tema usan uno de los dos métodos definidos aquí para realizar la serialización real.</span><span class="sxs-lookup"><span data-stu-id="1cff0-112">The code samples in this topic use one of two methods defined here to do the actual serialization.</span></span>  
  
 <span data-ttu-id="1cff0-113">`SerializeFeed` serializa una fuente de distribución.</span><span class="sxs-lookup"><span data-stu-id="1cff0-113">`SerializeFeed` serializes a syndication feed.</span></span>  
  
 [!code-csharp[SyndicationMapping#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#10)]
 [!code-vb[SyndicationMapping#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#10)]  
  
 <span data-ttu-id="1cff0-114">`SerializeItem` serializa un elemento de distribución.</span><span class="sxs-lookup"><span data-stu-id="1cff0-114">`SerializeItem` serializes a syndication item.</span></span>  
  
 [!code-csharp[SyndicationMapping#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#11)]
 [!code-vb[SyndicationMapping#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#11)]  
  
## <a name="syndicationfeed"></a><span data-ttu-id="1cff0-115">SyndicationFeed</span><span class="sxs-lookup"><span data-stu-id="1cff0-115">SyndicationFeed</span></span>  

 <span data-ttu-id="1cff0-116">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.SyndicationFeed> a Atom 1.0 y RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-116">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.SyndicationFeed> class to Atom 1.0 and RSS 2.0.</span></span>  
  
 [!code-csharp[SyndicationMapping#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#0)]
 [!code-vb[SyndicationMapping#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#0)]  
  
 <span data-ttu-id="1cff0-117">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationFeed> a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-117">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationFeed> is serialized to Atom 1.0.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<feed xml:lang="EN-US" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text">My Feed Title</title>  
  <subtitle type="text">My Feed Description</subtitle>  
  <id>FeedID</id>  
  <rights type="text">Copyright 2007</rights>  
  <updated>2007-08-29T13:57:17-07:00</updated>  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <logo>http://server/image.jpg</logo>  
  <generator>Sample Code</generator>  
  <link rel="alternate" href="http://myfeeduri/" />  
  <entry>  
    <id>ItemID</id>  
    <title type="text">Item Title</title>  
    <summary type="text">Item Summary</summary>  
    <published>2007-08-29T00:00:00-07:00</published>  
    <updated>2007-08-29T13:57:17-07:00</updated>  
    <author>  
      <name>Jesper Aaberg</name>  
      <uri>http://Jesper/Aaberg</uri>  
      <email>Jesper@Aaberg.com</email>  
    </author>  
    <contributor>  
      <name>Lene Aaling</name>  
      <uri>http://Lene/Aaling</uri>  
      <email>Lene@Aaling.com</email>  
    </contributor>  
    <link rel="alternate" href="http://myitemuri/" />  
    <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
    <content type="text">Item Content</content>  
    <rights type="text">Copyright 2007</rights>  
    <source>  
      <title type="text">My Feed Title</title>  
      <subtitle type="text">My Feed Description</subtitle>  
      <id>FeedID</id>  
      <rights type="text">Copyright 2007</rights>  
      <updated>2007-08-29T13:57:17-07:00</updated>  
      <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
      <logo>http://server/image.jpg</logo>  
      <generator>Sample Code</generator>  
      <link rel="alternate" href="http://myfeeduri/" />  
    </source>  
  </entry>  
</feed>  
```  
  
 <span data-ttu-id="1cff0-118">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationFeed> a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-118">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationFeed> is serialized to RSS 2.0.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<rss xmlns:a10="http://www.w3.org/2005/Atom" version="2.0">  
  <channel>  
    <title>My Feed Title</title>  
    <link>http://myfeeduri/</link>  
    <description>My Feed Description</description>  
    <language>EN-US</language>  
    <copyright>Copyright 2007</copyright>  
    <lastBuildDate>Wed, 29 Aug 2007 13:57:17 -0700</lastBuildDate>  
    <category domain="categoryScheme">categoryName</category>  
    <generator>Sample Code</generator>  
    <image>  
      <url>http://server/image.jpg</url>  
      <title>My Feed Title</title>  
      <link>http://myfeeduri/</link>  
    </image>  
    <a10:id>FeedID</a10:id>  
    <item>  
      <guid isPermaLink="false">ItemID</guid>  
      <link>http://myitemuri/</link>  
      <author>Jesper@Aaberg.com</author>  
      <category domain="categoryScheme">categoryName</category>  
      <title>Item Title</title>  
      <description>Item Summary</description>  
      <source>My Feed Title</source>  
      <pubDate>Wed, 29 Aug 2007 00:00:00 -0700</pubDate>  
      <a10:updated>2007-08-29T13:57:17-07:00</a10:updated>  
      <a10:rights type="text">Copyright 2007</a10:rights>  
      <a10:content type="text">Item Content</a10:content>  
      <a10:contributor>  
        <a10:name>Lene Aaling</a10:name>  
        <a10:uri>http://Lene/Aaling</a10:uri>  
        <a10:email>Lene@Aaling.com</a10:email>  
      </a10:contributor>  
    </item>  
  </channel>  
</rss>  
```  
  
## <a name="syndicationitem"></a><span data-ttu-id="1cff0-119">SyndicationItem</span><span class="sxs-lookup"><span data-stu-id="1cff0-119">SyndicationItem</span></span>  

 <span data-ttu-id="1cff0-120">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.SyndicationItem> a Atom 1.0 y RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-120">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.SyndicationItem> class to Atom 1.0 and RSS 2.0.</span></span>  
  
 [!code-csharp[SyndicationMapping#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#1)]
 [!code-vb[SyndicationMapping#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#1)]  
  
 <span data-ttu-id="1cff0-121">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationItem> a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-121">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationItem> is serialized to Atom 1.0.</span></span>  
  
```xml  
<entry xmlns="http://www.w3.org/2005/Atom">  
  <id>ItemID</id>  
  <title type="text">Item Title</title>  
  <summary type="text">Item Summary</summary>  
  <published>2007-08-29T00:00:00-07:00</published>  
  <updated>2007-08-29T14:07:09-07:00</updated>  
  <author>  
    <name>Jesper Aaberg</name>  
    <uri>http://Contoso/Aaberg</uri>  
    <email>Jesper.Aaberg@contoso.com</email>  
  </author>  
  <author>  
    <name>Syed Abbas</name>  
    <uri>http://Contoso/Abbas</uri>  
    <email>Syed.Abbas@contoso.com</email>  
  </author>  
  <contributor>  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
  <contributor>  
    <name>Kim Abercrombie</name>  
    <uri>http://Contoso/Abercrombie</uri>  
    <email>Kim.Abercrombie@contoso.com</email>  
  </contributor>  
  <link rel="alternate" href="http://myitemuri/" />  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <content type="text">Item Content</content>  
  <rights type="text">Copyright 2007</rights>  
  <source>  
    <title type="text">My Feed Title</title>  
    <subtitle type="text">My Feed Description</subtitle>  
    <link rel="alternate" href="http://myfeeduri/" />  
  </source>  
</entry>  
```  
  
 <span data-ttu-id="1cff0-122">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationItem> a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-122">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationItem> is serialized to RSS 2.0.</span></span>  
  
```xml  
<item>  
  <guid isPermaLink="false">ItemID</guid>  
  <link>http://myitemuri/</link>  
  <author xmlns="http://www.w3.org/2005/Atom">  
    <name>Jesper Aaberg</name>  
    <uri>http://Jesper/Aaberg</uri>  
    <email>Jesper@Aaberg.com</email>  
  </author>  
  <author xmlns="http://www.w3.org/2005/Atom">  
    <name>Syed Abbas</name>  
    <uri>http://Contoso/Abbas</uri>  
    <email>Syed.Abbas@contoso.com</email>  
  </author>  
  <category domain="categoryScheme">categoryName</category>  
  <category domain="categoryScheme">categoryName</category>  
  <title>Item Title</title>  
  <description>Item Summary</description>  
  <source>My Feed Title</source>  
  <pubDate>Wed, 29 Aug 2007 00:00:00 -0700</pubDate>  
  <updated xmlns="http://www.w3.org/2005/Atom">2007-08-29T14:07:09-07:00</updated>  
  <rights type="text" xmlns="http://www.w3.org/2005/Atom">Copyright 2007</rights>  
  <content type="text" xmlns="http://www.w3.org/2005/Atom">Item Content</content>  
  <contributor xmlns="http://www.w3.org/2005/Atom">  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
  <contributor xmlns="http://www.w3.org/2005/Atom">  
    <name>Kim Abercrombie</name>  
    <uri>http://Contoso/Abercrombie</uri>  
    <email>Kim.Abercrombie@contoso.com</email>  
  </contributor>  
</item>  
```  
  
## <a name="syndicationperson"></a><span data-ttu-id="1cff0-123">SyndicationPerson</span><span class="sxs-lookup"><span data-stu-id="1cff0-123">SyndicationPerson</span></span>  

 <span data-ttu-id="1cff0-124">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.SyndicationPerson> a Atom 1.0 y RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-124">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.SyndicationPerson> class to Atom 1.0 and RSS 2.0.</span></span>  
  
 [!code-csharp[SyndicationMapping#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#2)]
 [!code-vb[SyndicationMapping#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#2)]  
  
 <span data-ttu-id="1cff0-125">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationPerson> a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-125">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationPerson> is serialized to Atom 1.0.</span></span>  
  
```xml  
  <author>  
    <name>Jesper Aaberg</name>  
    <uri>http://Contoso/Aaberg</uri>  
    <email>Jesper.Aaberg@contoso.com</email>  
  </author>  
<contributor>  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
```  
  
 <span data-ttu-id="1cff0-126">El siguiente fragmento XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.SyndicationPerson> a RSS 2.0 si solo existe una <xref:System.ServiceModel.Syndication.SyndicationPerson> en las colecciones `Authors` o `Contributors`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1cff0-126">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationPerson> class is serialized to RSS 2.0 if only one <xref:System.ServiceModel.Syndication.SyndicationPerson> exists in the `Authors` or `Contributors` collections, respectively.</span></span>  
  
```xml  
<author>Jesper.Aaberg@contoso.com</author>  
<a10:contributor>  
    <a10:name>Lene Aaling</a10:name>  
    <a10:uri>http://Contoso/Aaling</a10:uri>  
    <a10:email>Lene.Aaling@contoso.com</a10:email>  
</a10:contributor>  
```  
  
 <span data-ttu-id="1cff0-127">El siguiente fragmento XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.SyndicationPerson> a RSS 2.0 si existe más de una <xref:System.ServiceModel.Syndication.SyndicationPerson> en las colecciones `Authors` o `Contributors`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1cff0-127">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationPerson> class is serialized to RSS 2.0 if more than one <xref:System.ServiceModel.Syndication.SyndicationPerson> exists in the `Authors` or `Contributors` collections, respectively.</span></span>  
  
```xml  
<a10:author>  
    <a10:name>Jesper Aaberg</a10:name>  
    <a10:uri>http://Contoso/Aaberg</a10:uri>  
    <a10:email>Jesper.Aaberg@contoso.com</a10:email>  
</a10:author>  
<a10:author>  
    <a10:name>Syed Abbas</a10:name>  
    <a10:uri>http://Contoso/Abbas</a10:uri>  
    <a10:email>Syed.Abbas@contoso.com</a10:email>  
</a10:author>  
<a10:contributor>  
    <a10:name>Lene Aaling</a10:name>  
    <a10:uri>http://Contoso/Aaling</a10:uri>  
    <a10:email>Lene.Aaling@contoso.com</a10:email>  
</a10:contributor>  
<a10:contributor>  
    <a10:name>Kim Abercrombie</a10:name>  
    <a10:uri>http://Contoso/Abercrombie</a10:uri>  
    <a10:email>Kim.Abercrombie@contoso.com</a10:email>  
</a10:contributor>  
```  
  
## <a name="syndicationlink"></a><span data-ttu-id="1cff0-128">SyndicationLink</span><span class="sxs-lookup"><span data-stu-id="1cff0-128">SyndicationLink</span></span>  

 <span data-ttu-id="1cff0-129">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.SyndicationLink> a Atom 1.0 y RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-129">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.SyndicationLink> class to Atom 1.0 and RSS 2.0.</span></span>  
  
 [!code-csharp[SyndicationMapping#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#3)]
 [!code-vb[SyndicationMapping#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#3)]  
  
 <span data-ttu-id="1cff0-130">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationLink> a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-130">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationLink> is serialized to Atom 1.0.</span></span>  
  
 `<link rel="alternate" type="text/html" title="My Link Title" length="2048" href="http://contoso/MyLink" />`  
  
 <span data-ttu-id="1cff0-131">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationLink> a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-131">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationLink> is serialized to RSS 2.0.</span></span>  
  
 `<a10:link rel="alternate" type="text/html" title="My Link Title" length="2048" href="http://contoso/MyLink" />`  
  
## <a name="syndicationcategory"></a><span data-ttu-id="1cff0-132">SyndicationCategory</span><span class="sxs-lookup"><span data-stu-id="1cff0-132">SyndicationCategory</span></span>  

 <span data-ttu-id="1cff0-133">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.SyndicationCategory> a Atom 1.0 y RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-133">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.SyndicationCategory> class to Atom 1.0 and RSS 2.0.</span></span>  
  
 [!code-csharp[SyndicationMapping#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#4)]
 [!code-vb[SyndicationMapping#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#4)]  
  
 <span data-ttu-id="1cff0-134">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationCategory> a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-134">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationCategory> is serialized to Atom 1.0.</span></span>  
  
 `<category term="categoryName" label="categoryLabel" scheme="categoryScheme" />`  
  
 <span data-ttu-id="1cff0-135">El siguiente XML muestra cómo se serializa <xref:System.ServiceModel.Syndication.SyndicationCategory> a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-135">The following XML shows how the <xref:System.ServiceModel.Syndication.SyndicationCategory> is serialized to RSS 2.0.</span></span>  
  
 `<category domain="categoryScheme">categoryName</category>`  
  
## <a name="textsyndicationcontent"></a><span data-ttu-id="1cff0-136">TextSyndicationContent</span><span class="sxs-lookup"><span data-stu-id="1cff0-136">TextSyndicationContent</span></span>  

 <span data-ttu-id="1cff0-137">El siguiente ejemplo de código muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> a Atom 1.0 y RSS 2.0 cuando <xref:System.ServiceModel.Syndication.TextSyndicationContent> se crea con contenido HTML.</span><span class="sxs-lookup"><span data-stu-id="1cff0-137">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class to Atom 1.0 and RSS 2.0 when <xref:System.ServiceModel.Syndication.TextSyndicationContent> is created with HTML content.</span></span>  
  
 [!code-csharp[SyndicationMapping#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#5)]
 [!code-vb[SyndicationMapping#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#5)]  
  
 <span data-ttu-id="1cff0-138">El siguiente XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> con contenido de HTML a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-138">The following XML shows how the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class with HTML content is serialized to Atom 1.0.</span></span>  
  
 `<content type="html"><html> some html </html></content>`  
  
 <span data-ttu-id="1cff0-139">El siguiente XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> con contenido de HTML a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-139">The following XML shows how the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class with HTML content is serialized to RSS 2.0.</span></span>  
  
 `<description><html> some html </html></description>`  
  
 <span data-ttu-id="1cff0-140">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> a Atom 1.0 y RSS 2.0 cuando se crea <xref:System.ServiceModel.Syndication.TextSyndicationContent> con contenido de texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="1cff0-140">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class to Atom 1.0 and RSS 2.0 when <xref:System.ServiceModel.Syndication.TextSyndicationContent> is created with plain text content.</span></span>  
  
 [!code-csharp[SyndicationMapping#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#6)]
 [!code-vb[SyndicationMapping#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#6)]  
  
 <span data-ttu-id="1cff0-141">El siguiente XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> con contenido de texto sin formato a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-141">The following XML shows how the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class with plain text content is serialized to Atom 1.0.</span></span>  
  
 `<content type="text">Some Plain Text</content>`  
  
 <span data-ttu-id="1cff0-142">El siguiente XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> con contenido de texto sin formato a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-142">The following XML shows how the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class with plain text content is serialized to RSS 2.0.</span></span>  
  
 `<description>Some Plain Text</description>`  
  
 <span data-ttu-id="1cff0-143">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> a Atom 1.0 y RSS 2.0 cuando se crea <xref:System.ServiceModel.Syndication.TextSyndicationContent> con contenido XHTML.</span><span class="sxs-lookup"><span data-stu-id="1cff0-143">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class to Atom 1.0 and RSS 2.0 when <xref:System.ServiceModel.Syndication.TextSyndicationContent> is created with XHTML content.</span></span>  
  
 [!code-csharp[SyndicationMapping#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#7)]
 [!code-vb[SyndicationMapping#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#7)]  
  
 <span data-ttu-id="1cff0-144">El siguiente XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> con contenido de XHTML a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-144">The following XML shows how the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class with XHTML content is serialized to Atom 1.0.</span></span>  
  
 `<content type="xhtml">`  
  
 `<html> some xhtml </html>`  
  
 `</content>`  
  
 <span data-ttu-id="1cff0-145">El siguiente fragmento XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.TextSyndicationContent> con contenido XHTML a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-145">The following XML shows how the <xref:System.ServiceModel.Syndication.TextSyndicationContent> class with XHTML content is serialized to RSS 2.0.</span></span>  
  
 `<description><html> some xhtml </html></description>`  
  
## <a name="urlsyndicationcontent"></a><span data-ttu-id="1cff0-146">UrlSyndicationContent</span><span class="sxs-lookup"><span data-stu-id="1cff0-146">UrlSyndicationContent</span></span>  

 <span data-ttu-id="1cff0-147">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.UrlSyndicationContent> a Atom 1.0 y RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-147">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.UrlSyndicationContent> class to Atom 1.0 and RSS 2.0.</span></span>  
  
 [!code-csharp[SyndicationMapping#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#8)]
 [!code-vb[SyndicationMapping#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#8)]  
  
 <span data-ttu-id="1cff0-148">El siguiente fragmento XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.UrlSyndicationContent> a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-148">The following XML shows how the <xref:System.ServiceModel.Syndication.UrlSyndicationContent> class is serialized to Atom 1.0.</span></span>  
  
 `<content type="audio" src="http://someurl/" />`  
  
 <span data-ttu-id="1cff0-149">El siguiente fragmento XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.UrlSyndicationContent> con contenido XHTML a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-149">The following XML shows how the <xref:System.ServiceModel.Syndication.UrlSyndicationContent> class with XHTML content is serialized to RSS 2.0.</span></span>  
  
 `<description />`  
  
 `<content type="audio" src="http://Contoso/someurl/" xmlns="http://www.w3.org/2005/Atom" />`  
  
## <a name="xmlsyndicationcontent"></a><span data-ttu-id="1cff0-150">XmlSyndicationContent</span><span class="sxs-lookup"><span data-stu-id="1cff0-150">XmlSyndicationContent</span></span>  

 <span data-ttu-id="1cff0-151">El siguiente código de ejemplo muestra cómo serializar la clase <xref:System.ServiceModel.Syndication.XmlSyndicationContent> a Atom 1.0 y RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-151">The following code example shows how to serialize the <xref:System.ServiceModel.Syndication.XmlSyndicationContent> class to Atom 1.0 and RSS 2.0.</span></span>  
  
 [!code-csharp[SyndicationMapping#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#9)]
 [!code-vb[SyndicationMapping#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#9)]  
  
 <span data-ttu-id="1cff0-152">El siguiente fragmento XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.XmlSyndicationContent> a Atom 1.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-152">The following XML shows how the <xref:System.ServiceModel.Syndication.XmlSyndicationContent> class is serialized to Atom 1.0.</span></span>  
  
 `<content type="mytype">`  
  
 `<SomeData xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.datacontract.org/2004/07/FeedMapping" />`  
  
 `</content>`  
  
 <span data-ttu-id="1cff0-153">El siguiente fragmento XML muestra cómo se serializa la clase <xref:System.ServiceModel.Syndication.XmlSyndicationContent> con contenido XHTML a RSS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1cff0-153">The following XML shows how the <xref:System.ServiceModel.Syndication.XmlSyndicationContent> class with XHTML content is serialized to RSS 2.0.</span></span>  
  
 `<content type="mytype" xmlns="http://www.w3.org/2005/Atom">`  
  
 `<SomeData xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.datacontract.org/2004/07/FeedMapping" />`  
  
 `</content>`  
  
## <a name="see-also"></a><span data-ttu-id="1cff0-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cff0-154">See also</span></span>

- [<span data-ttu-id="1cff0-155">Información general de distribución de WCF</span><span class="sxs-lookup"><span data-stu-id="1cff0-155">WCF Syndication Overview</span></span>](wcf-syndication-overview.md)
- [<span data-ttu-id="1cff0-156">Arquitectura de distribución</span><span class="sxs-lookup"><span data-stu-id="1cff0-156">Architecture of Syndication</span></span>](architecture-of-syndication.md)
- [<span data-ttu-id="1cff0-157">Procedimiento para crear una fuente RSS básica</span><span class="sxs-lookup"><span data-stu-id="1cff0-157">How to: Create a Basic RSS Feed</span></span>](how-to-create-a-basic-rss-feed.md)
- [<span data-ttu-id="1cff0-158">Procedimiento para crear una fuente Atom básica</span><span class="sxs-lookup"><span data-stu-id="1cff0-158">How to: Create a Basic Atom Feed</span></span>](how-to-create-a-basic-atom-feed.md)
- [<span data-ttu-id="1cff0-159">Procedimiento para exponer una fuente como Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="1cff0-159">How to: Expose a Feed as Both Atom and RSS</span></span>](how-to-expose-a-feed-as-both-atom-and-rss.md)
