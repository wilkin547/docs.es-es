---
title: Serialización XML con servicios Web XML
description: Aprenda sobre la serialización XML como mecanismo de transporte utilizado en la arquitectura de servicios Web XML. La serialización XML se realiza mediante la clase XmlSerializer.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML Web services, XML serialization
- XML serialization, XML Web services
- SOAP, XML serialization
- asmx files
- serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- .asmx files
- encoded XML serialization
- literal XML serialization
- serialization, attributes
ms.assetid: a416192f-8102-458e-bc0a-0b8f3f784da9
ms.openlocfilehash: 8464122d4849271ba76edd6b3400ed09d7429821
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542012"
---
# <a name="xml-serialization-with-xml-web-services"></a>Serialización XML con servicios Web XML
La serialización XML es el mecanismo de transporte subyacente utilizado en la arquitectura de los servicios Web XML, realizada por la clase <xref:System.Xml.Serialization.XmlSerializer>. Para controlar el XML generado por un servicio web XML, puede aplicar los atributos de [Atributos que controlan la serialización XML](attributes-that-control-xml-serialization.md) y [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md) a las clases, los valores devueltos, los parámetros y los campos de un archivo usados para crear un servicio web XML (.asmx). Para más información sobre cómo crear un servicio web XML, vea [Servicios web XML con ASP.NET](/previous-versions/dotnet/netframework-4.0/ba0z6a33(v=vs.100)).  
  
## <a name="literal-and-encoded-styles"></a>Estilos literales y codificados  
 Se puede aplicar formato al XML generado por un servicio web XML de dos maneras distintas, estilo literal o codificado, como se explica en [Personalizar el formato de mensajes SOAP](/previous-versions/dotnet/netframework-4.0/dkwy2d72(v=vs.100)). Hay, por consiguiente, dos conjuntos de atributos que controlan la serialización XML. Los atributos que se mencionan en [Atributos que controlan la serialización XML](attributes-that-control-xml-serialization.md) están diseñados para controlar el XML de estilo literal. Los atributos mencionados en [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md) controlan el estilo codificado. Aplicando selectivamente estos atributos, puede entallar una aplicación para devolver uno o ambos estilos. Además, estos atributos se pueden aplicar (según corresponda) a los valores devueltos y parámetros.  
  
### <a name="example-of-using-both-styles"></a>Ejemplo de utilizar ambos estilos  
 Al estar creando un servicio Web XML, puede utilizar ambos conjuntos de atributos en los métodos. En el ejemplo de código siguiente, la clase denominada `MyService` contiene dos métodos de servicios Web XML, `MyLiteralMethod` y `MyEncodedMethod`. Ambos métodos realizan la misma función: devolviendo una instancia de la clase `Order`. En la clase `Order`, los atributos <xref:System.Xml.Serialization.XmlTypeAttribute> y <xref:System.Xml.Serialization.SoapTypeAttribute> se aplican al campo `OrderID` y ambos tienen la propiedad `ElementName` establecida en valores diferentes.  
  
 Para ejecutar el ejemplo, pegue el código en un archivo con una extensión .asmx y coloque el archivo en un directorio virtual administrado por Internet Information Services (IIS). De un examinador de HTML, como Internet Explorer, escriba el nombre del equipo, directorio virtual y archivo.  
  
```vb  
<%@ WebService Language="VB" Class="MyService" %>  
Imports System  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports System.Xml.Serialization  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which type  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
  
Public Class MyService  
    <WebMethod, SoapDocumentMethod> _  
    public Function MyLiteralMethod() As Order
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
    <WebMethod, SoapRpcMethod> _  
    public Function MyEncodedMethod() As Order
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
End Class  
```  
  
```csharp  
<%@ WebService Language="C#" Class="MyService" %>  
using System;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Serialization;  
public class Order {  
    // Both types of attributes can be applied. Depending on which type  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
public class MyService {  
    [WebMethod][SoapDocumentMethod]  
    public Order MyLiteralMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
    [WebMethod][SoapRpcMethod]  
    public Order MyEncodedMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
}  
```  
  
 En el ejemplo de código siguiente se llama a `MyLiteralMethod`. El nombre de elemento se cambia a "LiteralOrderID."  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <MyLiteralMethodResult>  
                <LiteralOrderID>string</LiteralOrderID>  
            </MyLiteralMethodResult>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 En el ejemplo de código siguiente se llama a `MyEncodedMethod`. El nombre de elemento es "EncodedOrderID."  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tns="http://tempuri.org/" xmlns:types="http://tempuri.org/encodedTypes" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body soap:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
        <tns:MyEncodedMethodResponse>  
            <MyEncodedMethodResult href="#id1" />  
        </tns:MyEncodedMethodResponse>  
        <types:Order id="id1" xsi:type="types:Order">  
            <EncodedOrderID xsi:type="xsd:string">string</EncodedOrderID>  
        </types:Order>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="applying-attributes-to-return-values"></a>Aplicar los atributos a los valores de devolución  
 También puede aplicar los atributos a los valores devueltos para controlar el espacio de nombres, nombre de elemento, etc. En el ejemplo de código siguiente se aplica el atributo `XmlElementAttribute` para devolver valores del método `MyLiteralMethod`. Hacer esto le permite controlar el espacio de nombres y nombre de elemento.  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod() As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order
    Dim myOrder As Order = New Order()  
    return myOrder  
