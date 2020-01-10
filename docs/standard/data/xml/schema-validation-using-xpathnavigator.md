---
title: Validación de esquemas con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 81fa0e41-d9c9-46f0-b22b-50da839c77f5
ms.openlocfilehash: bfcbf7306e896af54808c49e25f95d0631f5bcc0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710211"
---
# <a name="schema-validation-using-xpathnavigator"></a><span data-ttu-id="db3a2-102">Validación de esquemas con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="db3a2-102">Schema Validation using XPathNavigator</span></span>
<span data-ttu-id="db3a2-103">Con la clase <xref:System.Xml.XmlDocument>, puede validar el contenido XML de un objeto <xref:System.Xml.XmlDocument> de dos formas.</span><span class="sxs-lookup"><span data-stu-id="db3a2-103">Using the <xref:System.Xml.XmlDocument> class, you can validate the XML content contained in an <xref:System.Xml.XmlDocument> object in two ways.</span></span> <span data-ttu-id="db3a2-104">La primera forma sirve para validar el contenido XML utilizando un objeto <xref:System.Xml.XmlReader> de validación y, la segunda, consiste en utilizar el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-104">The first way is to validate the XML content using a validating <xref:System.Xml.XmlReader> object and the second way is to use the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="db3a2-105">También se puede realizar una validación de solo lectura del contenido XML utilizando la clase <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-105">You can also perform read-only validation of XML content using the <xref:System.Xml.XPath.XPathDocument> class.</span></span>  
  
## <a name="validating-xml-data"></a><span data-ttu-id="db3a2-106">Validación de datos XML</span><span class="sxs-lookup"><span data-stu-id="db3a2-106">Validating XML Data</span></span>  
 <span data-ttu-id="db3a2-107">La clase <xref:System.Xml.XmlDocument> no valida un documento XML utilizando una DTD o una validación de esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="db3a2-107">The <xref:System.Xml.XmlDocument> class does not validate an XML document using either DTD or XML schema definition language (XSD) schema validation by default.</span></span> <span data-ttu-id="db3a2-108">Solo comprueba que el documento XML sea correcto.</span><span class="sxs-lookup"><span data-stu-id="db3a2-108">It only verifies that the XML document is well formed.</span></span>  
  
 <span data-ttu-id="db3a2-109">La primera forma de validar un documento XML consiste en validarlo a medida que se carga en un objeto <xref:System.Xml.XmlDocument> utilizando un objeto <xref:System.Xml.XmlReader> de validación.</span><span class="sxs-lookup"><span data-stu-id="db3a2-109">The first way to validate an XML document is to validate the document as it is loaded into an <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="db3a2-110">La segunda forma consiste en validar un documento XML que previamente no tenga información de tipos utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-110">The second way is to validate a previously untyped XML document using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="db3a2-111">En ambos casos, se pueden volver a validar los cambios realizados en el documento XML utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-111">In both cases, changes to the validated XML document can be revalidated using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
