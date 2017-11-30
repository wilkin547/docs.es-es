---
title: "Compilación de esquema XmlSchemaCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="91f80-102">Compilación de esquema XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="91f80-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="91f80-103">El **XmlSchemaCollection** es una caché o una biblioteca donde se pueden almacenar y validar esquemas de lenguaje (XSD) de definición de datos XML reducidos (XDR) y el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="91f80-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="91f80-104">**XmlSchemaCollection** mejora el rendimiento al almacenar en caché esquemas en memoria en lugar de obtener acceso a ellos desde un archivo o dirección URL.</span><span class="sxs-lookup"><span data-stu-id="91f80-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91f80-105">Aunque la **XmlSchemaCollection** clase almacena tanto esquemas XDR como XML, cualquier método y propiedad que acepte o devuelva un **XmlSchema** objeto sólo admitirá esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="91f80-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91f80-106">La clase <xref:System.Xml.Schema.XmlSchemaCollection> está obsoleta y ha sido reemplazada por la clase <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="91f80-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="91f80-107">Para obtener más información sobre la <xref:System.Xml.Schema.XmlSchemaSet> , vea clase [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="91f80-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="91f80-108">Agregar esquemas a la colección</span><span class="sxs-lookup"><span data-stu-id="91f80-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="91f80-109">Los esquemas se cargan a la colección utilizando la **agregar** método **XmlSchemaCollection**, momento en el que el esquema está asociado a un URI de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="91f80-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="91f80-110">Para los esquemas XML, el URI de espacio de nombres es, por lo general, el espacio de nombres de destino para el esquema.</span><span class="sxs-lookup"><span data-stu-id="91f80-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="91f80-111">Para los esquemas XDR, es el espacio de nombres especificado cuando el esquema se agregó a la colección.</span><span class="sxs-lookup"><span data-stu-id="91f80-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="91f80-112">Comprobar un esquema en la colección</span><span class="sxs-lookup"><span data-stu-id="91f80-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="91f80-113">También puede comprobar si un esquema se encuentra en la colección utilizando la **Contains** método.</span><span class="sxs-lookup"><span data-stu-id="91f80-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="91f80-114">El **Contains** método puede toma una **XmlSchema** objeto (sólo para esquemas XML) o una cadena que representa el URI de espacio de nombres asociado al esquema (para esquemas XML y XDR).</span><span class="sxs-lookup"><span data-stu-id="91f80-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="91f80-115">Recuperar un esquema de la colección</span><span class="sxs-lookup"><span data-stu-id="91f80-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="91f80-116">Puede recuperar un esquema de la colección mediante la **elemento** propiedad.</span><span class="sxs-lookup"><span data-stu-id="91f80-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="91f80-117">El **elemento** propiedad toma una cadena que representa el espacio de nombres URI asociado con el esquema, por lo general su destino espacio de nombres y devuelve un **XmlSchema** objeto.</span><span class="sxs-lookup"><span data-stu-id="91f80-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="91f80-118">El **elemento** propiedad solo se aplica a los esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="91f80-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="91f80-119">El valor devuelto siempre es una referencia nula para los esquemas XDR porque carecen de un modelo de objetos disponible.</span><span class="sxs-lookup"><span data-stu-id="91f80-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="91f80-120">Validar documentos XML mediante XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="91f80-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="91f80-121">Puede validar un documento de instancia XML con un **XmlSchemaCollection** mediante la creación de la **XmlSchemaCollection** objeto, agrega los esquemas a la colección y establecer el **esquemas**  propiedad en el **XmlValidatingReader** asignar creado **XmlSchemaCollection** a la **XmlValidatingReader**.</span><span class="sxs-lookup"><span data-stu-id="91f80-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="91f80-122">Mejorar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="91f80-122">Improved Performance</span></span>  
 <span data-ttu-id="91f80-123">Se recomienda, si va a validar más de un documento con respecto al mismo esquema, que usa el **XmlSchemaCollection** porque proporciona un mejor rendimiento al almacenar en caché esquemas en memoria.</span><span class="sxs-lookup"><span data-stu-id="91f80-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="91f80-124">En el ejemplo de código siguiente se crea el **XmlSchemaCollection** objeto, se agregan esquemas a la colección y se establece la **esquemas** propiedad.</span><span class="sxs-lookup"><span data-stu-id="91f80-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");    
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a><span data-ttu-id="91f80-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f80-125">See Also</span></span>  
 [<span data-ttu-id="91f80-126">Validación de XDR con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="91f80-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [<span data-ttu-id="91f80-127">XML de validación de esquema (XSD) con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="91f80-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
