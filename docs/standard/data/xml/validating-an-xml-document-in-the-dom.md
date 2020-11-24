---
title: Validación de un documento XML en el DOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2c61c920-d0f8-4c72-bfcc-6524570f3060
ms.openlocfilehash: db3748d1d0e1a5687219d5b07d1261639a4ef670
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819297"
---
# <a name="validating-an-xml-document-in-the-dom"></a>Validación de un documento XML en el DOM

La clase <xref:System.Xml.XmlDocument> no valida el código XML en el Modelo de objetos de documento (DOM) con un esquema del lenguaje de definición de esquemas XML (XSD) ni una definición de tipo de documento (DTD) de manera predeterminada; solo se comprueba si el código XML es correcto.

Para validar el código XML en el DOM, puede validarlo a medida que se carga en el DOM pasando un <xref:System.Xml.XmlReader> de validación de esquemas al método <xref:System.Xml.XmlDocument.Load%2A> de la clase <xref:System.Xml.XmlDocument>, o bien validar en el DOM un documento XML que no estuviera validado previamente utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>.

## <a name="validating-an-xml-document-as-it-is-loaded-into-the-dom"></a>Validación de un documento XML a medida que se carga en el DOM

La clase <xref:System.Xml.XmlDocument> valida los datos XML a medida que se cargan en el DOM cuando se pasa un <xref:System.Xml.XmlReader> de validación al método <xref:System.Xml.XmlDocument.Load%2A> de la clase <xref:System.Xml.XmlDocument>.

Después de realizar la validación correctamente, se aplican los valores predeterminados del esquema, los valores de texto se convierten en valores atómicos como sea preciso y la información de tipos se asocia a los elementos de información validados. Como resultado, los datos XML con tipo reemplazan a los datos XML sin tipo anteriores.

### <a name="creating-an-xml-schema-validating-xmlreader"></a>Creación de un XmlReader de validación de esquemas XML

Para crear un <xref:System.Xml.XmlReader> de validación de esquemas XML, siga estos pasos.

1. Cree una nueva instancia de <xref:System.Xml.XmlReaderSettings>.

2. Agregue un esquema XML a la propiedad <xref:System.Xml.XmlReaderSettings.Schemas%2A> de la instancia <xref:System.Xml.XmlReaderSettings>.

3. Especifique `Schema` como <xref:System.Xml.XmlReaderSettings.ValidationType%2A>.

4. Opcionalmente, especifique <xref:System.Xml.XmlReaderSettings.ValidationFlags%2A> y <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> para que controlen las advertencias y errores de validación de esquemas que se encuentren durante la validación.

5. Por último, pase el objeto <xref:System.Xml.XmlReaderSettings> al método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> junto con el documento XML, para crear un <xref:System.Xml.XmlReader> de validación de esquemas.

### <a name="example"></a>Ejemplo

En el siguiente código de ejemplo, un <xref:System.Xml.XmlReader> de validación de esquemas valida los datos XML cargados en el DOM. Se realizan modificaciones no válidas en el documento XML y, a continuación, dicho documento se vuelve a validar, lo que produce errores de validación del esquema. Por último, se corrige uno de los errores y, a continuación, se valida parcialmente parte del documento XML.