### <a name="validating-a-document-as-it-is-loaded"></a><span data-ttu-id="db3a2-112">Validación de un documento a medida que se carga</span><span class="sxs-lookup"><span data-stu-id="db3a2-112">Validating a Document as it is Loaded</span></span>  
 <span data-ttu-id="db3a2-113">Para crear un objeto <xref:System.Xml.XmlReader> de validación, se pasa un objeto <xref:System.Xml.XmlReaderSettings> al método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> que toma un objeto <xref:System.Xml.XmlReaderSettings> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="db3a2-113">A validating <xref:System.Xml.XmlReader> object is created by passing an <xref:System.Xml.XmlReaderSettings> object to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class that takes an <xref:System.Xml.XmlReaderSettings> object as a parameter.</span></span> <span data-ttu-id="db3a2-114">El objeto <xref:System.Xml.XmlReaderSettings> que se pasa como parámetro tiene la propiedad <xref:System.Xml.XmlReaderSettings.ValidationType%2A> establecida en `Schema` y un esquema XML para el documento XML contenido en el objeto <xref:System.Xml.XmlDocument> que se ha agregado a su propiedad <xref:System.Xml.XmlReaderSettings.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-114">The <xref:System.Xml.XmlReaderSettings> object passed as a parameter has a <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property set to `Schema` and an XML Schema for the XML document contained in the <xref:System.Xml.XmlDocument> object added to its <xref:System.Xml.XmlReaderSettings.Schemas%2A> property.</span></span> <span data-ttu-id="db3a2-115">A continuación, el objeto <xref:System.Xml.XmlReader> de validación se utiliza para crear el objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-115">The validating <xref:System.Xml.XmlReader> object is then used to create the <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="db3a2-116">En el siguiente ejemplo se valida el archivo `contosoBooks.xml` a medida que se carga en el objeto <xref:System.Xml.XmlDocument> creando el objeto <xref:System.Xml.XmlDocument> utilizando un objeto <xref:System.Xml.XmlReader> de validación.</span><span class="sxs-lookup"><span data-stu-id="db3a2-116">The following example validates the `contosoBooks.xml` file as it is loaded into the <xref:System.Xml.XmlDocument> object by creating the <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="db3a2-117">Dado que el documento XML es válido de acuerdo con su esquema, no se genera ninguna advertencia ni error de validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="db3a2-117">Because the XML document is valid according to its schema, no schema validation errors or warnings are generated.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="db3a2-118">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="db3a2-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="db3a2-119">En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="db3a2-119">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 <span data-ttu-id="db3a2-120">En el ejemplo anterior, si un atributo o tipo de elemento no se corresponde con el tipo especificado en el esquema de validación, se producirá una <xref:System.Xml.Schema.XmlSchemaValidationException> cuando se llame a <xref:System.Xml.XmlDocument.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-120">In the above example, an <xref:System.Xml.Schema.XmlSchemaValidationException> will be thrown when <xref:System.Xml.XmlDocument.Load%2A> is called if any attribute or element type does not match the corresponding type specified in the validating schema.</span></span> <span data-ttu-id="db3a2-121">Si se establece un <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> en la validación de <xref:System.Xml.XmlReader>, se llamará al <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> siempre que se encuentre un tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="db3a2-121">If a <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> is set on the validating <xref:System.Xml.XmlReader>, the <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> will get called whenever an invalid type is encountered.</span></span>  
  
 <span data-ttu-id="db3a2-122">Se producirá una <xref:System.Xml.Schema.XmlSchemaException> siempre que el <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> obtenga acceso a un atributo o elemento con `invalid` establecido en <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-122">An <xref:System.Xml.Schema.XmlSchemaException> will be thrown when an attribute or element with <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> set to `invalid` is accessed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="db3a2-123">La propiedad <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> se puede utilizar para determinar si un elemento o atributo en particular es válido cuando se obtiene acceso a atributos o elementos con el <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-123">The <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> property can be used to determine whether or not an individual attribute or element is valid when accessing attributes or elements with the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db3a2-124">Cuando se carga un documento XML en un objeto <xref:System.Xml.XmlDocument> con un esquema asociado que define valores predeterminados, el objeto <xref:System.Xml.XmlDocument> trata estos valores predeterminados como si aparecieran en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="db3a2-124">When an XML document is loaded into an <xref:System.Xml.XmlDocument> object with an associated schema that defines default values, the <xref:System.Xml.XmlDocument> object treats these defaults as if they appeared in the XML document.</span></span> <span data-ttu-id="db3a2-125">Esto significa que la propiedad <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> siempre devuelve `false` para un elemento que utilice los valores predeterminados de un esquema, incluso aunque el documento XML se hubiera escrito como un elemento vacío.</span><span class="sxs-lookup"><span data-stu-id="db3a2-125">This means that the <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> property  always returns `false` for an element that was defaulted from the schema, even if in the XML document it was written as an empty element.</span></span>  
  