End Function  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod(){  
    Order myOrder = new Order();  
    return myOrder;  
}  
```  
  
 Cuando se invoca, el código devuelve XML que se parece a lo siguiente.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <BookOrder xmlns="http://www.cohowinery.com">  
                <LiteralOrderID>string</LiteralOrderID>  
            </BookOrder>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="attributes-applied-to-parameters"></a>Atributos aplicados a parámetros  
 También puede aplicar los atributos a los parámetros para especificar el espacio de nombres, nombre de elemento etc. El ejemplo de código siguiente agrega un parámetro al método `MyLiteralMethodResponse` y aplica el atributo `XmlAttributeAttribute` al parámetro. El nombre de elemento y espacio de nombres están establecidos para el parámetro.  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod(<XmlElement _  
("MyOrderID", Namespace:="http://www.microsoft.com")>ID As String) As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order
    Dim myOrder As Order = New Order()  
    myOrder.OrderID = ID  
    return myOrder  
End Function  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod([XmlElement("MyOrderID",
Namespace="http://www.microsoft.com")] string ID){  
    Order myOrder = new Order();  
    myOrder.OrderID = ID;  
    return myOrder;  
}
```  
  
 La solicitud SOAP debería tener un aspecto similar al siguiente.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethod xmlns="http://tempuri.org/">  
            <MyOrderID xmlns="http://www.microsoft.com">string</MyOrderID>  
        </MyLiteralMethod>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="applying-attributes-to-classes"></a>Aplicar los atributos a las clases  
 Si necesita controlar el espacio de nombres de elementos que ponen en correlación a las clases, puede aplicar `XmlTypeAttribute`, `XmlRootAttribute`y `SoapTypeAttribute`, según corresponda. En el siguiente ejemplo de código se aplican los tres a la clase `Order` .  
  
```vb  
<XmlType("BigBookService"), _  
SoapType("SoapBookService"), _  
XmlRoot("BookOrderForm")> _  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
```  
  
```csharp  
[XmlType("BigBooksService", Namespace = "http://www.cpandl.com")]  
[SoapType("SoapBookService")]  
[XmlRoot("BookOrderForm")]  
public class Order {  
    // Both types of attributes can be applied. Depending on which  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
```  
  
 Se pueden ver los resultados de aplicar `XmlTypeAttribute` y `SoapTypeAttribute` al examinar la descripción del servicio, como se muestra en el ejemplo de código siguiente.  
  
```xml
<s:element name="BookOrderForm" type="s0:BigBookService" />
<s:complexType name="BigBookService">
  <s:sequence>
    <s:element minOccurs="0" maxOccurs="1" name="LiteralOrderID" type="s:string" />
  </s:sequence>

  <s:schema targetNamespace="http://tempuri.org/encodedTypes">
    <s:complexType name="SoapBookService">
      <s:sequence>
        <s:element minOccurs="1" maxOccurs="1" name="EncodedOrderID" type="s:string" />
      </s:sequence>
    </s:complexType>
  </s:schema>
</s:complexType>
```
  
 El efecto de `XmlRootAttribute` también se puede ver en el Http GET y resultados de Http POST, como sigue.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<BookOrderForm xmlns="http://tempuri.org/">  
    <LiteralOrderID>string</LiteralOrderID>  
</BookOrderForm>  
```  
  
## <a name="see-also"></a>Vea también

- [Serialización SOAP y XML](xml-and-soap-serialization.md)
- [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md)
- [Cómo: Serializar un objeto como secuencia XML con codificación SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
- [Cómo: invalidar la serialización XML SOAP codificada](how-to-override-encoded-soap-xml-serialization.md)
- [Introducción a la serialización XML](introducing-xml-serialization.md)
- [Cómo: Serialización de un objeto](how-to-serialize-an-object.md)
- [Cómo: Deserialización de un objeto](how-to-deserialize-an-object.md)
