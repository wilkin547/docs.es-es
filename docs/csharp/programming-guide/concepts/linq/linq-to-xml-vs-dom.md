---
title: LINQ to XML frente a DOM (C#)
ms.date: 07/20/2015
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: f6a89bba1ff2753f04406a060beb37bf2bf6552c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344794"
---
# <a name="linq-to-xml-vs-dom-c"></a><span data-ttu-id="dd641-102">LINQ to XML frente a DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="dd641-102">LINQ to XML vs. DOM (C#)</span></span>
<span data-ttu-id="dd641-103">En esta sección se describen algunas diferencias fundamentales entre [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] y la API de programación XML predominante actual, Document Object Model (DOM) W3C.</span><span class="sxs-lookup"><span data-stu-id="dd641-103">This section describes some key differences between [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>  
  
## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="dd641-104">Nuevas formas de crear árboles XML</span><span class="sxs-lookup"><span data-stu-id="dd641-104">New Ways to Construct XML Trees</span></span>  
 <span data-ttu-id="dd641-105">En DOM W3C, los árboles XML se crean de abajo arriba; es decir, se crea un documento, se crean elementos y, a continuación, se agregan los elementos al documento.</span><span class="sxs-lookup"><span data-stu-id="dd641-105">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>  
  
 <span data-ttu-id="dd641-106">Por ejemplo, a continuación se muestra una forma típica de crear un árbol XML usando la implementación de DOM de Microsoft, <xref:System.Xml.XmlDocument>:</span><span class="sxs-lookup"><span data-stu-id="dd641-106">For example, the following would be a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>:</span></span>  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
XmlElement phone1 = doc.CreateElement("Phone");  
phone1.SetAttribute("Type", "Home");  
phone1.InnerText = "206-555-0144";          
XmlElement phone2 = doc.CreateElement("Phone");  
phone2.SetAttribute("Type", "Work");  
phone2.InnerText = "425-555-0145";          
XmlElement street1 = doc.CreateElement("Street1");          
street1.InnerText = "123 Main St";  
XmlElement city = doc.CreateElement("City");  
city.InnerText = "Mercer Island";  
XmlElement state = doc.CreateElement("State");  
state.InnerText = "WA";  
XmlElement postal = doc.CreateElement("Postal");  
postal.InnerText = "68042";  
XmlElement address = doc.CreateElement("Address");  
address.AppendChild(street1);  
address.AppendChild(city);  
address.AppendChild(state);  
address.AppendChild(postal);  
XmlElement contact = doc.CreateElement("Contact");  
contact.AppendChild(name);  
contact.AppendChild(phone1);  
contact.AppendChild(phone2);  
contact.AppendChild(address);  
XmlElement contacts = doc.CreateElement("Contacts");  
contacts.AppendChild(contact);  
doc.AppendChild(contacts);  
```  
  
 <span data-ttu-id="dd641-107">Este estilo de codificación no proporciona mucha información visual acerca de la estructura del árbol XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-107">This style of coding does not visually provide much information about the structure of the XML tree.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-108">admite este enfoque para crear un árbol XML, pero también admite un enfoque alternativo, la *construcción funcional*.</span><span class="sxs-lookup"><span data-stu-id="dd641-108">supports this approach to constructing an XML tree, but also supports an alternative approach, *functional construction*.</span></span> <span data-ttu-id="dd641-109">La construcción funcional usa los constructores <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute> para crear un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-109">Functional construction uses the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors to build an XML tree.</span></span>  
  
 <span data-ttu-id="dd641-110">A continuación se muestra cómo se crea el mismo árbol XML mediante la construcción funcional [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dd641-110">Here is how you would construct the same XML tree by using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] functional construction:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144",   
                new XAttribute("Type", "Home")),  
            new XElement("phone", "425-555-0145",  
                new XAttribute("Type", "Work")),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="dd641-111">Tenga en cuenta que si se aplica la sangría al código para crear el árbol XML, se mostrará la estructura XML subyacente.</span><span class="sxs-lookup"><span data-stu-id="dd641-111">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span>  
  
 <span data-ttu-id="dd641-112">Para obtener más información, vea [Creating XML Trees (C#)](./linq-to-xml-overview.md) (Crear árboles XML (C#))</span><span class="sxs-lookup"><span data-stu-id="dd641-112">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
## <a name="working-directly-with-xml-elements"></a><span data-ttu-id="dd641-113">Trabajar directamente con elementos XML</span><span class="sxs-lookup"><span data-stu-id="dd641-113">Working Directly with XML Elements</span></span>  
 <span data-ttu-id="dd641-114">La programación con XML suele centrarse en elementos XML y quizás en los atributos.</span><span class="sxs-lookup"><span data-stu-id="dd641-114">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="dd641-115">En [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se puede trabajar directamente con atributos y elementos XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-115">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="dd641-116">Por ejemplo, puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd641-116">For example, you can do the following:</span></span>  
  
- <span data-ttu-id="dd641-117">Crear elementos XML sin usar un objeto de documento.</span><span class="sxs-lookup"><span data-stu-id="dd641-117">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="dd641-118">Esto simplifica la programación cuando se tiene que trabajar con fragmentos de árboles XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-118">This simplifies programming when you have to work with fragments of XML trees.</span></span>  
  
- <span data-ttu-id="dd641-119">Cargar objetos `T:System.Xml.Linq.XElement` directamente de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-119">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>  
  
- <span data-ttu-id="dd641-120">Serializar objetos `T:System.Xml.Linq.XElement` a un archivo o una secuencia.</span><span class="sxs-lookup"><span data-stu-id="dd641-120">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>  
  
 <span data-ttu-id="dd641-121">Compare esto con modelo DOM del consorcio W3C, en el que el documento XML se usa como contenedor lógico para el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-121">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="dd641-122">En DOM, los nodos XML, incluyendo elementos y atributos, se deben crear en el contexto de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-122">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="dd641-123">A continuación se muestra un fragmento del código para crear un nombre de elemento en DOM:</span><span class="sxs-lookup"><span data-stu-id="dd641-123">Here is a fragment of the code to create a name element in DOM:</span></span>  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 <span data-ttu-id="dd641-124">Si desea usar un elemento en varios documentos, debe importar los nodos en los documentos.</span><span class="sxs-lookup"><span data-stu-id="dd641-124">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-125">evita este grado de complejidad.</span><span class="sxs-lookup"><span data-stu-id="dd641-125">avoids this layer of complexity.</span></span>  
  
 <span data-ttu-id="dd641-126">Cuando se utiliza LINQ to XML, se usa la clase <xref:System.Xml.Linq.XDocument> solamente si se desea agregar un comentario o una instrucción de procesamiento en el nivel de raíz del documento.</span><span class="sxs-lookup"><span data-stu-id="dd641-126">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="dd641-127">Control simplificado de nombres y espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="dd641-127">Simplified Handling of Names and Namespaces</span></span>  
 <span data-ttu-id="dd641-128">Controlar nombres, espacios de nombres y prefijos de espacios de nombres suele ser una parte compleja de la programación XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-128">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-129">simplifica los nombres y los espacios de nombres al eliminar el requisito de tener que tratar con prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="dd641-129">simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="dd641-130">Si lo desea, puede controlar los prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="dd641-130">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="dd641-131">Pero si decide no controlar explícitamente los prefijos de espacios de nombres, durante la serialización [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] asignará prefijos de espacios de nombres si son necesarios, o serializará con espacios de nombres predeterminados si no lo son.</span><span class="sxs-lookup"><span data-stu-id="dd641-131">But if you decide to not explicitly control namespace prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will assign namespace prefixes during serialization if they are required, or will serialize using default namespaces if they are not.</span></span> <span data-ttu-id="dd641-132">Si se usan espacios de nombres predeterminados, no habrá prefijos de espacios de nombres en el documento resultante.</span><span class="sxs-lookup"><span data-stu-id="dd641-132">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="dd641-133">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="dd641-133">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="dd641-134">Otro problema de DOM consiste en que no permite cambiar el nombre de un nodo.</span><span class="sxs-lookup"><span data-stu-id="dd641-134">Another problem with the DOM is that it does not let you change the name of a node.</span></span> <span data-ttu-id="dd641-135">Por el contrario, hay que crear un nuevo nodo y copiar en él todos los nodos secundarios, por lo que se pierde la identidad del nodo original.</span><span class="sxs-lookup"><span data-stu-id="dd641-135">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-136">evita este problema al permitir que se establezca la propiedad <xref:System.Xml.Linq.XName> en un nodo.</span><span class="sxs-lookup"><span data-stu-id="dd641-136">avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>  
  
## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="dd641-137">Compatibilidad con el método estático para cargar XML</span><span class="sxs-lookup"><span data-stu-id="dd641-137">Static Method Support for Loading XML</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-138">permite cargar XML mediante métodos estáticos en lugar de métodos de instancia.</span><span class="sxs-lookup"><span data-stu-id="dd641-138">lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="dd641-139">Esto simplifica la carga y el análisis.</span><span class="sxs-lookup"><span data-stu-id="dd641-139">This simplifies loading and parsing.</span></span> <span data-ttu-id="dd641-140">Para más información, consulte [Procedimiento para cargar un documento XML desde un archivo (C#)](./how-to-load-xml-from-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="dd641-140">For more information, see [How to load XML from a file (C#)](./how-to-load-xml-from-a-file.md).</span></span>  
  
## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="dd641-141">Eliminación de la compatibilidad con construcciones DTD</span><span class="sxs-lookup"><span data-stu-id="dd641-141">Removal of Support for DTD Constructs</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-142">simplifica aún más la programación XML quitando la compatibilidad con entidades y referencias a entidades.</span><span class="sxs-lookup"><span data-stu-id="dd641-142">further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="dd641-143">La administración de entidades es compleja y su uso es muy poco común.</span><span class="sxs-lookup"><span data-stu-id="dd641-143">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="dd641-144">La eliminación de la compatibilidad aumenta el rendimiento y simplifica la interfaz de programación.</span><span class="sxs-lookup"><span data-stu-id="dd641-144">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="dd641-145">Cuando se rellena un árbol de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se expanden todas las entidades DTD.</span><span class="sxs-lookup"><span data-stu-id="dd641-145">When a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tree is populated, all DTD entities are expanded.</span></span>  
  
## <a name="support-for-fragments"></a><span data-ttu-id="dd641-146">Compatibilidad con fragmentos</span><span class="sxs-lookup"><span data-stu-id="dd641-146">Support for Fragments</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-147">no proporciona un equivalente para la clase `XmlDocumentFragment`.</span><span class="sxs-lookup"><span data-stu-id="dd641-147">does not provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="dd641-148">En cambio, es bastante común que el concepto `XmlDocumentFragment` se pueda controlar mediante el resultado de una consulta que se escribe como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XNode> o <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="dd641-148">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that is typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="support-for-xpathnavigator"></a><span data-ttu-id="dd641-149">Compatibilidad con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="dd641-149">Support for XPathNavigator</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-150">proporciona compatibilidad con <xref:System.Xml.XPath.XPathNavigator> mediante los métodos de extensión del espacio de nombres <xref:System.Xml.XPath?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd641-150">provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="dd641-151">Para obtener más información, vea <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd641-151">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="dd641-152">Compatibilidad con espacios en blanco y sangría</span><span class="sxs-lookup"><span data-stu-id="dd641-152">Support for White Space and Indentation</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-153">trata los espacios en blanco de forma más sencilla que DOM.</span><span class="sxs-lookup"><span data-stu-id="dd641-153">handles white space more simply than the DOM.</span></span>  
  
 <span data-ttu-id="dd641-154">Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin preservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y éste se guarda con sangría.</span><span class="sxs-lookup"><span data-stu-id="dd641-154">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="dd641-155">Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos.</span><span class="sxs-lookup"><span data-stu-id="dd641-155">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="dd641-156">Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd641-156">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="dd641-157">Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada.</span><span class="sxs-lookup"><span data-stu-id="dd641-157">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="dd641-158">Es posible que no desee modificar esta sangría de ninguna forma.</span><span class="sxs-lookup"><span data-stu-id="dd641-158">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="dd641-159">En [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede conseguirlo si preserva los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.</span><span class="sxs-lookup"><span data-stu-id="dd641-159">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can do this by preserving white space when you load or parse the XML and disabling formatting when you serialize the XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-160">almacena un espacio en blanco como un nodo <xref:System.Xml.Linq.XText>, en lugar de tener un tipo de nodo <xref:System.Xml.XmlNodeType.Whitespace> especializado, al igual que DOM.</span><span class="sxs-lookup"><span data-stu-id="dd641-160">stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType.Whitespace> node type, as the DOM does.</span></span>  
  
## <a name="support-for-annotations"></a><span data-ttu-id="dd641-161">Compatibilidad con anotaciones</span><span class="sxs-lookup"><span data-stu-id="dd641-161">Support for Annotations</span></span>  
 <span data-ttu-id="dd641-162">Los elementos de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] admiten un conjunto extensible de anotaciones.</span><span class="sxs-lookup"><span data-stu-id="dd641-162">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] elements support an extensible set of annotations.</span></span> <span data-ttu-id="dd641-163">Esto puede resultar útil para realizar un seguimiento de información diversa de un elemento, como la información de esquema, información acerca de si un elemento está enlazado a una interfaz de usuario o cualquier otro tipo de información específica de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd641-163">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="dd641-164">Para obtener más información, vea [Anotaciones en LINQ to XML](./linq-to-xml-annotations.md).</span><span class="sxs-lookup"><span data-stu-id="dd641-164">For more information, see [LINQ to XML Annotations](./linq-to-xml-annotations.md).</span></span>  
  
## <a name="support-for-schema-information"></a><span data-ttu-id="dd641-165">Compatibilidad con la información de esquema</span><span class="sxs-lookup"><span data-stu-id="dd641-165">Support for Schema Information</span></span>  
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd641-166">proporciona compatibilidad con la validación XSD mediante métodos de extensión en el espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd641-166">provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="dd641-167">Puede validar que un árbol XML sea compatible con un XSD.</span><span class="sxs-lookup"><span data-stu-id="dd641-167">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="dd641-168">Puede rellenar el árbol XML con el conjunto de información posterior a la validación del esquema (PSVI).</span><span class="sxs-lookup"><span data-stu-id="dd641-168">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="dd641-169">Para más información, consulte [Procedimiento para validar con XSD (LINQ to XML) (C#)](./how-to-validate-using-xsd-linq-to-xml.md) y <xref:System.Xml.Schema.Extensions>.</span><span class="sxs-lookup"><span data-stu-id="dd641-169">For more information, see [How to validate using XSD](./how-to-validate-using-xsd-linq-to-xml.md) and <xref:System.Xml.Schema.Extensions>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd641-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd641-170">See also</span></span>

- [<span data-ttu-id="dd641-171">Introducción (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="dd641-171">Getting Started (LINQ to XML)</span></span>](./linq-to-xml-overview.md)