### <a name="validating-a-document-using-the-validate-method"></a><span data-ttu-id="db3a2-126">Validación de un documento con el método Validate</span><span class="sxs-lookup"><span data-stu-id="db3a2-126">Validating a Document using the Validate Method</span></span>  
 <span data-ttu-id="db3a2-127">El método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument> valida el documento XML contenido en un objeto <xref:System.Xml.XmlDocument> con los esquemas que se especifican en la propiedad <xref:System.Xml.XmlDocument> del objeto <xref:System.Xml.XmlDocument.Schemas%2A> y aumenta el conjunto de información.</span><span class="sxs-lookup"><span data-stu-id="db3a2-127">The <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class validates the XML document contained in an <xref:System.Xml.XmlDocument> object against the schemas specified in the <xref:System.Xml.XmlDocument> object's <xref:System.Xml.XmlDocument.Schemas%2A> property and performs infoset augmentation.</span></span> <span data-ttu-id="db3a2-128">El resultado es que se reemplaza un documento XML que previamente no tiene información de tipos del objeto <xref:System.Xml.XmlDocument> por un documento con información de tipos.</span><span class="sxs-lookup"><span data-stu-id="db3a2-128">The result is a previously untyped XML document in the <xref:System.Xml.XmlDocument> object replaced with a typed document.</span></span>  
  
 <span data-ttu-id="db3a2-129">El objeto <xref:System.Xml.XmlDocument> notifica los errores y advertencias de validación de esquemas utilizando el delegado <xref:System.Xml.Schema.ValidationEventHandler> que se pasa como parámetro al método <xref:System.Xml.XmlDocument.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-129">The <xref:System.Xml.XmlDocument> object reports schema validation errors and warnings using the <xref:System.Xml.Schema.ValidationEventHandler> delegate passed as a parameter to the <xref:System.Xml.XmlDocument.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="db3a2-130">En el siguiente ejemplo se valida el archivo `contosoBooks.xml` contenido en el objeto <xref:System.Xml.XmlDocument> con el esquema `contosoBooks.xsd` contenido en la propiedad <xref:System.Xml.XmlDocument> del objeto <xref:System.Xml.XmlDocument.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-130">The following example validates the `contosoBooks.xml` file contained in the <xref:System.Xml.XmlDocument> object against the `contosoBooks.xsd` schema contained in the <xref:System.Xml.XmlDocument> object's <xref:System.Xml.XmlDocument.Schemas%2A> property.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidateExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Dim document As XmlDocument = New XmlDocument()  
        document.Load("contosoBooks.xml")  
        Dim navigator As XPathNavigator = document.CreateNavigator()  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
        Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
        document.Validate(validation)  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidateExample  
{  
    static void Main(string[] args)  
    {  
        XmlDocument document = new XmlDocument();  
        document.Load("contosoBooks.xml");  
        XPathNavigator navigator = document.CreateNavigator();  
  
        document.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
        ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
        document.Validate(validation);  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="db3a2-131">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="db3a2-131">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="db3a2-132">En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="db3a2-132">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
### <a name="validating-modifications"></a><span data-ttu-id="db3a2-133">Validación de modificaciones</span><span class="sxs-lookup"><span data-stu-id="db3a2-133">Validating Modifications</span></span>  
 <span data-ttu-id="db3a2-134">Después de realizar modificaciones en un documento XML, puede validarlas con el esquema del documento XML utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-134">After modifications are made to an XML document, you can validate the modifications against the schema for the XML document using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="db3a2-135">En el siguiente ejemplo se valida el archivo `contosoBooks.xml` a medida que se carga en el objeto <xref:System.Xml.XmlDocument> creando el objeto <xref:System.Xml.XmlDocument> utilizando un objeto <xref:System.Xml.XmlReader> de validación.</span><span class="sxs-lookup"><span data-stu-id="db3a2-135">The following example validates the `contosoBooks.xml` file as it is loaded into the <xref:System.Xml.XmlDocument> object by creating the <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="db3a2-136">El documento XML se valida correctamente a medida que se carga sin generar ningún error ni advertencia de validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="db3a2-136">The XML document is validated successfully as it is loaded without generating any schema validation errors or warnings.</span></span> <span data-ttu-id="db3a2-137">A continuación, el ejemplo realiza dos modificaciones en el documento XML que no son válidas de acuerdo con el esquema `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="db3a2-137">The example then makes two modifications to the XML document that are invalid according to the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="db3a2-138">La primera modificación inserta un elemento secundario no válido que produce un error de validación del esquema, y la segunda modificación establece el valor de un nodo con información de tipos en un valor que no es válido de acuerdo con el tipo de nodo, lo cual produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="db3a2-138">The first modification inserts an invalid child element resulting in a schema validation error, and the second modification sets the value of a typed node to a value that is invalid according to the type of the node resulting in an exception.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Schema  
Imports System.Xml.XPath  
  
Class ValidatingReaderExample  
  
    Shared Sub Main(ByVal args() As String)  
  
        Try  
            Dim settings As XmlReaderSettings = New XmlReaderSettings()  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
            settings.ValidationType = ValidationType.Schema  
  
            Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
            Dim document As XmlDocument = New XmlDocument()  
            document.Load(reader)  
            Dim navigator As XPathNavigator = document.CreateNavigator()  
  
            Dim validation As ValidationEventHandler = New ValidationEventHandler(AddressOf SchemaValidationHandler)  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
            navigator.MoveToChild("book", "http://www.contoso.com/books")  
            navigator.MoveToChild("author", "http://www.contoso.com/books")  
  
            navigator.AppendChild("<title>Book Title</title>")  
  
            document.Validate(validation)  
  
            navigator.MoveToParent()  
            navigator.MoveToChild("price", "http://www.contoso.com/books")  
            navigator.SetTypedValue(DateTime.Now)  
        Catch e As Exception  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message)  
        End Try  
  
    End Sub  
  
    Shared Sub SchemaValidationHandler(ByVal sender As Object, ByVal e As ValidationEventArgs)  
  
        Select Case e.Severity  
            Case XmlSeverityType.Error  
                Console.WriteLine("Schema Validation Error: {0}", e.Message)  
                Exit Sub  
            Case XmlSeverityType.Warning  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message)  
                Exit Sub  
        End Select  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Schema;  
