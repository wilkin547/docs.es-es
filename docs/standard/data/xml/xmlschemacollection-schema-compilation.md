---
title: Compilación de esquema XmlSchemaCollection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
ms.openlocfilehash: af6df3729f1bd926e9a47cc5b9d9bf460c8e1225
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159291"
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="44c80-102">Compilación de esquema XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="44c80-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="44c80-103">**XmlSchemaCollection** es una caché o una biblioteca en la que se pueden almacenar y validar esquemas de esquema reducido de datos XML (XDR) y de lenguaje de definición de esquema XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="44c80-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="44c80-104">**XmlSchemaCollection** mejora el rendimiento al almacenar en memoria caché los esquemas, en lugar obtener acceso a ellos desde un archivo o dirección URL.</span><span class="sxs-lookup"><span data-stu-id="44c80-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44c80-105">Aunque la clase **XmlSchemaCollection** almacena tanto esquemas XDR como XML, cualquier método y propiedad que acepte o devuelva un objeto **XmlSchema** solo admitirá esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="44c80-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="44c80-106">La clase <xref:System.Xml.Schema.XmlSchemaCollection> está obsoleta y ha sido reemplazada por la clase <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="44c80-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="44c80-107">Para más información sobre la clase <xref:System.Xml.Schema.XmlSchemaSet>, vea [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="44c80-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="44c80-108">Agregar esquemas a la colección</span><span class="sxs-lookup"><span data-stu-id="44c80-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="44c80-109">Los esquemas se cargan en la colección mediante el método**Add** de **XmlSchemaCollection**. En ese momento, el esquema se asocia con un identificador URI de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="44c80-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="44c80-110">Para los esquemas XML, el URI de espacio de nombres es, por lo general, el espacio de nombres de destino para el esquema.</span><span class="sxs-lookup"><span data-stu-id="44c80-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="44c80-111">Para los esquemas XDR, es el espacio de nombres especificado cuando el esquema se agregó a la colección.</span><span class="sxs-lookup"><span data-stu-id="44c80-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="44c80-112">Comprobar un esquema en la colección</span><span class="sxs-lookup"><span data-stu-id="44c80-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="44c80-113">Puede comprobar si un esquema se encuentra en la colección con el método **Contains**,</span><span class="sxs-lookup"><span data-stu-id="44c80-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="44c80-114">que acepta un objeto **XmlSchema** (solo para esquemas XML) o una cadena que representa el identificador URI del espacio de nombres asociado al esquema (para esquemas XML y XDR).</span><span class="sxs-lookup"><span data-stu-id="44c80-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="44c80-115">Recuperar un esquema de la colección</span><span class="sxs-lookup"><span data-stu-id="44c80-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="44c80-116">Puede recuperar un esquema de la colección mediante la propiedad **Item**,</span><span class="sxs-lookup"><span data-stu-id="44c80-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="44c80-117">que acepta una cadena que representa el identificador URI de espacio de nombres asociado al esquema (por lo general, su espacio de nombres de destino) y devuelve un objeto **XmlSchema**.</span><span class="sxs-lookup"><span data-stu-id="44c80-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="44c80-118">La propiedad **Item** se aplica solo a esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="44c80-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="44c80-119">El valor devuelto siempre es una referencia nula para los esquemas XDR porque carecen de un modelo de objetos disponible.</span><span class="sxs-lookup"><span data-stu-id="44c80-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="44c80-120">Validar documentos XML mediante XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="44c80-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="44c80-121">Puede validar un documento XML de instancia con **XmlSchemaCollection** si crea el objeto **XmlSchemaCollection**, agrega los esquemas a la colección y establece el valor de la propiedad **Schemas** en el **XmlValidatingReader** de modo que se le asigne el objeto **XmlSchemaCollection** creado a **XmlValidatingReader**.</span><span class="sxs-lookup"><span data-stu-id="44c80-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="44c80-122">Mejorar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="44c80-122">Improved Performance</span></span>  
 <span data-ttu-id="44c80-123">Si va a validar más de un documento con respecto al mismo esquema, es recomendable utilizar **XmlSchemaCollection**, ya que proporciona un mayor rendimiento al almacenar en memoria caché los esquemas.</span><span class="sxs-lookup"><span data-stu-id="44c80-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="44c80-124">En el ejemplo de código siguiente se crea el objeto **XmlSchemaCollection**, se agregan esquemas a la colección y se establece el valor de la propiedad **Schemas**.</span><span class="sxs-lookup"><span data-stu-id="44c80-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="44c80-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="44c80-125">See also</span></span>

- [<span data-ttu-id="44c80-126">Validación de XDR con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="44c80-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)
- [<span data-ttu-id="44c80-127">Validación de esquemas XML (XSD) con XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="44c80-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
