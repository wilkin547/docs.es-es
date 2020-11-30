---
title: Entradas en la clase XslCompiledTransform
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 834049f1-ab41-449e-9f10-4a1d0701bc48
ms.openlocfilehash: af529f1c6ccfe3abe761c7707772d6f9697c179d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733430"
---
# <a name="inputs-to-the-xslcompiledtransform-class"></a>Entradas en la clase XslCompiledTransform

El método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> acepta tres tipos de entradas para el documento de origen: un objeto que implementa la interfaz <xref:System.Xml.XPath.IXPathNavigable>, un objeto <xref:System.Xml.XmlReader> que lee el documento de origen o un identificador URI de cadena.  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslCompiledTransform> conserva el espacio en blanco de manera predeterminada. Esto es lo que se establece en la [sección 3.4 de la recomendación de XSLT 1.0 del W3C](https://www.w3.org/TR/xslt.html#strip).  
  
## <a name="ixpathnavigable-interface"></a>Interfaz IXPathNavigable  

 La interfaz <xref:System.Xml.XPath.IXPathNavigable> se implementa en la clase <xref:System.Xml.XmlNode> y <xref:System.Xml.XPath.XPathDocument>. Estas clases representan una caché en memoria de datos XML.  
  
- La clase <xref:System.Xml.XmlNode> se basa en el Modelo de objetos de documento (DOM) del W3C e incluye capacidades de edición.  
  
- La clase <xref:System.Xml.XPath.XPathDocument> es un almacén de datos de solo lectura basado en el modelo de datos XPath. <xref:System.Xml.XPath.XPathDocument> es la clase recomendada para el procesamiento XSLT. Proporciona un rendimiento mayor comparada con la clase <xref:System.Xml.XmlNode>.  
  
> [!NOTE]
> Las transformaciones se aplican al documento en su totalidad. En otras palabras, si se pasa un nodo distinto del nodo raíz del documento, esto no evita que el proceso de transformación pueda obtener acceso a todos los nodos del documento cargado. Para transformar un fragmento del nodo, debe crear un objeto que contenga solo el fragmento del nodo y pasar ese objeto al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>. Para obtener más información, vea [Cómo: Transformación de un fragmento de nodo](how-to-transform-a-node-fragment.md).  
  
 En el siguiente ejemplo se utiliza el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> para transformar el archivo books.xml en el archivo books.html mediante la hoja de estilos transform.xsl. Los archivos books.xml y transform.xsl pueden encontrarse en este tema: [Cómo: Ejecución de una transformación XSLT mediante un ensamblado](how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#1)]
 [!code-vb[XslCompiledTransform.Transform2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#1)]  
  
## <a name="xmlreader-object"></a>Objeto XmlReader  

 El método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> se carga desde el nodo actual del <xref:System.Xml.XmlReader> a través de todos sus nodos secundarios. Esto le permite utilizar una parte de un documento como documento de contexto. Una vez devuelto el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>, <xref:System.Xml.XmlReader> se sitúa en el siguiente nodo después del final del documento de contexto. Si se llega al final del documento, <xref:System.Xml.XmlReader> se sitúa al final del archivo.  
  
 En el siguiente ejemplo se utiliza el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> para transformar el archivo books.xml en el archivo books.html mediante la hoja de estilos transform.xsl. Los archivos books.xml y transform.xsl pueden encontrarse en este tema: [Cómo: Ejecución de una transformación XSLT mediante un ensamblado](how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#2)]
 [!code-vb[XslCompiledTransform.Transform2#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#2)]  
  
## <a name="string-uri"></a>Identificador URI de cadena  

 También puede especificar el identificador URI del documento de origen como entrada XSLT. Se utiliza un <xref:System.Xml.XmlResolver> para resolver el identificador URI. Puede especificar el <xref:System.Xml.XmlResolver> que se va a utilizar pasándolo al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>. Si no se especifica un <xref:System.Xml.XmlResolver>, el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> utiliza un <xref:System.Xml.XmlUrlResolver> predeterminado sin ninguna credencial.  
  
 En el siguiente ejemplo se utiliza el método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> para transformar el archivo books.xml en el archivo books.html mediante la hoja de estilos transform.xsl. Los archivos books.xml y transform.xsl pueden encontrarse en este tema: [Cómo: Ejecución de una transformación XSLT mediante un ensamblado](how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#3)]
 [!code-vb[XslCompiledTransform.Transform2#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#3)]  
  
 Para más información, vea [Resolución de recursos externos durante el procesamiento XSLT](resolving-external-resources-during-xslt-processing.md).  
  
## <a name="see-also"></a>Vea también

- [Transformaciones XSLT](xslt-transformations.md)