using System.Xml.XPath;  
  
class ValidatingReaderExample  
{  
    static void Main(string[] args)  
    {  
        try  
        {  
            XmlReaderSettings settings = new XmlReaderSettings();  
            settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
            settings.ValidationType = ValidationType.Schema;  
  
            XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
            XmlDocument document = new XmlDocument();  
            document.Load(reader);  
            XPathNavigator navigator = document.CreateNavigator();  
  
            ValidationEventHandler validation = new ValidationEventHandler(SchemaValidationHandler);  
  
            navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
            navigator.MoveToChild("book", "http://www.contoso.com/books");  
            navigator.MoveToChild("author", "http://www.contoso.com/books");  
  
            navigator.AppendChild("<title>Book Title</title>");  
  
            document.Validate(validation);  
  
            navigator.MoveToParent();  
            navigator.MoveToChild("price", "http://www.contoso.com/books");  
            navigator.SetTypedValue(DateTime.Now);  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("ValidatingReaderExample.Exception: {0}", e.Message);  
        }  
    }  
  
    static void SchemaValidationHandler(object sender, ValidationEventArgs e)  
    {  
        switch (e.Severity)  
        {  
            case XmlSeverityType.Error:  
                Console.WriteLine("Schema Validation Error: {0}", e.Message);  
                break;  
            case XmlSeverityType.Warning:  
                Console.WriteLine("Schema Validation Warning: {0}", e.Message);  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="db3a2-139">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="db3a2-139">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="db3a2-140">En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="db3a2-140">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 <span data-ttu-id="db3a2-141">En el ejemplo anterior se realizan dos modificaciones en el documento XML contenido en el objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-141">In the example above, two modifications are made to the XML document contained in the <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="db3a2-142">A medida que se fuera cargando el documento XML, el método del controlador de eventos de validación controlaría cualquier error de validación del esquema que se encontrara y lo escribiría en la consola.</span><span class="sxs-lookup"><span data-stu-id="db3a2-142">As the XML document was loaded, any schema validation errors encountered would have been handled by the validation event handler method and written to the console.</span></span>  
  
 <span data-ttu-id="db3a2-143">En este ejemplo los errores de validación se introdujeron después de cargar el documento XML y se encontraron utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-143">In this example, the validation errors were introduced after the XML document was loaded and were found using the <xref:System.Xml.XmlDocument.Validate%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="db3a2-144">Las modificaciones realizadas con el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> iniciaron una <xref:System.InvalidCastException> porque el nuevo valor no era válido de acuerdo con el tipo de esquema del nodo.</span><span class="sxs-lookup"><span data-stu-id="db3a2-144">Modifications made using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class resulted in an <xref:System.InvalidCastException> because the new value was invalid according to the schema type of the node.</span></span>  
  
 <span data-ttu-id="db3a2-145">Para obtener más información sobre la modificación de valores con el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, vea el tema [Modificación de datos XML con XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="db3a2-145">For more information about modifying values using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
### <a name="read-only-validation"></a><span data-ttu-id="db3a2-146">Validación de solo lectura</span><span class="sxs-lookup"><span data-stu-id="db3a2-146">Read-Only Validation</span></span>  
 <span data-ttu-id="db3a2-147">La clase <xref:System.Xml.XPath.XPathDocument> es una representación en memoria de solo lectura de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="db3a2-147">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory representation of an XML document.</span></span> <span data-ttu-id="db3a2-148">Tanto la clase <xref:System.Xml.XPath.XPathDocument> como la clase <xref:System.Xml.XmlDocument> crean objetos <xref:System.Xml.XPath.XPathNavigator> para navegar por documentos XML y editarlos.</span><span class="sxs-lookup"><span data-stu-id="db3a2-148">Both the <xref:System.Xml.XPath.XPathDocument> class and the <xref:System.Xml.XmlDocument> class create <xref:System.Xml.XPath.XPathNavigator> objects to navigate and edit XML documents.</span></span> <span data-ttu-id="db3a2-149">Dado que la clase <xref:System.Xml.XPath.XPathDocument> es de solo lectura, los objetos <xref:System.Xml.XPath.XPathNavigator> que devuelven los objetos <xref:System.Xml.XPath.XPathDocument> no pueden editar el documento XML contenido en el objeto <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="db3a2-149">Because the <xref:System.Xml.XPath.XPathDocument> class is a read-only class, <xref:System.Xml.XPath.XPathNavigator> object's returned from <xref:System.Xml.XPath.XPathDocument> objects cannot edit the XML document contained in the <xref:System.Xml.XPath.XPathDocument> object.</span></span>  
  
 <span data-ttu-id="db3a2-150">En caso de validación, puede crear un objeto <xref:System.Xml.XPath.XPathDocument> igual que crea un objeto <xref:System.Xml.XmlDocument> utilizando un objeto <xref:System.Xml.XmlReader> de validación, tal y como se ha descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="db3a2-150">In the case of validation, you can create an <xref:System.Xml.XPath.XPathDocument> object just like you create an <xref:System.Xml.XmlDocument> object using a validating <xref:System.Xml.XmlReader> object as described earlier in this topic.</span></span> <span data-ttu-id="db3a2-151">El objeto <xref:System.Xml.XPath.XPathDocument> valida el documento XML a medida que se carga, pero dado que no se pueden editar los datos XML en el objeto <xref:System.Xml.XPath.XPathDocument>, no se puede volver a validar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="db3a2-151">The <xref:System.Xml.XPath.XPathDocument> object validates the XML document as it is loaded, but because you cannot edit the XML data in the <xref:System.Xml.XPath.XPathDocument> object, you cannot revalidate the XML document.</span></span>  
  
 <span data-ttu-id="db3a2-152">Para más información sobre objetos <xref:System.Xml.XPath.XPathNavigator> editables y de solo lectura, vea el tema [Lectura de datos XML con XPathDocument y XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="db3a2-152">For more information about read-only and editable <xref:System.Xml.XPath.XPathNavigator> objects, see the [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3a2-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="db3a2-153">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="db3a2-154">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="db3a2-154">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="db3a2-155">Lectura de datos XML con XPathDocument y XmlDocument</span><span class="sxs-lookup"><span data-stu-id="db3a2-155">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="db3a2-156">Selección, evaluación y coincidencia de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="db3a2-156">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="db3a2-157">Acceso a datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="db3a2-157">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="db3a2-158">Edición de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="db3a2-158">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)
