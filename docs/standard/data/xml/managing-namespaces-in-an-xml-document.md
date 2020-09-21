---
title: Administrar espacios de nombres en un documento XML
description: Aprenda a administrar espacios de nombres en un documento XML. Los espacios de nombres XML asocian nombres de elementos y de atributos de un documento XML con identificadores URI personalizados y predefinidos.
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 682643fc-b848-4e42-8c0d-50deeaeb5f2a
ms.openlocfilehash: 500c477eaa98b2858573e1012c62db4bc6c68137
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548096"
---
# <a name="managing-namespaces-in-an-xml-document"></a><span data-ttu-id="53b20-104">Administrar espacios de nombres en un documento XML</span><span class="sxs-lookup"><span data-stu-id="53b20-104">Managing Namespaces in an XML Document</span></span>
<span data-ttu-id="53b20-105">Los espacios de nombres XML asocian nombres de elementos y de atributos de un documento XML con identificadores URI personalizados y predefinidos.</span><span class="sxs-lookup"><span data-stu-id="53b20-105">XML namespaces associate element and attribute names in an XML document with custom and predefined URIs.</span></span> <span data-ttu-id="53b20-106">Para crear estas asociaciones, puede definir los prefijos de los URI del espacio de nombres y usar dichos prefijos para calificar los nombres de los elementos y de los atributos en los datos XML.</span><span class="sxs-lookup"><span data-stu-id="53b20-106">To create these associations, you define prefixes for namespace URIs, and use those prefixes to qualify element and attribute names in XML data.</span></span> <span data-ttu-id="53b20-107">Los espacios de nombres evitan conflictos de nombres de elementos y atributos y permiten que los elementos y atributos con el mismo nombre se traten y se validen de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="53b20-107">Namespaces prevent element and attribute name collisions, and enable elements and attributes of the same name to be handled and validated differently.</span></span>  
  
<a name="declare"></a>
## <a name="declaring-namespaces"></a><span data-ttu-id="53b20-108">Declarar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="53b20-108">Declaring namespaces</span></span>  
 <span data-ttu-id="53b20-109">Para declarar un espacio de nombres en un elemento, puede usar el atributo `xmlns:`:</span><span class="sxs-lookup"><span data-stu-id="53b20-109">To declare a namespace on an element, you use the `xmlns:` attribute:</span></span>  
  
 `xmlns:<name>=<"uri">`  
  
 <span data-ttu-id="53b20-110">Donde `<name>` es el prefijo de espacio de nombres y `<"uri">` es el URI que identifica el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="53b20-110">where `<name>` is the namespace prefix and `<"uri">` is the URI that identifies the namespace.</span></span> <span data-ttu-id="53b20-111">Después de declarar el prefijo, puede usarlo para calificar elementos y atributos de un documento XML y asociarlos al identificador URI del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="53b20-111">After you declare the prefix, you can use it to qualify elements and attributes in an XML document and associate them with the namespace URI.</span></span> <span data-ttu-id="53b20-112">Como el prefijo de espacio de nombres se utiliza en todo el documento, debe ser corto.</span><span class="sxs-lookup"><span data-stu-id="53b20-112">Because the namespace prefix is used throughout a document, it should be short in length.</span></span>  
  
 <span data-ttu-id="53b20-113">Este ejemplo define dos elementos `BOOK`.</span><span class="sxs-lookup"><span data-stu-id="53b20-113">This example defines two `BOOK` elements.</span></span> <span data-ttu-id="53b20-114">El primer elemento se califica mediante el prefijo del espacio de nombres `mybook` y el segundo elemento se califica con el prefijo `bb`.</span><span class="sxs-lookup"><span data-stu-id="53b20-114">The first element is qualified by the prefix, `mybook`, and the second element is qualified by the prefix, `bb`.</span></span> <span data-ttu-id="53b20-115">Cada prefijo se asocia a un URI del espacio de nombres distinto:</span><span class="sxs-lookup"><span data-stu-id="53b20-115">Each prefix is associated with a different namespace URI:</span></span>  
  
```xml  
<mybook:BOOK xmlns:mybook="http://www.contoso.com/books.dtd">  
<bb:BOOK xmlns:bb="urn:blueyonderairlines" />
</mybook>
```  
  
 <span data-ttu-id="53b20-116">Para indicar que un elemento es parte de un espacio de nombres en particular, agréguele el prefijo de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="53b20-116">To signify that an element is a part of a particular namespace, add the namespace prefix to it.</span></span> <span data-ttu-id="53b20-117">Por ejemplo, si el elemento `Author` pertenece al espacio de nombres `mybook`, se declara como `<mybook:Author>`.</span><span class="sxs-lookup"><span data-stu-id="53b20-117">For example, if a `Author` element belongs to the `mybook` namespace, it is declared as `<mybook:Author>`.</span></span>  
  
