---
title: Resolver hojas de estilos XSLT y documentos externos
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
ms.openlocfilehash: 8e7f66d67f2520b47c30307a98ed2f3fb08455df
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291479"
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a>Resolver hojas de estilos XSLT y documentos externos
Hay varios momentos a lo largo de una transformación en los cuales puede que necesite resolver recursos externos:  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 Hay varios momentos a lo largo de una transformación en los cuales puede que necesite resolver recursos externos:  
  
- Durante la operación <xref:System.Xml.Xsl.XslTransform.Load%2A> para localizar una hoja de estilos externa.  
  
- Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para resolver cualquier elemento `<xsl:include>` o `<xsl:import>` que se encuentre en la hoja de estilos.  
  
- Durante la operación <xref:System.Xml.Xsl.XslTransform.Transform%2A> para resolver las funciones `document()`.  
  
## <a name="using-the-xmlresolver-class"></a>Utilizar la clase XmlResolver  
 Si se precisa autenticación para tener acceso a un recurso de red, utilice los métodos <xref:System.Xml.Xsl.XslTransform.Load%2A> que tengan un parámetro <xref:System.Xml.XmlResolver> para pasar el objeto <xref:System.Xml.XmlResolver> que tenga establecido el conjunto de propiedades de credenciales necesarias.  
  
 Si tiene un <xref:System.Xml.XmlResolver> personalizado que desea utilizar o si tiene que especificar unas credenciales distintas, en la tabla siguiente se enumeran las tareas requeridas en función de que sea o no necesario resolver el recurso externo.  
  
|Proceso que requiere resolución|Tareas necesarias|  
|--------------------------------------|-------------------|  
|Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para localizar la hoja de estilos.|Especificar el método <xref:System.Xml.Xsl.XslTransform.Load%2A> sobrecargado que toma como parámetro un <xref:System.Xml.XmlResolver> si la hoja de estilos se encuentra en un recurso que requiere credenciales.|  
|Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para resolver `<xsl:include>` o `<xsl:import>`.|Especificar el método <xref:System.Xml.Xsl.XslTransform.Load%2A> sobrecargado que admite, como parámetro, un <xref:System.Xml.XmlResolver>. <xref:System.Xml.XmlResolver> se utiliza para cargar las hojas de estilos a las que hacen referencia las instrucciones `import` o `include`. Si proporciona un valor `null`, los recursos externos no se resuelven.|  
|Durante una transformación para resolver las funciones `document()`.|Especifique <xref:System.Xml.XmlResolver> durante la transformación utilizando el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> que toma un argumento <xref:System.Xml.XmlResolver>.|  
  
 La función `document()` recupera otros recursos XML desde una hoja de estilos, además de los datos XML iniciales proporcionados por el flujo de entrada. Como esta función permite la inclusión de datos XML que pueden localizarse en cualquier otro lugar, <xref:System.Xml.XmlResolver> con un valor `null` suministrado al método <xref:System.Xml.Xsl.XslTransform.Transform%2A> evita que la función `document()` se ejecute. Si desea utilizar la función `document()`, utilice el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> que toma un <xref:System.Xml.XmlResolver> como parámetro.  
  
 Para más información sobre el método <xref:System.Xml.Xsl.XslTransform.Load%2A> y su uso de <xref:System.Xml.XmlResolver>, consulte <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.  
  
 Cuando se llama al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>, los permisos se calculan con la evidencia proporcionada durante el tiempo de carga y dicho conjunto de permisos se asigna a todo el proceso de transformación. Si la función `document()` intenta iniciar una acción que requiere permisos que no se han encontrado en el conjunto, se inicia una excepción.  
  
## <a name="see-also"></a>Vea también

- [Transformaciones XSLT con la clase XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
- [Salidas de XslTransform](outputs-from-an-xsltransform.md)
- [Transformaciones XSLT en distintos almacenes](xslt-transformations-over-different-stores.md)
- [XsltArgumentList para parámetros Stylesheet y objetos de extensión](xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)
- [Escritura de scripts de hojas de estilos XSLT mediante \<msxsl:script>](xslt-stylesheet-scripting-using-msxsl-script.md)
- [Compatibilidad con la función msxsl:node-set()](support-for-the-msxsl-node-set-function.md)
- [XPathNavigator en transformaciones](xpathnavigator-in-transformations.md)
- [XPathNodeIterator en transformaciones](xpathnodeiterator-in-transformations.md)
- [Entrada XPathDocument en XslTransform](xpathdocument-input-to-xsltransform.md)
- [Entrada de XmlDataDocument en XslTransform](xmldatadocument-input-to-xsltransform.md)
- [Entrada de XmlDocument en XslTransform](xmldocument-input-to-xsltransform.md)
