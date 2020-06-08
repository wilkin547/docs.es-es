---
title: Parámetros XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
ms.openlocfilehash: 7651360b375071c48ba0d23b64881ac794e51e86
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282537"
---
# <a name="xslt-parameters"></a>Parámetros XSLT
Los parámetros XSLT se agregan a <xref:System.Xml.Xsl.XsltArgumentList> mediante el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>. En ese momento se asocia al objeto de parámetro un nombre completo y un identificador URI de espacio de nombres.  
  
### <a name="to-use-an-xslt-parameter"></a>Para utilizar un parámetro XSLT  
  
1. Cree un objeto <xref:System.Xml.Xsl.XsltArgumentList> y agregue el parámetro utilizando el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.  
  
2. Llame al parámetro desde la hoja de estilos.  
  
3. Pase el objeto <xref:System.Xml.Xsl.XsltArgumentList> al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## <a name="parameter-types"></a>Tipos de parámetros  
 El objeto de parámetro se debería corresponder a un tipo del W3C. En la siguiente tabla se muestran los tipos correspondientes del W3C, las clases de Microsoft .NET Framework equivalentes (tipo) y si el tipo del W3C es un tipo XPath o un tipo XSLT.  
  
|Tipo del W3C|Clase equivalente de .NET (tipo)|Tipo XPath o XSLT|  
|--------------|------------------------------------|------------------------|  
|`String`|<xref:System.String?displayProperty=nameWithType>|XPath|  
|`Boolean`|<xref:System.Boolean?displayProperty=nameWithType>|XPath|  
|`Number`|<xref:System.Double?displayProperty=nameWithType>|XPath|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|XSLT|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|XPath|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> **XPathNavigator[]**|XPath|  
  
 *Es equivalente a un conjunto de nodos que contiene un solo nodo.  
  
 Si el objeto de parámetro no pertenece a una de las clases anteriores, se convierte de acuerdo con las siguientes reglas. Los tipos de Common Language Runtime (CLR) numéricos se convierten en <xref:System.Double>. El tipo <xref:System.DateTime> se convierte en <xref:System.String>. Los tipos <xref:System.Xml.XPath.IXPathNavigable> se convierten en <xref:System.Xml.XPath.XPathNavigator>. **XPathNavigator[]** se convierte en <xref:System.Xml.XPath.XPathNodeIterator>.  
  
 El resto de los tipos inician un error.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza el método <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> para crear un parámetro que almacena la fecha de descuento calculada. Para calcular la fecha de descuento se deben sumar 20 días a partir de la fecha del pedido.  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### <a name="input"></a>Entrada  
  
##### <a name="orderxml"></a>order.xml  
 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### <a name="discountxsl"></a>discount.xsl  
 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### <a name="output"></a>Salida  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## <a name="see-also"></a>Vea también

- [Transformaciones XSLT](xslt-transformations.md)
