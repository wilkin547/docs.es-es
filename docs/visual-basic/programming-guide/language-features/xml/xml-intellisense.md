---
title: XML IntelliSense en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, XML
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8c43db3d2010e4fa92eebeec8a973c50052b1340
ms.lasthandoff: 03/13/2017

---
# <a name="xml-intellisense-in-visual-basic"></a>XML IntelliSense en Visual Basic
El Editor de código de Visual Basic incluye características de IntelliSense para XML que proporcionan la finalización de palabras para los elementos definidos en un esquema XML. Si incluye un archivo de definición de esquemas XML (XSD) en el proyecto e importar el espacio de nombres de destino del esquema mediante la `Imports` instrucción, el Editor de código incluirá elementos desde el esquema XSD en la lista de IntelliSense de variables miembro válidas para <xref:System.Xml.Linq.XElement>y <xref:System.Xml.Linq.XDocument>objetos.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> La ilustración siguiente muestra la lista de los miembros de IntelliSense para un <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement>  
  
 ![XML IntelliSense en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")  
IntelliSense XML  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a>Habilitar IntelliSense XML en Visual Basic  
 Para habilitar IntelliSense XML en Visual Basic, debe incluir un archivo de esquema XSD en el proyecto de Visual Basic. También debe importar el espacio de nombres de destino para el esquema XSD en el archivo de código mediante el uso de la `Imports` instrucción. Como alternativa, puede agregar el espacio de nombres de destino a la lista de nombres de nivel de proyecto mediante la **referencias** página del Diseñador de proyectos de Visual Basic. Para obtener ejemplos, vea [Cómo: habilitar IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md). Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) y [página referencias, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Tenga en cuenta que, de forma predeterminada, no puede ver los archivos de esquema XSD en proyectos de Visual Basic. Puede que tenga que haga clic en el **mostrar todos los archivos** el botón para seleccionar un archivo XSD para incluir en el proyecto.  
  
### <a name="generating-a-schema-file-schema-inference"></a>Generar un archivo de esquema (inferencia de esquemas)  
 Puede crear un esquema XSD para un archivo XML existente deduciendo el esquema XSD mediante las herramientas XML de Visual Studio.  
  
-   A partir de SP1, puede utilizar el Asistente de XML a esquema para crear un conjunto de esquemas XML que se infiere de uno o más documentos XML e incluirlo en el proyecto. Puede utilizar cualquier combinación de documentos XML en forma de archivos de texto, XML de direcciones de HTTP Internet o XML que esté escrito o pegado en el Asistente de XML a esquema. Para tener acceso el Asistente de XML a esquema, haga clic en **Agregar nuevo elemento** en el **proyecto** menú y agregue un **XML a esquema** plantilla desde el **datos** o **elementos comunes** grupo de plantillas. Una vez que ha incluido todos los orígenes de documentos XML para inferir el conjunto de esquemas XML desde, haga clic en **Aceptar** para crear el esquema deducido conjunto. Para obtener más información, consulte [Asistente XML a esquema](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).  
  
-   También puede utilizar el Editor XML de Visual Studio para deducir un esquema XSD que se establece desde un archivo XML. Para crear un esquema XML establecido mediante el Editor XML, abra un archivo XML en el Diseñador de XML de Visual Studio y, a continuación, haga clic en **Create Schema** en el **XML** menú. Después de crear el conjunto de esquemas XSD, puede guardar el conjunto de esquemas creados en uno o más archivos XSD y los incluye en el proyecto. Para obtener más información, consulte[Cómo: habilitar IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  
  
 Tenga en cuenta que los distintos conjuntos de esquemas XSD se podrían deducir de varios documentos XML que se piensa que tienen el mismo esquema. Esto puede ocurrir cuando se encuentran elementos y atributos concretos en un archivo XML y no en otro, o cuando se incluyen los elementos en un orden diferente, por ejemplo. Debe revisar los conjuntos de esquemas XSD deducidos son completos y precisos al utilizar la inferencia del esquema XSD.  
  
## <a name="member-list"></a>Lista de miembros  
 Después de escribir un punto (.) para delimitar una instancia de un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>objeto (o una instancia de `IEnumerable(Of XElement)` o `IEnumerable(Of XDocument)`), IntelliSense de Visual Basic muestra una lista de miembros de objeto posibles.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> La lista inicial incluye tres opciones que representan propiedades de eje XML, como se describe en la siguiente lista.  
  
|Opción|Descripción|  
|---|---|  
|**\< >**|Seleccione esta opción para mostrar una lista de posibles secundarios de elementos. Para obtener más información, consulte [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y <xref:System.Xml.Linq.XContainer.Elements%2A>método.</xref:System.Xml.Linq.XContainer.Elements%2A>|  
|**@**|Seleccione esta opción para mostrar una lista de los posibles atributos. Para obtener más información, consulte [propiedades de eje XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Esta opción sólo está disponible para objetos de tipo <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|**…\< >**|Seleccione esta opción para mostrar una lista de posibles elementos descendientes. Para obtener más información, consulte [Cómo: obtener acceso a XML descendiente elementos](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) y la <xref:System.Xml.Linq.XContainer.Elements%2A>(método).</xref:System.Xml.Linq.XContainer.Elements%2A>|  
  
 Seleccione o comience a escribir en cualquiera de las opciones de XML de la lista. La lista de miembros mostrará después los posibles miembros del esquema XML que son específicos de la opción seleccionada. Si tiene espacios de nombres XML importado que están asociados con un prefijo de espacio de nombres XML concreto, se incluye una lista de prefijos de espacio de nombres XML potenciales en la lista de miembros.  
  
 Por ejemplo, considere el siguiente esquema XSD.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified"   
           elementFormDefault="qualified"   
           targetNamespace="http://SamplePurchaseOrder"   
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="PurchaseOrders">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="PurchaseOrder">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Address" />  
              <xs:element name="Items" />  
              <xs:element name="Comment" />  
            </xs:sequence>  
            <xs:attribute name="PurchaseOrderNumber" type="xs:unsignedShort" use="required" />  
            <xs:attribute name="OrderDate" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 XML válido para el esquema XSD se parecería al siguiente.  
  
```  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 Si incluye este archivo de esquema XSD en un proyecto e importar el espacio de nombres de destino del esquema XSD en el archivo de código o proyecto, IntelliSense de Visual Basic muestra los miembros desde el esquema a medida que escribe el código de Visual Basic. Si el espacio de nombres de destino para el esquema XSD se importa como el espacio de nombres predeterminado y escriba lo siguiente, IntelliSense muestra una lista de posibles elementos secundarios para el `PurchaseOrder` elemento XML.  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 La lista está formada por los elementos dirección, comentario y elementos.  
  
### <a name="certainty-levels-for-intellisense-list-items"></a>Niveles de seguridad para elementos de lista de IntelliSense  
 Determinar el tipo XSD para IntelliSense no es exacto. Como resultado, IntelliSense XML mostrará a menudo una lista expandida de posibles miembros. Para ayudarle a seleccionar un elemento de la lista de miembros de IntelliSense, los elementos se muestran con indicación del nivel de certeza que IntelliSense XML tiene para un miembro determinado.  
  
 A veces IntelliSense XML puede identificar un tipo específico del esquema XSD. En estos casos, mostrará posibles elementos secundarios, atributos o elementos descendientes para ese tipo XSD con un alto grado de certeza. Estos elementos se identifican con una marca de verificación.  
  
 Sin embargo, a veces IntelliSense XML no es capaz de identificar un tipo específico del esquema XSD. En estos casos, mostrará una lista expandida de posibles elementos secundarios, atributos o elementos descendientes desde el esquema XSD para el proyecto con un escaso grado de certeza. Estos elementos se identifican con un signo de interrogación.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: habilitar IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)   
 [Asistente XML a esquema](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)   
 [Imports (instrucción) (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Propiedad Axis para atributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)   
 [Propiedad de eje descendiente XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [Página Referencias, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)
