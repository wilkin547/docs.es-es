---
title: Deducción de esquemas a partir de documentos XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: f3d97d53-614d-4a04-a174-87965b7405f6
ms.openlocfilehash: 5b0f9bea33346083ce0015fbf3cdfeb0e0ea1181
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287667"
---
# <a name="inferring-schemas-from-xml-documents"></a>Deducción de esquemas a partir de documentos XML
Este tema describe cómo utilizar la clase <xref:System.Xml.Schema.XmlSchemaInference> para deducir un lenguaje de definición de esquema XML (XSD) a partir de la estructura de un documento XML.  
  
## <a name="the-schema-inference-process"></a>El proceso de deducción de esquema  
 La clase <xref:System.Xml.Schema.XmlSchemaInference> del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> se utiliza para generar uno o más lenguajes de definición de esquema XML (XSD) a partir de la estructura de un documento XML. Los esquemas generados podrían utilizarse para validar el documento XML original.  
  
 Mientras un documento XML es procesado por la clase <xref:System.Xml.Schema.XmlSchemaInference>, la clase <xref:System.Xml.Schema.XmlSchemaInference> hace suposiciones sobre los componentes de esquema que describen los elementos y atributos en el documento XML. La clase <xref:System.Xml.Schema.XmlSchemaInference> también deduce componentes de esquema de forma restrictiva deduciendo el tipo más restrictivo para un elemento o atributo particular. A medida que se reúne más información para el documento XML, estas restricciones se pierden deduciendo tipos menos restrictivos. El tipo menos restrictivo que puede deducirse es `xs:string`.  
  
 Tome, por ejemplo, el siguiente fragmento de documento XML.  
  
```xml  
<parent attribute1="6">  
    <child>One</child>  
    <child>Two</child>  
</parent>  
<parent attribute1="A" />
```  
  
 En el ejemplo de arriba, cuando el atributo `attribute1` se encuentra con un valor de `6` mediante el proceso <xref:System.Xml.Schema.XmlSchemaInference>, se asume que es del tipo `xs:unsignedByte`. Cuando el segundo elemento `parent` se encuentra mediante el proceso <xref:System.Xml.Schema.XmlSchemaInference>, la restricción se pierde modificando el tipo `xs:string` porque el valor del atributo `attribute1` es ahora `A`. De forma similar, el atributo `minOccurs` para todos los elementos `child` deducidos en el esquema se pierden a `minOccurs="0"` porque el segundo elemento primario no tiene elementos secundarios.  
  
## <a name="inferring-schemas-from-xml-documents"></a>Deducción de esquemas a partir de documentos XML  
 La clase <xref:System.Xml.Schema.XmlSchemaInference> utiliza dos métodos sobrecargados <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> para deducir un esquema a partir de un documento XML.  
  
 El primer método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> se utiliza para crear un esquema basado en un documento XML. El segundo método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> se utiliza para deducir un esquema que describa múltiples documentos XML. Por ejemplo, puede introducir múltiples documentos XML en el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> uno por uno para producir un esquema que describa el conjunto entero de documentos XML.  
  
 El primer método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> deduce un esquema a partir de un documento XML contenido en un objeto <xref:System.Xml.XmlReader>, y devuelve un objeto <xref:System.Xml.Schema.XmlSchemaSet> que contiene el esquema deducido. El segundo método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> busca un objeto <xref:System.Xml.Schema.XmlSchemaSet> para un esquema con el mismo espacio de nombres de destino que el documento XML contenido en el objeto <xref:System.Xml.XmlReader>, refina el esquema existente y devuelve un objeto <xref:System.Xml.Schema.XmlSchemaSet> que contiene el esquema deducido.  
  
 Los cambios realizados en el esquema refinado se basan en la nueva estructura encontrada en el documento XML. Por ejemplo, mientras se atraviesa un documento XML, se realizan suposiciones sobre los tipos de datos encontrados y el esquema se crea basándose en dichas suposiciones. No obstante, si los datos se encuentra en un segundo pase de deducción que difiere de la suposición original, el esquema se refina. En el ejemplo siguiente se muestra el proceso de refinamiento.  
  
 [!code-cpp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaInferenceExamples/CPP/XmlSchemaInferenceExamples.cpp#4)]
 [!code-csharp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaInferenceExamples/CS/XmlSchemaInferenceExamples.cs#4)]
 [!code-vb[XmlSchemaInferenceExamples#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaInferenceExamples/VB/XmlSchemaInferenceExamples.vb#4)]  
  
 El ejemplo toma el siguiente archivo, `item1.xml`, como su primera entrada.  
  
 [!code-xml[XmlSchemaInferenceExamples#13](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item1.xml#13)]  
  
 A continuación, toma el archivo `item2.xml` como su segunda entrada:  
  
 [!code-xml[XmlSchemaInferenceExamples#14](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item2.xml#14)]  
  
 Cuando se encuentra el atributo `productID` en el primer documento XML, el valor de `123456789` se asume que es de tipo `xs:unsignedInt`. Sin embargo, cuando se lee el segundo documento XML y se encuentra el valor de `A53-246`, el tipo `xs:unsignedInt` no puede asumirse más. El esquema se refina y el tipo de `productID` cambia a `xs:string`. Además, el atributo `minOccurs` para el elemento `supplierID` se establece en `0`, porque el segundo documento XML no contiene ningún elemento `supplierID`.  
  
 El siguiente es el esquema deducido a partir del primer documento XML.  
  
 [!code-xml[XmlSchemaInferenceExamples#15](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema1.xml#15)]  
  
 El siguiente es el esquema deducido a partir del primer documento XML, refinado mediante el segundo documento XML.  
  
 [!code-xml[XmlSchemaInferenceExamples#16](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema2.xml#16)]  
  
## <a name="inline-schemas"></a>Esquemas alineados  
 Si un lenguaje de definición de esquema XML alineado (XSD) se encuentra durante el proceso <xref:System.Xml.Schema.XmlSchemaInference>, se inicia <xref:System.Xml.Schema.XmlSchemaInferenceException>. Por ejemplo, el siguiente esquema alineado inicia <xref:System.Xml.Schema.XmlSchemaInferenceException>.  
  
```xml  
<root xmlns:ex="http://www.contoso.com" xmlns="http://www.tempuri.org">  
    <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://www.contoso.com">  
        <xs:element name="Contoso" type="xs:normalizedString" />  
    </xs:schema>  
    <ex:Contoso>Test</ex:Contoso>  
</root>  
```  
  
## <a name="schemas-that-cannot-be-refined"></a>Esquemas que no pueden refinarse  
 Existen construcciones de esquema XML de W3C que el proceso <xref:System.Xml.Schema.XmlSchemaInference> de lenguaje de definición de esquema XML (XSD) no puede controlar si se da un tipo para refinar y provoca que se inicie una excepción. Como un tipo complejo cuyo compositor de nivel superior es una secuencia. En el modelo de objeto de esquema (SOM), esto corresponde a <xref:System.Xml.Schema.XmlSchemaComplexType> cuya propiedad <xref:System.Xml.Schema.XmlSchemaComplexType.Particle%2A> no es una instancia de <xref:System.Xml.Schema.XmlSchemaSequence>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Schema.XmlSchemaInference>
- [Modelo de objetos de esquema XML (SOM)](xml-schema-object-model-som.md)
- [Deducción de esquema XML](inferring-an-xml-schema.md)
- [Reglas para deducir los tipos de nodo de esquema y estructura](rules-for-inferring-schema-node-types-and-structure.md)
- [Reglas para deducir tipos simples](rules-for-inferring-simple-types.md)
