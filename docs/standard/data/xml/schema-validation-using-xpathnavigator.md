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
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710211"
---
# <a name="schema-validation-using-xpathnavigator"></a>Validación de esquemas con XPathNavigator
Con la clase <xref:System.Xml.XmlDocument>, puede validar el contenido XML de un objeto <xref:System.Xml.XmlDocument> de dos formas. La primera forma sirve para validar el contenido XML utilizando un objeto <xref:System.Xml.XmlReader> de validación y, la segunda, consiste en utilizar el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>. También se puede realizar una validación de solo lectura del contenido XML utilizando la clase <xref:System.Xml.XPath.XPathDocument>.  
  
## <a name="validating-xml-data"></a>Validación de datos XML  
 La clase <xref:System.Xml.XmlDocument> no valida un documento XML utilizando una DTD o una validación de esquema del lenguaje de definición de esquemas XML (XSD). Solo comprueba que el documento XML sea correcto.  
  
 La primera forma de validar un documento XML consiste en validarlo a medida que se carga en un objeto <xref:System.Xml.XmlDocument> utilizando un objeto <xref:System.Xml.XmlReader> de validación. La segunda forma consiste en validar un documento XML que previamente no tenga información de tipos utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>. En ambos casos, se pueden volver a validar los cambios realizados en el documento XML utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.  
  
### <a name="validating-a-document-as-it-is-loaded"></a>Validación de un documento a medida que se carga  
 Para crear un objeto <xref:System.Xml.XmlReader> de validación, se pasa un objeto <xref:System.Xml.XmlReaderSettings> al método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> que toma un objeto <xref:System.Xml.XmlReaderSettings> como parámetro. El objeto <xref:System.Xml.XmlReaderSettings> que se pasa como parámetro tiene la propiedad <xref:System.Xml.XmlReaderSettings.ValidationType%2A> establecida en `Schema` y un esquema XML para el documento XML contenido en el objeto <xref:System.Xml.XmlDocument> que se ha agregado a su propiedad <xref:System.Xml.XmlReaderSettings.Schemas%2A>. A continuación, el objeto <xref:System.Xml.XmlReader> de validación se utiliza para crear el objeto <xref:System.Xml.XmlDocument>.  
  
 En el siguiente ejemplo se valida el archivo `contosoBooks.xml` a medida que se carga en el objeto <xref:System.Xml.XmlDocument> creando el objeto <xref:System.Xml.XmlDocument> utilizando un objeto <xref:System.Xml.XmlReader> de validación. Dado que el documento XML es válido de acuerdo con su esquema, no se genera ninguna advertencia ni error de validación del esquema.  
  
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
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 En el ejemplo anterior, si un atributo o tipo de elemento no se corresponde con el tipo especificado en el esquema de validación, se producirá una <xref:System.Xml.Schema.XmlSchemaValidationException> cuando se llame a <xref:System.Xml.XmlDocument.Load%2A>. Si se establece un <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> en la validación de <xref:System.Xml.XmlReader>, se llamará al <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> siempre que se encuentre un tipo no válido.  
  
 Se producirá una <xref:System.Xml.Schema.XmlSchemaException> siempre que el <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> obtenga acceso a un atributo o elemento con `invalid` establecido en <xref:System.Xml.XPath.XPathNavigator>.  
  
 La propiedad <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> se puede utilizar para determinar si un elemento o atributo en particular es válido cuando se obtiene acceso a atributos o elementos con el <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
> Cuando se carga un documento XML en un objeto <xref:System.Xml.XmlDocument> con un esquema asociado que define valores predeterminados, el objeto <xref:System.Xml.XmlDocument> trata estos valores predeterminados como si aparecieran en el documento XML. Esto significa que la propiedad <xref:System.Xml.XPath.XPathNavigator.IsEmptyElement%2A> siempre devuelve `false` para un elemento que utilice los valores predeterminados de un esquema, incluso aunque el documento XML se hubiera escrito como un elemento vacío.  
  