[!code-cpp[XmlDocumentValidation.Load#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlDocumentValidation.Load/CPP/XmlDocumentValidationExample.cpp#1)]
[!code-csharp[XmlDocumentValidation.Load#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlDocumentValidation.Load/CS/XmlDocumentValidationExample.cs#1)]
[!code-vb[XmlDocumentValidation.Load#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlDocumentValidation.Load/VB/XmlDocumentValidationExample.vb#1)]

En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.

[!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]

Tenga en cuenta lo siguiente a la hora de validar datos XML a medida que se cargan en el DOM.

- En el ejemplo anterior, se llama a <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> cada vez que se encuentra un tipo no válido. Si no se establece un <xref:System.Xml.XmlReaderSettings.ValidationEventHandler> en el <xref:System.Xml.XmlReader> de validación, se produce una excepción <xref:System.Xml.Schema.XmlSchemaValidationException> cuando se llama a <xref:System.Xml.XmlDocument.Load%2A> si algún atributo o tipo de elemento no se corresponde con el tipo especificado en el esquema de validación.

- Cuando se carga un documento XML en un objeto <xref:System.Xml.XmlDocument> con un esquema asociado que define valores predeterminados, <xref:System.Xml.XmlDocument> trata estos valores predeterminados como si aparecieran en el documento XML. Esto significa que la propiedad <xref:System.Xml.XmlReader.IsEmptyElement%2A> siempre devuelve `false` para un elemento que tenga los valores predeterminados del esquema. Aunque estuviera en el documento XML, se escribiría como un elemento vacío.

## <a name="validating-an-xml-document-in-the-dom"></a>Validación de un documento XML en el DOM

El método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument> valida los datos XML que se cargan en el DOM con los esquemas de la propiedad <xref:System.Xml.XmlDocument> del objeto <xref:System.Xml.XmlDocument.Schemas%2A>. Después de realizar la validación correctamente, se aplican los valores predeterminados del esquema, los valores de texto se convierten en valores atómicos como sea preciso y la información de tipos se asocia a los elementos de información validados. Como resultado, los datos XML con tipo reemplazan a los datos XML sin tipo anteriores.

El siguiente ejemplo es similar al ejemplo de la sección anterior "Validación de un documento XML a medida que se carga en el DOM". En este ejemplo, el documento XML no se valida a medida que se carga en el DOM, sino después de cargarlo en el DOM utilizando el método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>. El método <xref:System.Xml.XmlDocument.Validate%2A> valida el documento XML con los esquemas XML contenidos en la propiedad <xref:System.Xml.XmlDocument.Schemas%2A> de <xref:System.Xml.XmlDocument>. Luego, se realizan modificaciones no válidas en el documento XML y dicho documento se vuelve a validar, lo que produce errores de validación del esquema. Por último, se corrige uno de los errores y, a continuación, se valida parcialmente parte del documento XML.

[!code-csharp[XmlDocumentValidation.Validate#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlDocumentValidation.Validate/CS/XmlDocumentValidationExample.cs#1)]
[!code-vb[XmlDocumentValidation.Validate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlDocumentValidation.Validate/VB/XmlDocumentValidationExample.vb#1)]

En el ejemplo se toman como entrada los archivos `contosoBooks.xml` y `contosoBooks.xsd` que se mencionan en la sección anterior "Validación de un documento XML a medida que se carga en el DOM".

## <a name="handling-validation-errors-and-warnings"></a>Control de advertencias y errores de validación

Los errores de validación de esquemas XML se presentan durante la validación de datos XML cargados en el DOM. Todos los errores de validación de esquemas se le notifican mientras se validan los datos a medida que se cargan o cuando se valida un documento XML que no estuviera previamente validado.

<xref:System.Xml.Schema.ValidationEventHandler> controla los errores de validación. Si se ha asignado un <xref:System.Xml.Schema.ValidationEventHandler> a la instancia de <xref:System.Xml.XmlReaderSettings> o se ha pasado al método <xref:System.Xml.XmlDocument.Validate%2A> de la clase <xref:System.Xml.XmlDocument>, el <xref:System.Xml.Schema.ValidationEventHandler> controlará los errores de validación de esquemas; de lo contrario, se inicia una <xref:System.Xml.Schema.XmlSchemaValidationException> cuando se encuentra un error de validación de esquema.

> [!NOTE]
> Los datos XML se cargan en el DOM a pesar de los errores de validación de esquemas, a menos que <xref:System.Xml.Schema.ValidationEventHandler> inicie una excepción para detener el proceso.
>
> No se notifican advertencias de validación de esquemas a menos que se especifique la marca <xref:System.Xml.Schema.XmlSchemaValidationFlags.ReportValidationWarnings> para el objeto <xref:System.Xml.XmlReaderSettings>.

 Para ver ejemplos sobre <xref:System.Xml.Schema.ValidationEventHandler>, vea las secciones "Validación de un documento XML a medida que se carga en el DOM" y "Validación de un documento XML en el DOM".

## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XmlReader>
- <xref:System.Xml.Schema.ValidationEventHandler>
- <xref:System.Xml.XmlReaderSettings>
- [Procesamiento de datos XML con el modelo DOM](process-xml-data-using-the-dom-model.md)
- [Trabajo con esquemas XML](working-with-xml-schemas.md)
