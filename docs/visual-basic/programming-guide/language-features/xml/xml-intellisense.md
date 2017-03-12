---
title: "IntelliSense XML en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IntelliSense [Visual Basic], XML"
  - "código de Visual Basic, XML"
  - "XML [Visual Basic], IntelliSense"
  - "XML IntelliSense [Visual Basic]"
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# IntelliSense XML en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El editor de código de Visual Basic incluye las características de IntelliSense para XML que proporcionan la finalización de palabras de los elementos definidos en un esquema XML.  Si incluye un archivo de definición de esquema XML \(XSD\) en el proyecto e importa el espacio de nombres de destino del esquema mediante la instrucción `Imports`, el editor de código incluirá elementos desde el esquema XSD en la lista de IntelliSense de variables miembro válidas para los objetos <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XDocument>.  La ilustración siguiente muestra la lista de miembros de IntelliSense para un objeto <xref:System.Xml.Linq.XElement>.  
  
 ![XML IntelliSense en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml-intellisense.png "XML\_Intellisense")  
IntelliSense XML  
  
## Habilitar IntelliSense XML en Visual Basic  
 Para habilitar IntelliSense XML en Visual Basic, debe incluir un archivo de esquema XSD en el proyecto de Visual Basic.  También debe importar el espacio de nombres de destino para dicho esquema en el archivo de código mediante la instrucción `Imports`.  O bien, puede agregar el espacio de nombres de destino a la lista de espacios de nombres de nivel de proyecto mediante la página **Referencias** del Diseñador de proyectos de Visual Basic.  Para obtener ejemplos, vea [Cómo: Habilitar IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  Para obtener más información, vea [Imports \(Instrucción, Espacio de nombres XML\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) y [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  
  
 Observe que, de forma predeterminada, no puede ver los archivos de esquema XSD en proyectos de Visual Basic.  Quizá deba hacer clic en el botón **Mostrar todos los archivos** para seleccionar un archivo XSD que se vaya a incluir en el proyecto.  
  
### Generar un archivo de esquema \(inferencia de esquemas\)  
 Puede crear un esquema XSD para un archivo XML existente deduciendo el esquema XSD mediante las herramientas XML de Visual Studio.  
  
-   A partir de SP1, puede utilizar el Asistente de XML a esquema para crear un conjunto de esquemas XML que se infiere de uno o más documentos XML e incluirlo en el proyecto.  Puede utilizar cualquier combinación de documentos XML en forma de archivos de texto, XML de direcciones de Internet HTTP o XML que esté escrito o pegado en el Asistente de XML a esquema.  Para tener acceso al Asistente de XML a esquema, haga clic en **Agregar nuevo elemento** en el menú **Proyecto** y agregue una plantilla **XML a esquema** del grupo de plantillas **Datos** o **Elementos comunes**.  Después de haber incluido todos los orígenes de documentos XML desde los que inferir el conjunto de esquemas XML, haga clic en **Aceptar** para crear el conjunto de esquemas inferido.  Para obtener más información, vea [Asistente XML a esquema](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).  
  
-   También puede utilizar el Editor XML de Visual Studio para inferir un conjunto de esquemas XSD de un archivo XML.  Para crear un conjunto de esquemas XML mediante el Editor XML, abra un archivo XML en el Diseñador XML de Visual Studio y, a continuación, haga clic en **Crear esquema** en el menú **XML**.  Después de crear el conjunto de esquemas XSD, puede guardarlo en uno o más archivos XSD e incluirlos en su proyecto.  Para obtener más información, vea [Cómo: Habilitar IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  
  
 Observe que los distintos conjuntos de esquemas XSD se podrían inferir de varios documentos XML que se piensa que tienen el mismo esquema.  Esto se puede producir cuando elementos y atributos concretos se encuentran en un archivo XML y no en otro, o cuando los elementos están incluidos en orden diferente, por ejemplo.  Debe revisar los conjuntos de esquemas XSD inferidos respecto a su integridad y exactitud al utilizar la inferencia del esquema XSD.  
  
## Lista de miembros  
 Después de escribir un punto \(.\) para delimitar una instancia de un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> \(o una instancia de `IEnumerable(Of XElement)` o `IEnumerable(Of XDocument)`\), IntelliSense de Visual Basic muestra una lista de los posibles miembros del objeto.  La lista inicial incluye tres opciones que representan propiedades de eje XML, como se describe en la siguiente lista.  
  
|||  
|-|-|  
|Opción|Descripción|  
|**\< \>**|Seleccione esta opción para mostrar una lista de los posibles elementos secundarios.  Para obtener más información, vea [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y el método <xref:System.Xml.Linq.XContainer.Elements%2A>.|  
|**@**|Seleccione esta opción para mostrar una lista de los posibles atributos.  Para obtener más información, vea [Propiedades de eje XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Esta opción sólo está disponible para los objetos de tipo <xref:System.Xml.Linq.XElement>.|  
|**…\< \>**|Seleccione esta opción para mostrar una lista de los posibles elementos descendientes.  Para obtener más información, vea [Cómo: Obtener acceso a elementos descendientes XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) y el método <xref:System.Xml.Linq.XContainer.Elements%2A>.|  
  
 Seleccione o empiece a escribir cualquiera de las opciones XML de la lista.  La lista de miembros mostrará después los posibles miembros del esquema XML que son específicos de la opción seleccionada.  Si tiene espacios de nombres XML importados y asociados a un prefijo del espacio de nombres XML concreto, se incluye una posible lista de prefijos de espacio de nombres XML en la lista de miembros.  
  
 Por ejemplo, considere el siguiente esquema XSD:  
  
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
  
 El XML válido para el esquema XSD se parecería a lo siguiente.  
  
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
  
 Si incluye este archivo de esquema XSD en un proyecto e importa el espacio de nombres de destino desde el esquema XSD al proyecto o archivo de código, IntelliSense de Visual Basic muestra los miembros a partir del esquema a medida que escribe el código de Visual Basic.  Si el espacio de nombres de destino para el esquema XSD se importa como el espacio de nombres predeterminado y escribe lo siguiente, IntelliSense muestra una lista de posibles elementos secundarios del elemento XML `PurchaseOrder`.  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 La lista está formada por los elementos Dirección, Comentario y Elementos.  
  
### Niveles de certeza de los elementos de la lista de IntelliSense  
 El procedimiento con el fin de determinar el tipo XSD que se va a utilizar para IntelliSense no es exacto.  Como resultado, IntelliSense XML mostrará a menudo una lista expandida de posibles miembros.  Para ayudar a seleccionar un elemento en la lista de miembros de IntelliSense, los elementos se muestran con indicación del nivel de certeza que IntelliSense XML tiene para un miembro determinado.  
  
 A veces IntelliSense XML puede identificar un tipo específico a partir del esquema XSD.  En estos casos, mostrará posibles elementos secundarios, atributos o elementos descendientes para ese tipo XSD con un grado alto de certeza.  Estos elementos se identifican con una marca de verificación.  
  
 Sin embargo, a veces IntelliSense XML no puede identificar un tipo específico a partir del esquema XSD.  En estos casos, mostrará una lista expandida de posibles elementos secundarios, atributos o elementos descendientes a partir del esquema XSD para el proyecto con un grado bajo de certeza.  Estos elementos se identifican con un signo de interrogación.  
  
## Vea también  
 [Cómo: Habilitar IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)   
 [Asistente XML a esquema](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)   
 [Imports \(Instrucción, Espacio de nombres XML\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Propiedad Axis para atributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)   
 [Propiedad de eje descendiente XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)