<a name="scope"></a>
## <a name="declaration-scope"></a><span data-ttu-id="53b20-118">Ámbito de la declaración</span><span class="sxs-lookup"><span data-stu-id="53b20-118">Declaration scope</span></span>  
 <span data-ttu-id="53b20-119">Un espacio de nombres es efectivo desde el momento de su declaración hasta el fin del elemento en el que se ha declarado.</span><span class="sxs-lookup"><span data-stu-id="53b20-119">A namespace is effective from its point of declaration until the end of the element it was declared in.</span></span> <span data-ttu-id="53b20-120">En este ejemplo, el espacio de nombres definido en el elemento `BOOK` no se aplica a elementos que estén fuera del elemento `BOOK`, tales como el elemento `Publisher`:</span><span class="sxs-lookup"><span data-stu-id="53b20-120">In this example, the namespace defined in the `BOOK` element doesn't apply to elements outside the `BOOK` element, such as the `Publisher` element:</span></span>  
  
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
  
 <span data-ttu-id="53b20-121">Para usar un espacio de nombres, antes éste se debe declarar, pero no tiene que aparecer al principio del documento XML.</span><span class="sxs-lookup"><span data-stu-id="53b20-121">A namespace must be declared before it can be used, but it doesn't have to appear at the top of the XML document.</span></span>  
  
 <span data-ttu-id="53b20-122">Si se usan varios espacios de nombres en un documento XML, puede definir un espacio de nombres como predeterminado para crear un documento en el que se mejora la claridad.</span><span class="sxs-lookup"><span data-stu-id="53b20-122">When you use multiple namespaces in an XML document, you can define one namespace as the default namespace to create a cleaner looking document.</span></span> <span data-ttu-id="53b20-123">El espacio de nombres predeterminado se declara en el elemento raíz y se aplica a todos los elementos sin calificar del documento.</span><span class="sxs-lookup"><span data-stu-id="53b20-123">The default namespace is declared in the root element and applies to all unqualified elements in the document.</span></span> <span data-ttu-id="53b20-124">Los espacios de nombres predeterminados solo se aplican a los elementos, no a los atributos.</span><span class="sxs-lookup"><span data-stu-id="53b20-124">Default namespaces apply to elements only, not to attributes.</span></span>  
  
 <span data-ttu-id="53b20-125">Para usar el espacio de nombres predeterminado, omita el prefijo y los dos puntos de la declaración en el elemento:</span><span class="sxs-lookup"><span data-stu-id="53b20-125">To use the default namespace, omit the prefix and the colon from the declaration on the element:</span></span>  
  
```xml  
<BOOK xmlns="http://www.contoso.com/books.dtd">  
...
</BOOK>
```  
  
