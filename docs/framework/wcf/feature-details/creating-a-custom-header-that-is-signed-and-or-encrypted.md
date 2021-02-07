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
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a><span data-ttu-id="5bc9b-103">Creación de un encabezado personalizado firmado o cifrado</span><span class="sxs-lookup"><span data-stu-id="5bc9b-103">Creating a custom header that is signed and-or encrypted</span></span>

<span data-ttu-id="5bc9b-104">Al llamar a un servicio no WCF utilizando un cliente WCF a veces es necesario utilizar encabezados SOAP personalizados.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-104">When calling a non-WCF service using a WCF client it is sometimes necessary to use custom SOAP headers.</span></span> <span data-ttu-id="5bc9b-105">Hay un error de canonización en WCF que impide que los encabezados personalizados firmados y cifrados funcionen con un servicio no WCF.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-105">There is a canonicalization bug in WCF that prevents custom headers that are signed and encrypted from working with a non-WCF service.</span></span> <span data-ttu-id="5bc9b-106">El problema se debe a la canonización incorrecta de los espacios de nombres XML predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-106">The problem is caused by the incorrect canonicalization of default XML namespaces.</span></span> <span data-ttu-id="5bc9b-107">Este hecho es problemático únicamente al llamar a servicios no WCF con encabezados personalizados firmados o cifrados.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-107">This is only problematic when calling non-WCF services with custom headers that are signed and/or encrypted.</span></span>  <span data-ttu-id="5bc9b-108">Cuando el servicio recibe el mensaje que contiene el encabezado personalizado firmado o cifrado, no puede comprobar la firma.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-108">When the service receives the message containing the signed and/or encrypted custom header it is unable to verify the signature.</span></span> <span data-ttu-id="5bc9b-109">Esta solución evita el error de canonización, permite la interoperabilidad con servicios no WCF, pero no impide la interoperabilidad con servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-109">This workaround avoids the canonicalization bug, allows interoperability with non-WCF services, but does not prevent interoperability with WCF services.</span></span>  
  
## <a name="defining-the-custom-header"></a><span data-ttu-id="5bc9b-110">Definición del encabezado personalizado</span><span class="sxs-lookup"><span data-stu-id="5bc9b-110">Defining the custom header</span></span>  

 <span data-ttu-id="5bc9b-111">Para definir los encabezados personalizados, se define un contrato de mensaje y se marcan los miembros que se desean enviar como encabezados con un atributo <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-111">Custom headers are defined by defining a message contract and marking the members you want to be sent as headers with a <xref:System.ServiceModel.MessageHeaderAttribute> attribute.</span></span> <span data-ttu-id="5bc9b-112">Para evitar el error de canonización, debe asegurarse de que el serializador XML declara el espacio de nombres para el encabezado personalizado con un prefijo en lugar de una declaración de espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-112">To work around the canonicalization bug you must ensure that the XML serializer declares the namespace for the custom header with a prefix instead of a default namespace declaration.</span></span> <span data-ttu-id="5bc9b-113">El siguiente código muestra cómo definir el tipo de datos que se utilizará como encabezado del mensaje con la declaración de espacio de nombres correcta.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-113">The following code shows how to define the data type that will be used as a message header with the correct namespace declaration.</span></span>  
  
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
  
 <span data-ttu-id="5bc9b-114">Este código declara un nuevo tipo llamado `msgHeaderElement` que se serializará con el Serializador XML.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-114">This code declares a new type called `msgHeaderElement` that will be serialized with the XML Serializer.</span></span> <span data-ttu-id="5bc9b-115">Cuando se serializa una instancia de este tipo, definirá un espacio de nombres con un prefijo 'h', con lo que se soluciona el error de canonización.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-115">When an instance of this type is serialized, it will define a namespace with an ‘h’ prefix, thus working around the canonicalization bug.</span></span>  <span data-ttu-id="5bc9b-116">El contrato del mensaje definiría a continuación una instancia de `msgHeaderElement` y la marcaría con el atributo <xref:System.ServiceModel.MessageHeaderAttribute>, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5bc9b-116">The message contract would then define an instance of `msgHeaderElement` and mark it with the <xref:System.ServiceModel.MessageHeaderAttribute> attribute as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5bc9b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bc9b-117">See also</span></span>

- [<span data-ttu-id="5bc9b-118">Contrato de mensaje predeterminado</span><span class="sxs-lookup"><span data-stu-id="5bc9b-118">Default Message Contract</span></span>](../samples/default-message-contract.md)
- [<span data-ttu-id="5bc9b-119">Contratos de mensajes</span><span class="sxs-lookup"><span data-stu-id="5bc9b-119">Message Contracts</span></span>](../samples/message-contracts.md)
- [<span data-ttu-id="5bc9b-120">Usar contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="5bc9b-120">Using Message Contracts</span></span>](using-message-contracts.md)