### <a name="validating-a-document-using-the-validate-method"></a>Validación de un documento con el método Validate  
 El método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument> valida el documento XML contenido en un objeto <xref:System.Xml.XmlDocument> con los esquemas que se especifican en la propiedad <xref:System.Xml.XmlDocument> del objeto <xref:System.Xml.XmlDocument.Schemas%2A> y aumenta el conjunto de información. El resultado es que se reemplaza un documento XML que previamente no tiene información de tipos del objeto <xref:System.Xml.XmlDocument> por un documento con información de tipos.  
  
 El objeto <xref:System.Xml.XmlDocument> notifica los errores y advertencias de validación de esquemas utilizando el delegado <xref:System.Xml.Schema.ValidationEventHandler> que se pasa como parámetro al método <xref:System.Xml.XmlDocument.Validate%2A>.  
  
 En el siguiente ejemplo se valida el archivo `contosoBooks.xml` contenido en el objeto <xref:System.Xml.XmlDocument> con el esquema `contosoBooks.xsd` contenido en la propiedad <xref:System.Xml.XmlDocument> del objeto <xref:System.Xml.XmlDocument.Schemas%2A>.  
  
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
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
### <a name="validating-modifications"></a>Validación de modificaciones  
 Después de realizar modificaciones en un documento XML, puede validarlas con el esquema del documento XML utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.  
  
 En el siguiente ejemplo se valida el archivo `contosoBooks.xml` a medida que se carga en el objeto <xref:System.Xml.XmlDocument> creando el objeto <xref:System.Xml.XmlDocument> utilizando un objeto <xref:System.Xml.XmlReader> de validación. El documento XML se valida correctamente a medida que se carga sin generar ningún error ni advertencia de validación del esquema. A continuación, el ejemplo realiza dos modificaciones en el documento XML que no son válidas de acuerdo con el esquema `contosoBooks.xsd`. La primera modificación inserta un elemento secundario no válido que produce un error de validación del esquema, y la segunda modificación establece el valor de un nodo con información de tipos en un valor que no es válido de acuerdo con el tipo de nodo, lo cual produce una excepción.  
  
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
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
 En el ejemplo anterior se realizan dos modificaciones en el documento XML contenido en el objeto <xref:System.Xml.XmlDocument>. A medida que se fuera cargando el documento XML, el método del controlador de eventos de validación controlaría cualquier error de validación del esquema que se encontrara y lo escribiría en la consola.  
  
 En este ejemplo los errores de validación se introdujeron después de cargar el documento XML y se encontraron utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.  
  
 Las modificaciones realizadas con el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> iniciaron una <xref:System.InvalidCastException> porque el nuevo valor no era válido de acuerdo con el tipo de esquema del nodo.  
  
 Para obtener más información sobre la modificación de valores con el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, vea el tema [Modificación de datos XML con XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).  
  
### <a name="read-only-validation"></a>Validación de solo lectura  
 La clase <xref:System.Xml.XPath.XPathDocument> es una representación en memoria de solo lectura de un documento XML. Tanto la clase <xref:System.Xml.XPath.XPathDocument> como la clase <xref:System.Xml.XmlDocument> crean objetos <xref:System.Xml.XPath.XPathNavigator> para navegar por documentos XML y editarlos. Dado que la clase <xref:System.Xml.XPath.XPathDocument> es de solo lectura, los objetos <xref:System.Xml.XPath.XPathNavigator> que devuelven los objetos <xref:System.Xml.XPath.XPathDocument> no pueden editar el documento XML contenido en el objeto <xref:System.Xml.XPath.XPathDocument>.  
  
 En caso de validación, puede crear un objeto <xref:System.Xml.XPath.XPathDocument> igual que crea un objeto <xref:System.Xml.XmlDocument> utilizando un objeto <xref:System.Xml.XmlReader> de validación, tal y como se ha descrito anteriormente en este tema. El objeto <xref:System.Xml.XPath.XPathDocument> valida el documento XML a medida que se carga, pero dado que no se pueden editar los datos XML en el objeto <xref:System.Xml.XPath.XPathDocument>, no se puede volver a validar el documento XML.  
  
 Para más información sobre objetos <xref:System.Xml.XPath.XPathNavigator> editables y de solo lectura, vea el tema [Lectura de datos XML con XPathDocument y XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Lectura de datos XML con XPathDocument y XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [Selección, evaluación y coincidencia de datos XML con XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [Acceso a datos XML con XPathNavigator](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [Edición de datos XML con XPathNavigator](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)