## <a name="managing-namespaces"></a><span data-ttu-id="53b20-126">Administrar los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="53b20-126">Managing namespaces</span></span>  
 <span data-ttu-id="53b20-127">La clase <xref:System.Xml.XmlNamespaceManager> almacena una colección de URI del espacio de nombres y sus prefijos y permite buscar, agregar y quitar los espacios de nombres en esta colección.</span><span class="sxs-lookup"><span data-stu-id="53b20-127">The <xref:System.Xml.XmlNamespaceManager> class stores a collection of namespace URIs and their prefixes, and lets you look up, add, and remove namespaces from this collection.</span></span> <span data-ttu-id="53b20-128">En determinados contextos, esta clase es necesaria para obtener un mejor rendimiento del procesamiento XML.</span><span class="sxs-lookup"><span data-stu-id="53b20-128">In certain contexts, this class is required for better XML processing performance.</span></span> <span data-ttu-id="53b20-129">Por ejemplo, la clase <xref:System.Xml.Xsl.XsltContext> usa <xref:System.Xml.XmlNamespaceManager> para la compatibilidad con XPath.</span><span class="sxs-lookup"><span data-stu-id="53b20-129">For example, the <xref:System.Xml.Xsl.XsltContext> class uses <xref:System.Xml.XmlNamespaceManager> for XPath support.</span></span>  
  
 <span data-ttu-id="53b20-130">El administrador de espacios de nombres no realiza ninguna validación en los espacios de nombres, pero asume que ya se han comprobado los prefijos y los espacios de nombres y son compatibles con la especificación de [espacios de nombres de W3C](https://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="53b20-130">The namespace manager doesn't perform any validation on the namespaces, but assumes that prefixes and namespaces have already been verified and conform to the [W3C Namespaces](https://www.w3.org/TR/REC-xml-names/) specification.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53b20-131">LINQ to XML en [C#](../../linq/linq-xml-overview.md) y [Visual Basic](../../linq/linq-xml-overview.md) no utilizan <xref:System.Xml.XmlNamespaceManager> para administrar espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="53b20-131">LINQ TO XML in [C#](../../linq/linq-xml-overview.md) and [Visual Basic](../../linq/linq-xml-overview.md) don't use <xref:System.Xml.XmlNamespaceManager> to manage namespaces.</span></span> <span data-ttu-id="53b20-132">Vea [Working with XML Namespaces (C#)](../../linq/namespaces-overview.md) (Trabajo con espacios de nombres XML [C#]) y [Working with XML Namespaces (Visual Basic)](../../linq/namespaces-overview.md) (Trabajo con espacios de nombres XML [Visual Basic]) en la documentación de LINQ para obtener información sobre cómo administrar los espacios de nombres al usar LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="53b20-132">See [Working with XML Namespaces (C#)](../../linq/namespaces-overview.md) and [Working with XML Namespaces (Visual Basic)](../../linq/namespaces-overview.md) in the LINQ documentation for information about managing namespaces when using LINQ to XML.</span></span>  
  
 <span data-ttu-id="53b20-133">A continuación se detallan algunas de las tareas de administración y búsqueda que puede realizar con la clase <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="53b20-133">Here are some of the management and lookup tasks you can perform with the <xref:System.Xml.XmlNamespaceManager> class.</span></span> <span data-ttu-id="53b20-134">Para obtener más información y ejemplos, siga los vínculos a la página de referencia para cada método o propiedad.</span><span class="sxs-lookup"><span data-stu-id="53b20-134">For more information and examples, follow the links to the reference page for each method or property.</span></span>  
  
|<span data-ttu-id="53b20-135">En</span><span class="sxs-lookup"><span data-stu-id="53b20-135">To</span></span>|<span data-ttu-id="53b20-136">Usar</span><span class="sxs-lookup"><span data-stu-id="53b20-136">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="53b20-137">Agregar un espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="53b20-137">Add a namespace</span></span>|<span data-ttu-id="53b20-138">Método <xref:System.Xml.XmlNamespaceManager.AddNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-138"><xref:System.Xml.XmlNamespaceManager.AddNamespace%2A> method</span></span>|  
|<span data-ttu-id="53b20-139">Eliminar un espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="53b20-139">Remove a namespace</span></span>|<span data-ttu-id="53b20-140">Método <xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-140"><xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A> method</span></span>|  
|<span data-ttu-id="53b20-141">Encontrar el URI del espacio de nombres predeterminado</span><span class="sxs-lookup"><span data-stu-id="53b20-141">Find the URI for the default namespace</span></span>|<span data-ttu-id="53b20-142">Propiedad<xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-142"><xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A> property</span></span>|  
|<span data-ttu-id="53b20-143">Encontrar el URI de un prefijo de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="53b20-143">Find the URI for a namespace prefix</span></span>|<span data-ttu-id="53b20-144">Método <xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-144"><xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A> method</span></span>|  
|<span data-ttu-id="53b20-145">Encontrar el prefijo de un URI del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="53b20-145">Find the prefix for a namespace URI</span></span>|<span data-ttu-id="53b20-146">Método <xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-146"><xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A> method</span></span>|  
|<span data-ttu-id="53b20-147">Obtener una lista de espacios de nombres del nodo actual</span><span class="sxs-lookup"><span data-stu-id="53b20-147">Get a list of namespaces in the current node</span></span>|<span data-ttu-id="53b20-148">Método <xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-148"><xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A> method</span></span>|  
|<span data-ttu-id="53b20-149">Asignar un ámbito a un espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="53b20-149">Scope a namespace</span></span>|<span data-ttu-id="53b20-150">Métodos <xref:System.Xml.XmlNamespaceManager.PushScope%2A> y <xref:System.Xml.XmlNamespaceManager.PopScope%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-150"><xref:System.Xml.XmlNamespaceManager.PushScope%2A> and <xref:System.Xml.XmlNamespaceManager.PopScope%2A> methods</span></span>|  
|<span data-ttu-id="53b20-151">Comprobar si un prefijo está definido en el ámbito actual</span><span class="sxs-lookup"><span data-stu-id="53b20-151">Check whether a prefix is defined in the current scope</span></span>|<span data-ttu-id="53b20-152">Método <xref:System.Xml.XmlNamespaceManager.HasNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-152"><xref:System.Xml.XmlNamespaceManager.HasNamespace%2A> method</span></span>|  
|<span data-ttu-id="53b20-153">Obtener la tabla de nombres usada para buscar prefijos e identificadores URI</span><span class="sxs-lookup"><span data-stu-id="53b20-153">Get the name table used to look up prefixes and URIs</span></span>|<span data-ttu-id="53b20-154">Propiedad<xref:System.Xml.XmlNamespaceManager.NameTable%2A></span><span class="sxs-lookup"><span data-stu-id="53b20-154"><xref:System.Xml.XmlNamespaceManager.NameTable%2A> property</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53b20-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="53b20-155">See also</span></span>

- <xref:System.Xml.XmlNamespaceManager>
- [<span data-ttu-id="53b20-156">Documentos y datos XML</span><span class="sxs-lookup"><span data-stu-id="53b20-156">XML Documents and Data</span></span>](index.md)
