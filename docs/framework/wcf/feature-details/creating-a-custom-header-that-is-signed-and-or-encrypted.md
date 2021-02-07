---
description: Más información acerca de cómo crear un encabezado personalizado firmado o cifrado
title: Creación de un encabezado personalizado firmado o cifrado
ms.date: 03/30/2017
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
ms.openlocfilehash: d3952eeb37cbe09f72e179fcaa50c650fe9aa90d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705179"
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a>Creación de un encabezado personalizado firmado o cifrado

Al llamar a un servicio no WCF utilizando un cliente WCF a veces es necesario utilizar encabezados SOAP personalizados. Hay un error de canonización en WCF que impide que los encabezados personalizados firmados y cifrados funcionen con un servicio no WCF. El problema se debe a la canonización incorrecta de los espacios de nombres XML predeterminados. Este hecho es problemático únicamente al llamar a servicios no WCF con encabezados personalizados firmados o cifrados.  Cuando el servicio recibe el mensaje que contiene el encabezado personalizado firmado o cifrado, no puede comprobar la firma. Esta solución evita el error de canonización, permite la interoperabilidad con servicios no WCF, pero no impide la interoperabilidad con servicios WCF.  
  
## <a name="defining-the-custom-header"></a>Definición del encabezado personalizado  

 Para definir los encabezados personalizados, se define un contrato de mensaje y se marcan los miembros que se desean enviar como encabezados con un atributo <xref:System.ServiceModel.MessageHeaderAttribute>. Para evitar el error de canonización, debe asegurarse de que el serializador XML declara el espacio de nombres para el encabezado personalizado con un prefijo en lugar de una declaración de espacio de nombres predeterminado. El siguiente código muestra cómo definir el tipo de datos que se utilizará como encabezado del mensaje con la declaración de espacio de nombres correcta.  
  
```csharp
[System.CodeDom.Compiler.GeneratedCodeAttribute("svcutil", "3.0.4506.648")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://www.example.org/getMessage/")]  
public partial class msgHeaderElement  
{  
   // Define the XML namespace and force it to use an ‘h’ prefix  
    [System.Xml.Serialization.XmlNamespaceDeclarations]  
    public System.Xml.Serialization.XmlSerializerNamespaces _xsns = new System.Xml.Serialization.XmlSerializerNamespaces(new System.Xml.XmlQualifiedName[] { new System.Xml.XmlQualifiedName("h", "http://www.example.org/getMessage/") });  
  
    private string msgHeaderInputField;  
  [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified, Order=0)]  
    public string msgHeaderInput  
    {  
        get  
        {  
            return this.msgHeaderInputField;  
        }  
        set  
        {  
            this.msgHeaderInputField = value;  
        }  
    }  
}  
```  
  
 Este código declara un nuevo tipo llamado `msgHeaderElement` que se serializará con el Serializador XML. Cuando se serializa una instancia de este tipo, definirá un espacio de nombres con un prefijo 'h', con lo que se soluciona el error de canonización.  El contrato del mensaje definiría a continuación una instancia de `msgHeaderElement` y la marcaría con el atributo <xref:System.ServiceModel.MessageHeaderAttribute>, como se muestra en el siguiente ejemplo.  
  
```csharp
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Contrato de mensaje predeterminado](../samples/default-message-contract.md)
- [Contratos de mensajes](../samples/message-contracts.md)
- [Usar contratos de mensaje](using-message-contracts.md)
