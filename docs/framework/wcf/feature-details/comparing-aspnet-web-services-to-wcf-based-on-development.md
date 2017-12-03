---
title: "Comparación de los servicios web ASP.NET con el WCF basado en desarrollo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6aa79e76bd81c0d56b30d4bac2edd4b9cbef6b33
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a><span data-ttu-id="520cb-102">Comparación de los servicios web ASP.NET con el WCF basado en desarrollo</span><span class="sxs-lookup"><span data-stu-id="520cb-102">Comparing ASP.NET Web Services to WCF Based on Development</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="520cb-103"> ofrece una opción de modo de compatibilidad de ASP.NET que permite programar y configurar aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] como servicios web ASP.NET, e imitar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="520cb-103"> has an ASP.NET compatibility mode option to enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications to be programmed and configured like ASP.NET Web services, and mimic their behavior.</span></span> <span data-ttu-id="520cb-104">Las secciones siguientes comparan los servicios web ASP.NET y [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] basado en los requisitos para desarrollar aplicaciones mediante ambas tecnologías.</span><span class="sxs-lookup"><span data-stu-id="520cb-104">The following sections compare ASP.NET Web services and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] based on what is required to develop applications using both technologies.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="520cb-105">Representación de datos</span><span class="sxs-lookup"><span data-stu-id="520cb-105">Data Representation</span></span>  
 <span data-ttu-id="520cb-106">Normalmente, el desarrollo de un servicio web con ASP.NET comienza con la definición de todos los tipos de datos complejos que utilizará el servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-106">The development of a Web service with ASP.NET typically begins with defining any complex data types the service is to use.</span></span> <span data-ttu-id="520cb-107">ASP.NET se basa en <xref:System.Xml.Serialization.XmlSerializer> para traducir los datos representados por los tipos de .NET Framework a XML para la transmisión hacia o desde un servicio, y para traducir los datos recibidos como XML en los objetos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="520cb-107">ASP.NET relies on the <xref:System.Xml.Serialization.XmlSerializer> to translate data represented by .NET Framework types to XML for transmission to or from a service and to translate data received as XML into .NET Framework objects.</span></span> <span data-ttu-id="520cb-108">La definición de los tipos de datos complejos que utilizará un servicio de ASP.NET requiere la definición de las clases de .NET Framework que <xref:System.Xml.Serialization.XmlSerializer> puede serializar a y desde XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-108">Defining the complex data types that an ASP.NET service is to use requires the definition of .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML.</span></span> <span data-ttu-id="520cb-109">Estas clases pueden escribirse manualmente o generarse a partir de las definiciones de los tipos de Esquema XML, mediante la línea de comandos de la utilidad de compatibilidad de tipos de datos de XML, xsd.exe.</span><span class="sxs-lookup"><span data-stu-id="520cb-109">Such classes can be written manually, or generated from definitions of the types in XML Schema using the command-line XML Schemas/Data Types Support Utility, xsd.exe.</span></span>  
  
 <span data-ttu-id="520cb-110">La siguiente lista muestra problemas clave que deben tenerse en cuenta al definir las clases de .NET Framework que <xref:System.Xml.Serialization.XmlSerializer> puede serializar a y desde XML:</span><span class="sxs-lookup"><span data-stu-id="520cb-110">The following is a list of key issues to know when defining .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML:</span></span>  
  
-   <span data-ttu-id="520cb-111">Solo los campos y propiedades públicas de los objetos de .NET Framework se traducen a XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-111">Only the public fields and properties of .NET Framework objects are translated into XML.</span></span>  
  
-   <span data-ttu-id="520cb-112">Las instancias de las clases de colección solo pueden serializarse a XML si las clases implementan <xref:System.Collections.IEnumerable>, o la interfaz <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="520cb-112">Instances of collection classes can be serialized into XML only if the classes implement either the <xref:System.Collections.IEnumerable> or <xref:System.Collections.ICollection> interface.</span></span>  
  
-   <span data-ttu-id="520cb-113">Las clases que implementan la interfaz <xref:System.Collections.IDictionary>, como <xref:System.Collections.Hashtable>, no pueden serializarse en XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-113">Classes that implement the <xref:System.Collections.IDictionary> interface, such as <xref:System.Collections.Hashtable>, cannot be serialized into XML.</span></span>  
  
-   <span data-ttu-id="520cb-114">La gran cantidad de tipos de atributo existente en el espacio de nombres <xref:System.Xml.Serialization>, puede agregarse a una clase de .NET Framework y sus miembros para controlar la representación de las instancias de la clase en XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-114">The great many attribute types in the <xref:System.Xml.Serialization> namespace can be added to a .NET Framework class and its members to control how instances of the class are represented in XML.</span></span>  
  
 <span data-ttu-id="520cb-115">El desarrollo de aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] normalmente también comienza con la definición de tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="520cb-115">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application development usually also begins with the definition of complex types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="520cb-116"> puede configurarse para usar los mismos tipos de .NET Framework que los servicios web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-116"> can be made to use the same .NET Framework types as ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="520cb-117">Puede agregarse [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a los tipos de .NET Framework para indicar que las instancias del tipo deben serializarse en XML, y qué campos o propiedades concretas del tipo deben serializarse, como muestra el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="520cb-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> can be added to .NET Framework types to indicate that instances of the type are to be serialized into XML, and which particular fields or properties of the type are to be serialized, as shown in the following sample code.</span></span>  
  
```  
//Example One:   
[DataContract]  
public class LineItem  
{  
    [DataMember]  
    public string ItemNumber;  
    [DataMember]  
    public decimal Quantity;  
    [DataMember]  
    public decimal UnitPrice;  
}  
  
//Example Two:   
public class LineItem  
{  
    [DataMember]  
    private string itemNumber;  
    [DataMember]  
    private decimal quantity;  
    [DataMember]  
    private decimal unitPrice;  
  
    public string ItemNumber  
    {  
      get  
      {  
          return this.itemNumber;  
      }  
  
      set  
      {  
          this.itemNumber = value;  
      }  
    }  
  
    public decimal Quantity  
    {  
        get  
        {  
            return this.quantity;  
        }  
  
        set  
        {  
            this.quantity = value;  
        }  
    }  
  
    public decimal UnitPrice  
    {  
      get  
      {  
          return this.unitPrice;  
      }  
  
      set  
      {  
          this.unitPrice = value;  
      }  
    }  
}  
  
//Example Three:   
public class LineItem  
{  
     private string itemNumber;  
     private decimal quantity;  
     private decimal unitPrice;  
  
     [DataMember]  
     public string ItemNumber  
     {  
       get  
       {  
          return this.itemNumber;  
       }  
  
       set  
       {  
           this.itemNumber = value;  
       }  
     }  
  
     [DataMember]  
     public decimal Quantity  
     {  
          get  
          {  
              return this.quantity;  
          }  
  
          set  
          {  
             this.quantity = value;  
          }  
     }  
  
     [DataMember]  
     public decimal UnitPrice  
     {  
          get  
          {  
              return this.unitPrice;  
          }  
  
          set  
          {  
              this.unitPrice = value;  
          }  
     }  
}  
```  
  
 <span data-ttu-id="520cb-118"><xref:System.Runtime.Serialization.DataContractAttribute> significa que cero o más campos o propiedades de un tipo deberán serializarse, mientras que <xref:System.Runtime.Serialization.DataMemberAttribute> indica que se serializará un campo o propiedad concreta.</span><span class="sxs-lookup"><span data-stu-id="520cb-118">The <xref:System.Runtime.Serialization.DataContractAttribute> signifies that zero or more of a type’s fields or properties are to be serialized, while the <xref:System.Runtime.Serialization.DataMemberAttribute> indicates that a particular field or property is to be serialized.</span></span> <span data-ttu-id="520cb-119">El atributo <xref:System.Runtime.Serialization.DataContractAttribute> se puede aplicar a una clase o a una estructura.</span><span class="sxs-lookup"><span data-stu-id="520cb-119">The <xref:System.Runtime.Serialization.DataContractAttribute> can be applied to a class or structure.</span></span> <span data-ttu-id="520cb-120"><xref:System.Runtime.Serialization.DataMemberAttribute> se puede aplicar a un campo o una propiedad, y los campos y propiedades a las que se aplica el atributo pueden ser públicos o privados.</span><span class="sxs-lookup"><span data-stu-id="520cb-120">The <xref:System.Runtime.Serialization.DataMemberAttribute> can be applied to a field or a property, and the fields and properties to which the attribute is applied can be either public or private.</span></span> <span data-ttu-id="520cb-121">Las instancias de tipos a los que se aplica <xref:System.Runtime.Serialization.DataContractAttribute> se conocen como contratos de datos en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-121">Instances of types that have the <xref:System.Runtime.Serialization.DataContractAttribute> applied to them are referred to as data contracts in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="520cb-122">Se serializan en XML mediante <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="520cb-122">They are serialized into XML using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="520cb-123">La siguiente lista enumera las principales diferencias entre la utilización de <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>, así como los distintos atributos del espacio de nombres <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="520cb-123">The following is a list of the important differences between using the <xref:System.Runtime.Serialization.DataContractSerializer> and using the <xref:System.Xml.Serialization.XmlSerializer> and the various attributes of the <xref:System.Xml.Serialization> namespace.</span></span>  
  
-   <span data-ttu-id="520cb-124"><xref:System.Xml.Serialization.XmlSerializer> y los atributos del espacio de nombres <xref:System.Xml.Serialization> están diseñados para permitir asignar los tipos de .NET Framework a cualquier tipo válido definido en Esquema XML, de modo que ofrecen un control muy preciso de la representación de un tipo en XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-124">The <xref:System.Xml.Serialization.XmlSerializer> and the attributes of the <xref:System.Xml.Serialization> namespace are designed to allow you to map .NET Framework types to any valid type defined in XML Schema, and so they provide for very precise control over how a type is represented in XML.</span></span> <span data-ttu-id="520cb-125"><xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> proporcionan un control muy preciso sobre la representación de un tipo en XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-125">The <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> provide very little control over how a type is represented in XML.</span></span> <span data-ttu-id="520cb-126">Solo pueden especificarse los espacios de nombres y los nombres utilizados para representar el tipo y sus campos, o propiedades en XML, así como la secuencia de aparición en XML de los campos y propiedades:</span><span class="sxs-lookup"><span data-stu-id="520cb-126">You can only specify the namespaces and names used to represent the type and its fields or properties in the XML, and the sequence in which the fields and properties appear in the XML:</span></span>  
  
    ```  
    [DataContract(  
    Namespace="urn:Contoso:2006:January:29",  
    Name="LineItem")]  
    public class LineItem  
    {  
         [DataMember(Name="ItemNumber",IsRequired=true,Order=0)]  
         public string itemNumber;  
         [DataMember(Name="Quantity",IsRequired=false,Order = 1)]  
         public decimal quantity;  
         [DataMember(Name="Price",IsRequired=false,Order = 2)]  
         public decimal unitPrice;  
    }  
    ```  
  
     <span data-ttu-id="520cb-127">El resto de información sobre la estructura de XML utilizada para representar el tipo .NET está determinada por <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="520cb-127">Everything else about the structure of the XML used to represent the .NET type is determined by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
-   <span data-ttu-id="520cb-128">Al no permitir un mayor control sobre la representación de un tipo en XML, el proceso de serialización se vuelve extremadamente predecible para <xref:System.Runtime.Serialization.DataContractSerializer>y, por lo tanto, más fácil de optimizar.</span><span class="sxs-lookup"><span data-stu-id="520cb-128">By not permitting much control over how a type is to be represented in XML, the serialization process becomes highly predictable for the <xref:System.Runtime.Serialization.DataContractSerializer>, and, thereby, easier to optimize.</span></span> <span data-ttu-id="520cb-129">Una ventaja práctica del diseño de <xref:System.Runtime.Serialization.DataContractSerializer> es un mejor rendimiento, aproximadamente un diez por ciento mejor.</span><span class="sxs-lookup"><span data-stu-id="520cb-129">A practical benefit of the design of the <xref:System.Runtime.Serialization.DataContractSerializer> is better performance, approximately ten percent better performance.</span></span>  
  
-   <span data-ttu-id="520cb-130">Los atributos utilizados con <xref:System.Xml.Serialization.XmlSerializer> no indican qué campos o propiedades del tipo se serializan en XML, mientras que <xref:System.Runtime.Serialization.DataMemberAttribute> utilizado con <xref:System.Runtime.Serialization.DataContractSerializer> muestra explícitamente qué campos o propiedades se serializan.</span><span class="sxs-lookup"><span data-stu-id="520cb-130">The attributes for use with the <xref:System.Xml.Serialization.XmlSerializer> do not indicate which fields or properties of the type are serialized into XML, whereas the <xref:System.Runtime.Serialization.DataMemberAttribute> for use with the <xref:System.Runtime.Serialization.DataContractSerializer> shows explicitly which fields or properties are serialized.</span></span> <span data-ttu-id="520cb-131">Por consiguiente, los contratos de datos son contratos explícitos de la estructura de datos que una aplicación enviará y recibirá.</span><span class="sxs-lookup"><span data-stu-id="520cb-131">Therefore, data contracts are explicit contracts about the structure of the data that an application is to send and receive.</span></span>  
  
-   <span data-ttu-id="520cb-132"><xref:System.Xml.Serialization.XmlSerializer> solo puede traducir a XML los miembros públicos de un objeto .NET, <xref:System.Runtime.Serialization.DataContractSerializer> puede traducir a XML los miembros de objetos independientemente de los modificadores de acceso de esos miembros.</span><span class="sxs-lookup"><span data-stu-id="520cb-132">The <xref:System.Xml.Serialization.XmlSerializer> can only translate the public members of a .NET object into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> can translate the members of objects into XML regardless of the access modifiers of those members.</span></span>  
  
-   <span data-ttu-id="520cb-133">Como consecuencia de poder serializar en XML los miembros no públicos de tipos, <xref:System.Runtime.Serialization.DataContractSerializer> posee menos restricciones en la variedad de tipos .NET que puede serializar en XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-133">As a consequence of being able to serialize the non-public members of types into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> has fewer restrictions on the variety of .NET types that it can serialize into XML.</span></span> <span data-ttu-id="520cb-134">En concreto, puede traducir a XML tipos como <xref:System.Collections.Hashtable> que implementa la interfaz <xref:System.Collections.IDictionary>.</span><span class="sxs-lookup"><span data-stu-id="520cb-134">In particular, it can translate into XML types like <xref:System.Collections.Hashtable> that implement the <xref:System.Collections.IDictionary> interface.</span></span> <span data-ttu-id="520cb-135">Es mucho más probable que <xref:System.Runtime.Serialization.DataContractSerializer> pueda serializar en XML las instancias de cualquiera tipo .NET existentes previamente, sin tener que modificar la definición del tipo o desarrollar un contenedor para él.</span><span class="sxs-lookup"><span data-stu-id="520cb-135">The <xref:System.Runtime.Serialization.DataContractSerializer> is much more likely to be able to serialize the instances of any pre-existing .NET type into XML without having to either modify the definition of the type or develop a wrapper for it.</span></span>  
  
-   <span data-ttu-id="520cb-136">Otra consecuencia de que <xref:System.Runtime.Serialization.DataContractSerializer> pueda tener acceso a los miembros no públicos de un tipo es que requiere plena confianza, al contrario que <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="520cb-136">Another consequence of the <xref:System.Runtime.Serialization.DataContractSerializer> being able to access the non-public members of a type is that it requires full trust, whereas the <xref:System.Xml.Serialization.XmlSerializer> does not.</span></span> <span data-ttu-id="520cb-137">El permiso de acceso al código de plena confianza otorga acceso total a todos los recursos de un equipo al que puede accederse mediante las credenciales con las que se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="520cb-137">The Full Trust code access permission give complete access to all resources on a machine that can be access using the credentials under which the code is executing.</span></span> <span data-ttu-id="520cb-138">Esta opción debería utilizarse con cuidado ya que el código de plena confianza puede acceder a todos los recursos del equipo.</span><span class="sxs-lookup"><span data-stu-id="520cb-138">This options should be used with care as fully trusted code accesses all resources on your machine.</span></span>  
  
-   <span data-ttu-id="520cb-139"><xref:System.Runtime.Serialization.DataContractSerializer> incorpora cierta compatibilidad para el control de versiones:</span><span class="sxs-lookup"><span data-stu-id="520cb-139">The <xref:System.Runtime.Serialization.DataContractSerializer> incorporates some support for versioning:</span></span>  
  
    -   <span data-ttu-id="520cb-140"><xref:System.Runtime.Serialization.DataMemberAttribute> posee una propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> a la puede asignarse un valor de falso para los miembros que se agregan a las nuevas versiones de un contrato de datos que no se encontraban en versiones anteriores, con lo que las aplicaciones con la versión más reciente del contrato pueden procesar las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="520cb-140">The <xref:System.Runtime.Serialization.DataMemberAttribute> has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property that can be assigned a value of false for members that are added to new versions of a data contract that were not present in earlier versions, thereby allowing applications with the newer version of the contract to be able to process earlier versions.</span></span>  
  
    -   <span data-ttu-id="520cb-141">Cuando un contrato de datos implementa la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>, es posible permitir a <xref:System.Runtime.Serialization.DataContractSerializer> pasar miembros definidos en versiones más recientes de un contrato de datos a través de aplicaciones con versiones anteriores del contrato.</span><span class="sxs-lookup"><span data-stu-id="520cb-141">By having a data contract implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface, one can allow the <xref:System.Runtime.Serialization.DataContractSerializer> to pass members defined in newer versions of a data contract through applications with earlier versions of the contract.</span></span>  
  
 <span data-ttu-id="520cb-142">A pesar de todas las diferencias, el XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, siempre y cuando defina explícitamente el espacio de nombres de XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-142">Despite all of the differences, the XML into which the <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="520cb-143">La siguiente clase, que posee atributos que pueden utilizarse con ambos serializadores, se traduce a un XML semánticamente idéntico utilizando <xref:System.Xml.Serialization.XmlSerializer> y <xref:System.Runtime.Serialization.DataContractAttribute>:</span><span class="sxs-lookup"><span data-stu-id="520cb-143">The following class, which has attributes for use with both of the serializers, are translated into semantically identical XML by the <xref:System.Xml.Serialization.XmlSerializer> and by the <xref:System.Runtime.Serialization.DataContractAttribute>:</span></span>  
  
```  
[Serializable]  
[XmlRoot(Namespace="urn:Contoso:2006:January:29")]  
[DataContract(Namespace="urn:Contoso:2006:January:29")]  
public class LineItem  
{  
     [DataMember]  
     public string ItemNumber;  
     [DataMember]  
     public decimal Quantity;  
     [DataMember]  
     public decimal UnitPrice;  
}  
```  
  
 <span data-ttu-id="520cb-144">El kit de desarrollo de software (SDK) de Windows incluye una herramienta de línea de comandos denominada el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Al igual que la herramienta xsd.exe utilizada con los servicios Web de ASP.NET, Svcutil.exe puede generar definiciones de tipos de datos de .NET de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="520cb-144">The Windows software development kit (SDK) includes a command-line tool called the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).Like the xsd.exe tool used with ASP.NET Web services, Svcutil.exe can generate definitions of .NET data types from XML Schema.</span></span> <span data-ttu-id="520cb-145">Los tipos son contratos de datos si <xref:System.Runtime.Serialization.DataContractSerializer> puede emitir XML con el formato definido por esquema XML; de lo contrario, están diseñados para serializarse mediante <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="520cb-145">The types are data contracts if the <xref:System.Runtime.Serialization.DataContractSerializer> can emit XML in the format defined by the XML Schema; otherwise, they are intended for serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="520cb-146">La herramienta, Svcutil.exe, también puede generar Esquema XML a partir de contratos de datos mediante su modificador `/dataContractOnly`.</span><span class="sxs-lookup"><span data-stu-id="520cb-146">The tool, Svcutil.exe, can also be made to generate XML Schema from data contracts using its `/dataContractOnly` switch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="520cb-147">Aunque los servicios web ASP.NET utilizan <xref:System.Xml.Serialization.XmlSerializer>, y el modo de compatibilidad de ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hace que los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] imiten el comportamiento de los servicios web ASP.NET, la opción de compatibilidad de ASP.NET no limita a la utilización del <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="520cb-147">Although ASP.NET Web services use the <xref:System.Xml.Serialization.XmlSerializer>, and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode makes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services mimic the behavior of ASP.NET Web services, the ASP.NET compatibility option does not restrict one to using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="520cb-148">Puede seguir utilizándose <xref:System.Runtime.Serialization.DataContractSerializer> con servicios que se ejecutan en el modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-148">One can still use the <xref:System.Runtime.Serialization.DataContractSerializer> with services running in the ASP.NET compatibility mode.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="520cb-149">Desarrollo del servicio</span><span class="sxs-lookup"><span data-stu-id="520cb-149">Service Development</span></span>  
 <span data-ttu-id="520cb-150">Para desarrollar un servicio mediante ASP.NET, lo habitual era agregar el atributo <xref:System.Web.Services.WebService> a una clase, y <xref:System.Web.Services.WebMethodAttribute> a cualquiera de los métodos de esa clase que serán operaciones del servicio:</span><span class="sxs-lookup"><span data-stu-id="520cb-150">To develop a service using ASP.NET, it has been customary to add the <xref:System.Web.Services.WebService> attribute to a class, and the <xref:System.Web.Services.WebMethodAttribute> to any of that class’ methods that are to be operations of the service:</span></span>  
  
```  
[WebService]  
public class Service : T:System.Web.Services.WebService  
{  
    [WebMethod]  
    public string Echo(string input)   
    {  
       return input;  
    }  
}  
```  
  
 <span data-ttu-id="520cb-151">ASP.NET 2.0 introdujo la opción de agregar el atributo <xref:System.Web.Services.WebService> y <xref:System.Web.Services.WebMethodAttribute> a una interfaz en lugar de a una clase, y de escribir una clase para implementar la interfaz:</span><span class="sxs-lookup"><span data-stu-id="520cb-151">ASP.NET 2.0 introduced the option of adding the attribute <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> to an interface rather than to a class, and writing a class to implement the interface:</span></span>  
  
```  
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 <span data-ttu-id="520cb-152">La utilización de esta opción es preferible porque la interfaz con el atributo <xref:System.Web.Services.WebService> constituye un contrato para las operaciones realizadas por el servicio, que puede reutilizarse con diferentes clases que podrían implementar ese mismo contrato de distintas maneras.</span><span class="sxs-lookup"><span data-stu-id="520cb-152">Using this option is to be preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="520cb-153">Se puede proporcionar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante la definición de uno o más extremos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-153">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is provided by defining one or more [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoints.</span></span> <span data-ttu-id="520cb-154">Un extremo se define mediante una dirección, un enlace y un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-154">An endpoint is defined by an address, a binding and a service contract.</span></span> <span data-ttu-id="520cb-155">La dirección define la ubicación del servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-155">The address defines where the service is located.</span></span> <span data-ttu-id="520cb-156">El enlace especifica cómo comunicar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-156">The binding specifies how to communicate with the service.</span></span> <span data-ttu-id="520cb-157">El contrato de servicio define las operaciones que puede realizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-157">The service contract defines the operations that the service can perform.</span></span>  
  
 <span data-ttu-id="520cb-158">Normalmente, primero se define el contrato de servicios agregando <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> a una interfaz:</span><span class="sxs-lookup"><span data-stu-id="520cb-158">The service contract is usually defined first, by adding <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> to an interface:</span></span>  
  
```  
[ServiceContract]  
public interface IEcho  
{  
     [OperationContract]  
     string Echo(string input);  
}  
```  
  
 <span data-ttu-id="520cb-159"><xref:System.ServiceModel.ServiceContractAttribute> especifica que la interfaz define un contrato del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], y <xref:System.ServiceModel.OperationContractAttribute> indica el método de la interfaz que define las operaciones del contrato de servicios, en caso de que alguno lo haga.</span><span class="sxs-lookup"><span data-stu-id="520cb-159">The <xref:System.ServiceModel.ServiceContractAttribute> specifies that the interface defines a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service contract, and the <xref:System.ServiceModel.OperationContractAttribute> indicates which, if any, of the methods of the interface define operations of the service contract.</span></span>  
  
 <span data-ttu-id="520cb-160">Una vez definido un contrato de servicios, se implementa en una clase, para ello la clase implementa la interfaz que define el contrato de servicios:</span><span class="sxs-lookup"><span data-stu-id="520cb-160">Once a service contract has been defined, it is implemented in a class, by having the class implement the interface by which the service contract is defined:</span></span>  
  
```  
public class Service : IEcho  
{  
    public string Echo(string input)  
    {  
       return input;  
    }  
}  
```  
  
 <span data-ttu-id="520cb-161">Una clase que implementa un contrato de servicios se conoce como un tipo de servicio en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-161">A class that implements a service contract is referred to as a service type in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="520cb-162">El paso siguiente es asociar una dirección y un enlace a un tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-162">The next step is to associate an address and a binding with a service type.</span></span> <span data-ttu-id="520cb-163">Generalmente, esto se hace en un archivo de configuración, bien editando directamente el archivo, o utilizando un editor de configuración proporcionado con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-163">That is typically done in a configuration file, either by editing the file directly, or by using a configuration editor provided with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="520cb-164">El siguiente es un ejemplo de archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="520cb-164">Here is an example of a configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
     <system.serviceModel>  
      <services>  
      <service name="Service ">  
       <endpoint   
        address="EchoService"  
        binding="basicHttpBinding"  
        contract="IEchoService "/>  
      </service>  
      </services>  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="520cb-165">El enlace especifica el conjunto de protocolos de comunicación con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="520cb-165">The binding specifies the set of protocols for communicating with the application.</span></span> <span data-ttu-id="520cb-166">La tabla siguiente enumera los enlaces proporcionados por el sistema que representan las opciones habituales.</span><span class="sxs-lookup"><span data-stu-id="520cb-166">The following table lists the system-provided bindings that represent common options.</span></span>  
  
|<span data-ttu-id="520cb-167">Name</span><span class="sxs-lookup"><span data-stu-id="520cb-167">Name</span></span>|<span data-ttu-id="520cb-168">Finalidad</span><span class="sxs-lookup"><span data-stu-id="520cb-168">Purpose</span></span>|  
|----------|-------------|  
|<span data-ttu-id="520cb-169">BasicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-169">BasicHttpBinding</span></span>|<span data-ttu-id="520cb-170">Interoperabilidad con los servicio y clientes web que admiten WS-BasicProfile 1.1 y Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="520cb-170">Interoperability with Web services and clients supporting the WS-BasicProfile 1.1 and Basic Security Profile 1.0.</span></span>|  
|<span data-ttu-id="520cb-171">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-171">WSHttpBinding</span></span>|<span data-ttu-id="520cb-172">Interoperabilidad con los servicio y clientes web que admiten los protocolos WS-* sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="520cb-172">Interoperability with Web services and clients that support the WS-* protocols over HTTP.</span></span>|  
|<span data-ttu-id="520cb-173">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-173">WSDualHttpBinding</span></span>|<span data-ttu-id="520cb-174">Comunicación HTTP dúplex, por la que el receptor de un mensaje inicial no responde directamente al remitente inicial, pero puede transmitir, durante un período de tiempo, cualquier número de respuestas utilizando HTTP de conformidad con los protocolos WS-*.</span><span class="sxs-lookup"><span data-stu-id="520cb-174">Duplex HTTP communication, by which the receiver of an initial message does not reply directly to the initial sender, but may transmit any number of responses over a period of time by using HTTP in conformity with WS-* protocols.</span></span>|  
|<span data-ttu-id="520cb-175">WSFederationBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-175">WSFederationBinding</span></span>|<span data-ttu-id="520cb-176">Comunicación HTTP, en la que el acceso a los recursos de un servicio puede controlarse en base a las credenciales emitidas por un proveedor de credenciales identificado explícitamente.</span><span class="sxs-lookup"><span data-stu-id="520cb-176">HTTP communication, in which access to the resources of a service can be controlled based on credentials issued by an explicitly-identified credential provider.</span></span>|  
|<span data-ttu-id="520cb-177">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-177">NetTcpBinding</span></span>|<span data-ttu-id="520cb-178">Comunicación segura, de confianza y de alto rendimiento entre las entidades de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de una red.</span><span class="sxs-lookup"><span data-stu-id="520cb-178">Secure, reliable, high-performance communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities across a network.</span></span>|  
|<span data-ttu-id="520cb-179">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-179">NetNamedPipeBinding</span></span>|<span data-ttu-id="520cb-180">Comunicación segura, de confianza y de alto rendimiento entre las entidades de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="520cb-180">Secure, reliable, high-performance communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities on the same machine.</span></span>|  
|<span data-ttu-id="520cb-181">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-181">NetMsmqBinding</span></span>|<span data-ttu-id="520cb-182">Comunicación entre las entidades de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizando MSMQ.</span><span class="sxs-lookup"><span data-stu-id="520cb-182">Communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities by using MSMQ.</span></span>|  
|<span data-ttu-id="520cb-183">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-183">MsmqIntegrationBinding</span></span>|<span data-ttu-id="520cb-184">Comunicación entre una entidad de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y otra entidad de software mediante MSMQ.</span><span class="sxs-lookup"><span data-stu-id="520cb-184">Communication between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entity and another software entity by using MSMQ.</span></span>|  
|<span data-ttu-id="520cb-185">NetPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="520cb-185">NetPeerTcpBinding</span></span>|<span data-ttu-id="520cb-186">Comunicación entre las entidades de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizando la conexión de red punto a punto de Windows.</span><span class="sxs-lookup"><span data-stu-id="520cb-186">Communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities by using Windows Peer-to-Peer Networking.</span></span>|  
  
 <span data-ttu-id="520cb-187">El enlace proporcionado por el sistema, <xref:System.ServiceModel.BasicHttpBinding>, incorpora el conjunto de protocolos admitido por los servicios web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-187">The system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>, incorporates the set of protocols supported by ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="520cb-188">Los enlaces personalizados para aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se definen fácilmente como colecciones de las clases de elementos de enlace que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza para implementar los protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="520cb-188">Custom bindings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are easily defined as collections of the binding element classes that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses to implement individual protocols.</span></span> <span data-ttu-id="520cb-189">Los nuevos elementos de enlace pueden escribirse para representar los protocolos adicionales.</span><span class="sxs-lookup"><span data-stu-id="520cb-189">New binding elements can be written to represent additional protocols.</span></span>  
  
 <span data-ttu-id="520cb-190">El comportamiento interno de los tipos de servicio puede ajustarse mediante las propiedades de una familia de clases denominadas comportamientos.</span><span class="sxs-lookup"><span data-stu-id="520cb-190">The internal behavior of service types can be adjusted using the properties of a family of classes called behaviors.</span></span> <span data-ttu-id="520cb-191">Aquí, la clase <xref:System.ServiceModel.ServiceBehaviorAttribute> se utiliza para especificar que el tipo de servicio es multiproceso.</span><span class="sxs-lookup"><span data-stu-id="520cb-191">Here, the <xref:System.ServiceModel.ServiceBehaviorAttribute> class is used to specify that the service type is to be multithreaded.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple]  
public class DerivativesCalculatorServiceType: IDerivativesCalculator  
```  
  
 <span data-ttu-id="520cb-192">Algunos comportamientos, como <xref:System.ServiceModel.ServiceBehaviorAttribute>, son atributos.</span><span class="sxs-lookup"><span data-stu-id="520cb-192">Some behaviors, like <xref:System.ServiceModel.ServiceBehaviorAttribute>, are attributes.</span></span> <span data-ttu-id="520cb-193">Otros, aquellos con las propiedades que desean establecer los administradores, pueden modificarse en la configuración de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="520cb-193">Others, the ones with properties that administrators would want to set, can be modified in the configuration of an application.</span></span>  
  
 <span data-ttu-id="520cb-194">A la hora de programar los tipos de servicio, se utiliza con frecuencia la clase <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="520cb-194">In programming service types, frequent use is made of the <xref:System.ServiceModel.OperationContext> class.</span></span> <span data-ttu-id="520cb-195">Su propiedad <xref:System.ServiceModel.OperationContext.Current%2A> estática proporciona acceso a información sobre el contexto en el que una operación se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="520cb-195">Its static <xref:System.ServiceModel.OperationContext.Current%2A> property provides access to information about the context in which an operation is running.</span></span> <span data-ttu-id="520cb-196"><xref:System.ServiceModel.OperationContext> es similar a las clases <xref:System.Web.HttpContext> y <xref:System.EnterpriseServices.ContextUtil>.</span><span class="sxs-lookup"><span data-stu-id="520cb-196"><xref:System.ServiceModel.OperationContext> is similar to both the <xref:System.Web.HttpContext> and <xref:System.EnterpriseServices.ContextUtil> classes.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="520cb-197">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="520cb-197">Hosting</span></span>  
 <span data-ttu-id="520cb-198">Los servicios web ASP.NET están compilados en un ensamblado de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="520cb-198">ASP.NET Web services are compiled into a class library assembly.</span></span> <span data-ttu-id="520cb-199">Se proporciona un archivo, denominado archivo de servicio, que posee la extensión .asmx y contiene una directiva `@ WebService`, que identifica la clase que contiene el código del servicio y el ensamblado en el que se encuentra.</span><span class="sxs-lookup"><span data-stu-id="520cb-199">A file called the service file is provided that has the extension .asmx and contains an `@ WebService` directive that identifies the class that contains the code for the service and the assembly in which it is located.</span></span>  
  
```  
<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>  
```  
  
 <span data-ttu-id="520cb-200">El archivo de servicio se copia en una raíz de la aplicación ASP.NET de Internet Information Services (IIS), y el ensamblado se copia en el subdirectorio \bin de esa raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="520cb-200">The service file is copied into an ASP.NET application root in Internet Information Services (IIS), and the assembly is copied into the \bin subdirectory of that application root.</span></span> <span data-ttu-id="520cb-201">Después, puede accederse a la aplicación mediante el identificador uniforme de recursos (URL) del archivo de servicio de la raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="520cb-201">The application is then accessible by using the uniform resource locator (URL) of the service file in the application root.</span></span>  
  
 <span data-ttu-id="520cb-202">Los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se pueden hospedar fácilmente en IIS 5.1 ó 6.0, el servicio de activación de procesos de Windows (WAS) que se proporciona junto con IIS 7.0, y en cualquier aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-202">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can readily be hosted within IIS 5.1 or 6.0, the Windows Process Activation Service (WAS) that is provided as part of IIS 7.0, and within any .NET application.</span></span> <span data-ttu-id="520cb-203">Para hospedar un servicio en IIS 5.1 ó 6.0, el servicio debe utilizar HTTP como protocolo de transporte de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="520cb-203">To host a service in IIS 5.1 or 6.0, the service must use HTTP as the communications transport protocol.</span></span>  
  
 <span data-ttu-id="520cb-204">Para hospedar un servicio en IIS 5.1, 6.0, o en WAS, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="520cb-204">To host a service within IIS 5.1, 6.0 or within WAS, use the follows steps:</span></span>  
  
1.  <span data-ttu-id="520cb-205">Compile el tipo de servicio en un ensamblado de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="520cb-205">Compile the service type into a class library assembly.</span></span>  
  
2.  <span data-ttu-id="520cb-206">Cree un archivo de servicio con una extensión .svc y una directiva `@ ServiceHost` que identifique el tipo de servicio:</span><span class="sxs-lookup"><span data-stu-id="520cb-206">Create a service file with a .svc extension with an `@ ServiceHost` directive to identify the service type:</span></span>  
  
    ```  
    <%@ServiceHost language="c#" Service="MyService" %>  
    ```  
  
3.  <span data-ttu-id="520cb-207">Copie el archivo de servicio en un directorio virtual, y el ensamblado en el subdirectorio \bin de dicho directorio.</span><span class="sxs-lookup"><span data-stu-id="520cb-207">Copy the service file into a virtual directory, and the assembly into the \bin subdirectory of that virtual directory.</span></span>  
  
4.  <span data-ttu-id="520cb-208">Copie el archivo de configuración en el directorio virtual y denomínelo Web.config.</span><span class="sxs-lookup"><span data-stu-id="520cb-208">Copy the configuration file into the virtual directory, and name it Web.config.</span></span>  
  
 <span data-ttu-id="520cb-209">A continuación, puede accederse a la aplicación mediante la dirección URL del archivo de servicio de la raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="520cb-209">The application is then accessible by using the URL of the service file in the application root.</span></span>  
  
 <span data-ttu-id="520cb-210">Para hospedar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en una aplicación .NET, compile el tipo de servicio en un ensamblado de biblioteca de clases a la que haga referencia la aplicación, y programe la aplicación para que hospede el servicio utilizando la clase <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="520cb-210">To host a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service within a .NET application, compile the service type into a class library assembly referenced by the application, and program the application to host the service using the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="520cb-211">El siguiente ejemplo muestra la programación básica requerida:</span><span class="sxs-lookup"><span data-stu-id="520cb-211">The following is an example of the basic programming required:</span></span>  
  
```  
string httpBaseAddress = "http://www.contoso.com:8000/";  
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";  
  
Uri httpBaseAddressUri = new Uri(httpBaseAddress);  
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);  
  
Uri[] baseAdresses = new Uri[] {   
 httpBaseAddressUri,  
 tcpBaseAddressUri};  
  
using(ServiceHost host = new ServiceHost(  
typeof(Service), //"Service" is the name of the service type baseAdresses))  
{  
     host.Open();  
  
     […] //Wait to receive messages  
     host.Close();  
}  
```  
  
 <span data-ttu-id="520cb-212">Este ejemplo muestra cómo se especifican las direcciones de uno o más protocolos de transporte en la construcción de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="520cb-212">This example shows how addresses for one or more transport protocols are specified in the construction of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="520cb-213">Estas direcciones se conocen como direcciones base.</span><span class="sxs-lookup"><span data-stu-id="520cb-213">These addresses are referred to as base addresses.</span></span>  
  
 <span data-ttu-id="520cb-214">La dirección proporcionada para cualquier extremo de un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está relacionada con la dirección base del host del extremo.</span><span class="sxs-lookup"><span data-stu-id="520cb-214">The address provided for any endpoint of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is an address relative to a base address of the endpoint’s host.</span></span> <span data-ttu-id="520cb-215">El host puede contar con una dirección base para cada protocolo de transporte de comunicación.</span><span class="sxs-lookup"><span data-stu-id="520cb-215">The host can have one base address for each communication transport protocol.</span></span> <span data-ttu-id="520cb-216">En la configuración de ejemplo del archivo de configuración anterior, el <xref:System.ServiceModel.BasicHttpBinding> seleccionado para el extremo utiliza HTTP como protocolo de transporte, por lo que la dirección del extremo, `EchoService`, es relativa a la dirección base HTTP del host.</span><span class="sxs-lookup"><span data-stu-id="520cb-216">In the sample configuration in the preceding configuration file, the <xref:System.ServiceModel.BasicHttpBinding> selected for the endpoint uses HTTP as the transport protocol, so the address of the endpoint, `EchoService`, is relative to the host’s HTTP base address.</span></span> <span data-ttu-id="520cb-217">En el caso del host del ejemplo anterior, la dirección base HTTP es http://www.contoso.com:8000/.</span><span class="sxs-lookup"><span data-stu-id="520cb-217">In the case of the host in the preceding example, the HTTP base address is http://www.contoso.com:8000/.</span></span> <span data-ttu-id="520cb-218">Para un servicio hospedado en IIS o WAS, la dirección base es la dirección URL del archivo de servicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-218">For a service hosted within IIS or WAS, the base address is the URL of the service’s service file.</span></span>  
  
 <span data-ttu-id="520cb-219">Solo los servicios hospedados en IIS o WAS, y configurados exclusivamente con HTTP como protocolo de transporte, pueden configurarse para utilizar la opción de modo de compatibilidad de ASP.NET de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-219">Only services hosted in IIS or WAS, and which are configured with HTTP as the transport protocol exclusively, can be made to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode option.</span></span> <span data-ttu-id="520cb-220">Los pasos siguientes son necesarios para activar esa opción.</span><span class="sxs-lookup"><span data-stu-id="520cb-220">Turning that option on requires the following steps.</span></span>  
  
1.  <span data-ttu-id="520cb-221">El programador debe agregar el atributo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> al tipo de servicio y especificar que el modo de compatibilidad de ASP.NET está permitido o es necesario.</span><span class="sxs-lookup"><span data-stu-id="520cb-221">The programmer must add the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> attribute to the service type and specify that ASP.NET compatibility mode is either allowed or required.</span></span>  
  
    ```  
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(  
          RequirementsMode=AspNetCompatbilityRequirementsMode.Require)]  
    public class DerivativesCalculatorServiceType: IDerivativesCalculator  
    ```  
  
2.  <span data-ttu-id="520cb-222">El administrador debe configurar la aplicación para utilizar el modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-222">The administrator must configure the application to use the ASP.NET compatibility mode.</span></span>  
  
    ```xml  
    <configuration>  
         <system.serviceModel>  
          <services>  
          […]  
          </services>  
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="520cb-223">Las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también pueden configurarse para utilizar .asmx como extensión de sus archivos de servicio en lugar de .svc.</span><span class="sxs-lookup"><span data-stu-id="520cb-223">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can also be configured to use .asmx as the extension for their service files rather than .svc.</span></span>  
  
    ```xml  
    <system.web>  
         <compilation>  
          <compilation debug="true">  
          <buildProviders>  
           <remove extension=".asmx"/>  
           <add extension=".asmx"   
            type="System.ServiceModel.ServiceBuildProvider,   
            Systemm.ServiceModel,   
            Version=3.0.0.0,   
            Culture=neutral,   
            PublicKeyToken=b77a5c561934e089" />  
          </buildProviders>  
          </compilation>  
         </compilation>  
    </system.web>  
    ```  
  
     <span data-ttu-id="520cb-224">Esa opción puede evitarle tener que modificar clientes configurados para utilizar las direcciones URL de archivos de servicio .asmx, cuando modifique un servicio para utilizar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-224">That option can save you from having to modify clients that are configured to use the URLs of .asmx service files when modifying a service to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="client-development"></a><span data-ttu-id="520cb-225">Desarrollo del cliente</span><span class="sxs-lookup"><span data-stu-id="520cb-225">Client Development</span></span>  
 <span data-ttu-id="520cb-226">Los clientes de los servicios web ASP.NET se generan mediante la herramienta de línea de comandos, WSDL.exe, que proporciona la dirección URL del archivo .asmx como entrada.</span><span class="sxs-lookup"><span data-stu-id="520cb-226">Clients for ASP.NET Web services are generated using the command-line tool, WSDL.exe, which provides the URL of the .asmx file as input.</span></span> <span data-ttu-id="520cb-227">La herramienta correspondiente proporcionada por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="520cb-227">The corresponding tool provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="520cb-228">Genera un módulo de código con la definición del contrato de servicios y la definición de una clase de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-228">It generates a code module with the definition of the service contract and the definition of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class.</span></span> <span data-ttu-id="520cb-229">También genera un archivo de configuración con la dirección y el enlace del servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-229">It also generates a configuration file with the address and binding of the service.</span></span>  
  
 <span data-ttu-id="520cb-230">Generalmente, cuando se programa un cliente de un servicio remoto resulta aconsejable realizar la programación de acuerdo con un patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="520cb-230">In programming a client of a remote service it is generally advisable to program according to an asynchronous pattern.</span></span> <span data-ttu-id="520cb-231">El código generado por la herramienta WSDL.exe siempre proporciona, de manera predeterminada, un patrón sincrónico y otro asincrónico.</span><span class="sxs-lookup"><span data-stu-id="520cb-231">The code generated by the WSDL.exe tool always provides for both a synchronous and an asynchronous pattern by default.</span></span> <span data-ttu-id="520cb-232">El código generado por el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) puede proporcionar cualquier patrón.</span><span class="sxs-lookup"><span data-stu-id="520cb-232">The code generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can provide for either pattern.</span></span> <span data-ttu-id="520cb-233">Proporciona el patrón sincrónico de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="520cb-233">It provides for the synchronous pattern by default.</span></span> <span data-ttu-id="520cb-234">Si se ejecuta la herramienta con el modificador `/async`, el código generado proporciona el patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="520cb-234">If the tool is executed with the `/async` switch, then the generated code provides for the asynchronous pattern.</span></span>  
  
 <span data-ttu-id="520cb-235">No existe garantía de que los nombres en las clases de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generadas, de forma predeterminada, por la herramienta WSDL.exe de ASP.NET coincidan con los nombres en las clases de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generadas por la herramienta Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="520cb-235">There is no guarantee that names in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client classes generated by ASP.NET’s WSDL.exe tool, by default, match the names in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client classes generated by the Svcutil.exe tool.</span></span> <span data-ttu-id="520cb-236">En concreto, a los nombres de las propiedades de clases que deben serializarse mediante <xref:System.Xml.Serialization.XmlSerializer>, se les asigna, de forma predeterminada, el sufijo Property en el código generado por la herramienta Svcutil.exe, lo que no ocurre en el caso de la herramienta WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="520cb-236">In particular, the names of the properties of classes that have to be serialized using the <xref:System.Xml.Serialization.XmlSerializer> are, by default, given the suffix Property in the code generated by the Svcutil.exe tool, which is not the case with the WSDL.exe tool.</span></span>  
  
## <a name="message-representation"></a><span data-ttu-id="520cb-237">Representación de mensajes</span><span class="sxs-lookup"><span data-stu-id="520cb-237">Message Representation</span></span>  
 <span data-ttu-id="520cb-238">Los encabezados de los mensajes SOAP enviados y recibidos por los servicios web ASP.NET puede personalizarse.</span><span class="sxs-lookup"><span data-stu-id="520cb-238">The headers of the SOAP messages sent and received by ASP.NET Web services can be customized.</span></span> <span data-ttu-id="520cb-239">Una clase se deriva de <xref:System.Web.Services.Protocols.SoapHeader> para definir la estructura del encabezado y, a continuación, <xref:System.Web.Services.Protocols.SoapHeaderAttribute> se utiliza para indicar la presencia del mismo.</span><span class="sxs-lookup"><span data-stu-id="520cb-239">A class is derived from <xref:System.Web.Services.Protocols.SoapHeader> to define the structure of the header, and then the <xref:System.Web.Services.Protocols.SoapHeaderAttribute> is used to indicate the presence of the header.</span></span>  
  
```  
public class SomeProtocol : SoapHeader  
{  
     public long CurrentValue;  
     public long Total;  
}  
  
[WebService]  
public interface IEcho  
{  
     SomeProtocol ProtocolHeader  
     {  
      get;  
     set;  
     }  
  
     [WebMethod]  
     [SoapHeader("ProtocolHeader")]  
     string PlaceOrders(PurchaseOrderType order);  
}  
  
public class Service: WebService, IEcho  
{  
     private SomeProtocol protocolHeader;  
  
     public SomeProtocol ProtocolHeader  
     {  
         get  
         {  
              return this.protocolHeader;  
         }  
  
         set  
         {  
              this.protocolHeader = value;  
         }  
     }  
  
     string PlaceOrders(PurchaseOrderType order)  
     {  
         long currentValue = this.protocolHeader.CurrentValue;  
     }  
}  
```  
  
 <span data-ttu-id="520cb-240">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona los atributos, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>y <xref:System.ServiceModel.MessageBodyMemberAttribute> para describir la estructura de los mensajes SOAP enviados y recibidos por un servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-240">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides the attributes, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, and <xref:System.ServiceModel.MessageBodyMemberAttribute> to describe the structure of the SOAP messages sent and received by a service.</span></span>  
  
```  
[DataContract]  
public class SomeProtocol  
{  
     [DataMember]  
     public long CurrentValue;  
     [DataMember]  
     public long Total;  
}  
  
[DataContract]  
public class Item  
{  
     [DataMember]  
     public string ItemNumber;  
     [DataMember]  
     public decimal Quantity;  
     [DataMember]  
     public decimal UnitPrice;  
}  
  
[MessageContract]  
public class ItemMesage  
{  
     [MessageHeader]  
     public SomeProtocol ProtocolHeader;  
     [MessageBody]  
     public Item Content;  
}  
  
[ServiceContract]  
public interface IItemService  
{  
     [OperationContract]  
     public void DeliverItem(ItemMessage itemMessage);  
}  
```  
  
 <span data-ttu-id="520cb-241">Esta sintaxis produce una representación explícita de la estructura de los mensajes, mientras que en el código de un servicio web ASP.NET la estructura de mensajes está implícita.</span><span class="sxs-lookup"><span data-stu-id="520cb-241">This syntax yields an explicit representation of the structure of the messages, whereas the structure of messages is implied by the code of an ASP.NET Web service.</span></span> <span data-ttu-id="520cb-242">Además, en la sintaxis ASP.NET, los encabezados del mensaje se representan como propiedades del servicio, como la propiedad `ProtocolHeader` en el ejemplo anterior, mientras que en la sintaxis [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se representan con más precisión, como propiedades de mensajes.</span><span class="sxs-lookup"><span data-stu-id="520cb-242">Also, in the ASP.NET syntax, message headers are represented as properties of the service, such as the `ProtocolHeader` property in the previous example, whereas in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] syntax, they are more accurately represented as properties of messages.</span></span> <span data-ttu-id="520cb-243">Asimismo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite agregar los encabezados del mensaje a la configuración de extremos.</span><span class="sxs-lookup"><span data-stu-id="520cb-243">Also, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows message headers to be added to the configuration of endpoints.</span></span>  
  
```xml  
<service name="Service ">  
     <endpoint   
      address="EchoService"  
      binding="basicHttpBinding"  
      contract="IEchoService ">  
      <headers>  
      <dsig:X509Certificate   
       xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">  
       ...  
      </dsig:X509Certificate>  
      </headers>  
     </endpoint>  
</service>  
```  
  
 <span data-ttu-id="520cb-244">Esa opción permite evitar cualquier referencia a los encabezados de protocolo de la infraestructura en el código de un cliente o servicio: los encabezados se agregan a los mensajes debido a cómo se configura el extremo.</span><span class="sxs-lookup"><span data-stu-id="520cb-244">That option allows you to avoid any reference to infrastructural protocol headers in the code for a client or service: the headers are added to messages because of how the endpoint is configured.</span></span>  
  
## <a name="service-description"></a><span data-ttu-id="520cb-245">Descripción del servicio</span><span class="sxs-lookup"><span data-stu-id="520cb-245">Service Description</span></span>  
 <span data-ttu-id="520cb-246">Emitir una solicitud GET de HTTP para el archivo .asmx de un servicio web ASP.NET con el WSDL de la consulta, provoca que ASP.NET genere WSDL para describir el servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-246">Issuing an HTTP GET request for the .asmx file of an ASP.NET Web service with the query WSDL causes ASP.NET to generate WSDL to describe the service.</span></span> <span data-ttu-id="520cb-247">Devuelve ese WSDL como respuesta a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="520cb-247">It returns that WSDL as the response to the request.</span></span>  
  
 <span data-ttu-id="520cb-248">ASP.NET 2.0 permitió validar si un servicio es conforme a Basic Profile 1.1 de Web Services-Interoperability Organization (WS-I), e insertar una notificación informando de que el servicio es conforme a su WSDL.</span><span class="sxs-lookup"><span data-stu-id="520cb-248">ASP.NET 2.0 made it possible to validate that a service is compliant with the Basic Profile 1.1 of the Web Services-Interoperability Organization (WS-I), and to insert a claim that the service is compliant into its WSDL.</span></span> <span data-ttu-id="520cb-249">Esto se lleva a cabo utilizando `ConformsTo` y los parámetros `EmitConformanceClaims` del atributo <xref:System.Web.Services.WebServiceBindingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="520cb-249">That is done using the `ConformsTo` and `EmitConformanceClaims` parameters of the <xref:System.Web.Services.WebServiceBindingAttribute> attribute.</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="520cb-250">Se puede personalizar el WSDL que genera ASP.NET para un servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-250">The WSDL that ASP.NET generates for a service can be customized.</span></span> <span data-ttu-id="520cb-251">Las personalización se realiza creando una clase derivada de <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension>, para agregar elementos a WSDL.</span><span class="sxs-lookup"><span data-stu-id="520cb-251">Customizations are made by creating a derived class of <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> to add items to the WSDL.</span></span>  
  
 <span data-ttu-id="520cb-252">La emisión de una solicitud GET de HTTP con el WSDL de la consulta para el archivo .svc de un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], con un extremo HTTP hospedado en IIS 51, 6.0 o WAS, da lugar a que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responda con WSDL para describir el servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-252">Issuing an HTTP GET request with the query WSDL for the .svc file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with an HTTP endpoint hosted within IIS 51, 6.0 or WAS causes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to respond with WSDL to describe the service.</span></span> <span data-ttu-id="520cb-253">Establecer httpGetEnabled en true tiene el mismo efecto que enviar una solicitud HTTP GET con el WSDL de la consulta a la dirección base HTTP de un servicio hospedado en una aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-253">Issuing an HTTP GET request with the query WSDL to the HTTP base address of a service hosted within a .NET application has the same effect if httpGetEnabled is set to true.</span></span>  
  
 <span data-ttu-id="520cb-254">Sin embargo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también responde a las solicitudes de WS-MetadataExchange con el WSDL que genera para describir un servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-254">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] also responds to WS-MetadataExchange requests with WSDL that it generates to describe a service.</span></span> <span data-ttu-id="520cb-255">Los servicios web ASP.NET no tienen compatibilidad integrada con las solicitudes de WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="520cb-255">ASP.NET Web services do not have built-in support for WS-MetadataExchange requests.</span></span>  
  
 <span data-ttu-id="520cb-256">Se puede personalizar ampliamente el WSDL que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera.</span><span class="sxs-lookup"><span data-stu-id="520cb-256">The WSDL that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates can be extensively customized.</span></span> <span data-ttu-id="520cb-257">La clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> proporciona algunas funciones para personalizar el WSDL.</span><span class="sxs-lookup"><span data-stu-id="520cb-257">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class provides some facilities for customizing the WSDL.</span></span> <span data-ttu-id="520cb-258">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también puede configurarse para no generar WSDL, sino usar un archivo WSDL estático en una dirección URL determinada.</span><span class="sxs-lookup"><span data-stu-id="520cb-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can also be configured to not generate WSDL, but rather to use a static WSDL file at a given URL.</span></span>  
  
```xml  
<behaviors>  
     <behavior name="DescriptionBehavior">  
     <metadataPublishing   
      enableMetadataExchange="true"   
      enableGetWsdl="true"   
      enableHelpPage="true"   
      metadataLocation=  
      "http://localhost/DerivativesCalculatorService/Service.WSDL"/>  
     </behavior>  
</behaviors>  
```  
  
## <a name="exception-handling"></a><span data-ttu-id="520cb-259">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="520cb-259">Exception Handling</span></span>  
 <span data-ttu-id="520cb-260">En los servicios web ASP.NET, las excepciones no controladas se devuelven a los clientes como errores de SOAP.</span><span class="sxs-lookup"><span data-stu-id="520cb-260">In ASP.NET Web services, unhandled exceptions are returned to clients as SOAP faults.</span></span> <span data-ttu-id="520cb-261">También puede iniciar explícitamente instancias de la clase <xref:System.Web.Services.Protocols.SoapException> y tener más control sobre el contenido del error de SOAP que se transmite al cliente.</span><span class="sxs-lookup"><span data-stu-id="520cb-261">You can also explicitly throw instances of the <xref:System.Web.Services.Protocols.SoapException> class and have more control over the content of the SOAP fault that gets transmitted to the client.</span></span>  
  
 <span data-ttu-id="520cb-262">En servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las excepciones no controladas no se devuelven a los clientes como errores de SOAP para evitar la exposición involuntaria de información confidencial a través de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="520cb-262">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, unhandled exceptions are not returned to clients as SOAP faults to prevent sensitive information being inadvertently exposed through the exceptions.</span></span> <span data-ttu-id="520cb-263">Se proporciona un valor de configuración para devolver las excepciones no controladas a los clientes con el propósito de depurarlas.</span><span class="sxs-lookup"><span data-stu-id="520cb-263">A configuration setting is provided to have unhandled exceptions returned to clients for the purpose of debugging.</span></span>  
  
 <span data-ttu-id="520cb-264">Para devolver los errores de SOAP a los clientes, puede iniciar las instancias del tipo genérico, <xref:System.ServiceModel.FaultException%601>, utilizando el tipo de contrato de datos como tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="520cb-264">To return SOAP faults to clients, you can throw instances of the generic type, <xref:System.ServiceModel.FaultException%601>, using the data contract type as the generic type.</span></span> <span data-ttu-id="520cb-265">Además, puede agregar los atributos <xref:System.ServiceModel.FaultContractAttribute> a las operaciones para especificar los errores que podría producir una operación.</span><span class="sxs-lookup"><span data-stu-id="520cb-265">You can also add <xref:System.ServiceModel.FaultContractAttribute> attributes to operations to specify the faults that an operation might yield.</span></span>  
  
```  
[DataContract]  
public class MathFault  
{   
     [DataMember]  
     public string operation;  
     [DataMember]  
     public string problemType;  
}  
  
[ServiceContract]  
public interface ICalculator  
{  
     [OperationContract]  
     [FaultContract(typeof(MathFault))]  
     int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="520cb-266">Con esto, los posibles errores podrían anunciarse en el WSDL del servicio, lo que permitiría a los desarrolladores del cliente anticipar qué errores pueden ser el resultado de una operación, y escribir las instrucciones de captura adecuadas.</span><span class="sxs-lookup"><span data-stu-id="520cb-266">Doing so results in the possible faults being advertised in the WSDL for the service, allowing client programmers to anticipate which faults can result from an operation, and write the appropriate catch statements.</span></span>  
  
```  
try  
{  
     result = client.Divide(value1, value2);  
}  
catch (FaultException<MathFault> e)  
{  
 Console.WriteLine("FaultException<MathFault>: Math fault while doing "  
  + e.Detail.operation   
  + ". Problem: "   
  + e.Detail.problemType);  
}  
```  
  
## <a name="state-management"></a><span data-ttu-id="520cb-267">Administración de estado</span><span class="sxs-lookup"><span data-stu-id="520cb-267">State Management</span></span>  
 <span data-ttu-id="520cb-268">La clase utilizada para implementar un servicio web ASP.NET se puede derivar de <xref:System.Web.Services.WebService>.</span><span class="sxs-lookup"><span data-stu-id="520cb-268">The class used to implement an ASP.NET Web service may be derived from <xref:System.Web.Services.WebService>.</span></span>  
  
```  
public class Service : WebService, IEcho  
{  
  
 public string Echo(string input)  
 {  
  return input;  
 }  
}  
```  
  
 <span data-ttu-id="520cb-269">En ese caso, la clase puede programarse para utilizar la propiedad del contexto de la clase base <xref:System.Web.Services.WebService> para tener acceso a un objeto <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="520cb-269">In that case, the class can be programmed to use the <xref:System.Web.Services.WebService> base class’ Context property to access a <xref:System.Web.HttpContext> object.</span></span> <span data-ttu-id="520cb-270">Se puede utilizar el objeto <xref:System.Web.HttpContext> para actualizar y recuperar información del estado de la aplicación mediante su propiedad Application, y puede utilizarse para actualizar y recuperar información del estado de la sesión utilizando su propiedad Session.</span><span class="sxs-lookup"><span data-stu-id="520cb-270">The <xref:System.Web.HttpContext> object can be used to update and retrieve application state information by using its Application property, and can be used to update and retrieve session state information by using its Session property.</span></span>  
  
 <span data-ttu-id="520cb-271">ASP.NET proporciona un control considerable sobre dónde se almacena realmente la información del estado de la sesión a la que se accedió mediante la propiedad Session de <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="520cb-271">ASP.NET provides considerable control over where the session state information accessed by using the Session property of the <xref:System.Web.HttpContext> is actually stored.</span></span> <span data-ttu-id="520cb-272">Puede almacenarse en cookies, en una base de datos, en la memoria del servidor actual o en la memoria de un servidor designado.</span><span class="sxs-lookup"><span data-stu-id="520cb-272">It may be stored in cookies, in a database, in the memory of the current server, or in the memory of a designated server.</span></span> <span data-ttu-id="520cb-273">La elección se realiza en el archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-273">The choice is made in the service’s configuration file.</span></span>  
  
 <span data-ttu-id="520cb-274">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona objetos extensibles para la administración de estados.</span><span class="sxs-lookup"><span data-stu-id="520cb-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides extensible objects for state management.</span></span> <span data-ttu-id="520cb-275">Los objetos extensibles son objetos que implementan <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="520cb-275">Extensible objects are objects that implement <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="520cb-276">Los objetos extensibles más importantes son <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="520cb-276">The most important extensible objects are <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="520cb-277">`ServiceHostBase` permite mantener el estado al que pueden tener acceso todas las instancias de todos los tipos de servicio en el mismo host, mientras que `InstanceContext` permite mantener el estado al que puede tener acceso cualquier código que se ejecute dentro de la misma instancia de un tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-277">`ServiceHostBase` allows you to maintain state that all of the instances of all of the service types on the same host can access, while `InstanceContext` allows you to maintain state that can be accessed by any code running within the same instance of a service type.</span></span>  
  
 <span data-ttu-id="520cb-278">Aquí, el tipo de servicio, `TradingSystem`, tiene un <xref:System.ServiceModel.ServiceBehaviorAttribute> que especifica que todas las llamadas desde la misma instancia de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se enruten a la misma instancia del tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-278">Here, the service type, `TradingSystem`, has a <xref:System.ServiceModel.ServiceBehaviorAttribute> that specifies that all calls from the same [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client instance are routed to the same instance of the service type.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class TradingSystem: ITradingService  
```  
  
 <span data-ttu-id="520cb-279">La clase, `DealData`, define el estado al que puede acceder cualquier código que se ejecute en la misma instancia de un tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-279">The class, `DealData`, defines state that can be accessed by any code running in the same instance of a service type.</span></span>  
  
```  
internal class DealData: IExtension<InstanceContext>  
{  
 public string DealIdentifier = null;  
 public Trade[] Trades = null;  
}  
```  
  
 <span data-ttu-id="520cb-280">En el código del tipo de servicio que implementa una de las operaciones del contrato de servicios, se agrega un objeto de estados `DealData` al estado de la instancia actual del tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="520cb-280">In the code of the service type that implements one of the operations of the service contract, a `DealData` state object is added to the state of the current instance of the service type.</span></span>  
  
```  
string ITradingService.BeginDeal()  
{  
 string dealIdentifier = Guid.NewGuid().ToString();  
 DealData state = new DealData(dealIdentifier);  
 OperationContext.Current.InstanceContext.Extensions.Add(state);  
 return dealIdentifier;  
}  
```  
  
 <span data-ttu-id="520cb-281">Después, el código que implementa otras operaciones del contrato de servicio puede recuperar y modificar ese objeto de estados.</span><span class="sxs-lookup"><span data-stu-id="520cb-281">That state object can then be retrieved and modified by the code that implements another of the service contract’s operations.</span></span>  
  
```  
void ITradingService.AddTrade(Trade trade)  
{  
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();  
 dealData.AddTrade(trade);  
}  
```  
  
 <span data-ttu-id="520cb-282">Mientras que ASP.NET permite controlar dónde se almacena realmente la información de estado en la clase <xref:System.Web.HttpContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], al menos en su versión inicial, no proporciona ningún control sobre dónde se almacenan los objetos extensibles.</span><span class="sxs-lookup"><span data-stu-id="520cb-282">Whereas ASP.NET provides control over where state information in the <xref:System.Web.HttpContext> class is actually stored, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], at least in its initial version, provides no control over where extensible objects are stored.</span></span> <span data-ttu-id="520cb-283">Eso constituye la mejor razón para seleccionar el modo de compatibilidad de ASP.NET para un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-283">That constitutes the very best reason for selecting the ASP.NET compatibility mode for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="520cb-284">Si la administración de estados configurable es imperativa, optar por el modo de compatibilidad de ASP.NET permite utilizar las funciones de la clase <xref:System.Web.HttpContext> exactamente igual a como se utilizan en ASP.NET, y, además, configurar dónde se almacena la información gestionada mediante la clase <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="520cb-284">If configurable state management is imperative, then opting for the ASP.NET compatibility mode allows you to use the facilities of the <xref:System.Web.HttpContext> class exactly as they are used in ASP.NET, and also to configure where state information managed by using the <xref:System.Web.HttpContext> class is stored.</span></span>  
  
## <a name="security"></a><span data-ttu-id="520cb-285">Seguridad</span><span class="sxs-lookup"><span data-stu-id="520cb-285">Security</span></span>  
 <span data-ttu-id="520cb-286">Las opciones para proteger los servicios web ASP.NET son las mismas que para proteger cualquier aplicación IIS.</span><span class="sxs-lookup"><span data-stu-id="520cb-286">The options for securing ASP.NET Web services are those for securing any IIS application.</span></span> <span data-ttu-id="520cb-287">Dado que las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no solo pueden hospedarse en IIS sino también en cualquier ejecutable de .NET, las opciones para proteger las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deben ser independientes de las funciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="520cb-287">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can be hosted not only within IIS but also within any .NET executable, the options for securing [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications must be made independent from the facilities of IIS.</span></span> <span data-ttu-id="520cb-288">No obstante, las funciones proporcionadas para los servicios web ASP.NET también están disponibles para los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-288">However, the facilities provided for ASP.NET Web services are also available for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running in ASP.NET compatibility mode.</span></span>  
  
### <a name="security-authentication"></a><span data-ttu-id="520cb-289">Seguridad: autenticación</span><span class="sxs-lookup"><span data-stu-id="520cb-289">Security: Authentication</span></span>  
 <span data-ttu-id="520cb-290">IIS proporciona funciones para controlar el acceso a las aplicaciones que permiten seleccionar un acceso anónimo, o una variedad de modos de autenticación: autenticación de Windows, autenticación implícita, autenticación básica y autenticación de .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="520cb-290">IIS provides facilities for controlling access to applications by which you can select either anonymous access or a variety of modes of authentication: Windows Authentication, Digest Authentication, Basic Authentication, and .NET Passport Authentication.</span></span> <span data-ttu-id="520cb-291">La opción de autenticación de Windows puede utilizarse para controlar el acceso a los servicios web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-291">The Windows Authentication option can be used to control access to ASP.NET Web services.</span></span> <span data-ttu-id="520cb-292">Sin embargo, cuando las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se hospedan en IIS, IIS debe configurarse para permitir el acceso anónimo a la aplicación, de modo que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede administrar la autenticación, lo que, entre otras opciones, es compatible con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="520cb-292">However, when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are hosted within IIS, IIS must be configured to permit anonymous access to the application, so that authentication can be managed by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] itself, which does support Windows authentication among various other options.</span></span> <span data-ttu-id="520cb-293">Las otras opciones integradas incluyen tokens del nombre de usuario, certificados X.509, tokens SAML, y tarjeta CardSpace, aunque también pueden definirse otros mecanismos de autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="520cb-293">The other options that are built-in include username tokens, X.509 certificates, SAML tokens, and CardSpace card, but custom authentication mechanisms can also be defined.</span></span>  
  
### <a name="security-impersonation"></a><span data-ttu-id="520cb-294">Seguridad: suplantación</span><span class="sxs-lookup"><span data-stu-id="520cb-294">Security: Impersonation</span></span>  
 <span data-ttu-id="520cb-295">ASP.NET proporciona un elemento de identidad por el que un servicio web ASP.NET puede suplantar a un usuario determinado, o a cualquier credencial de usuario proporcionada por la solicitud actual.</span><span class="sxs-lookup"><span data-stu-id="520cb-295">ASP.NET provides an identity element by which an ASP.NET Web service can be made to impersonate a particular user or whichever user’s credentials are provided with the current request.</span></span> <span data-ttu-id="520cb-296">Ese elemento puede utilizarse para configurar la suplantación en aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-296">That element can be used to configure impersonation in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications running in ASP.NET compatibility mode.</span></span>  
  
 <span data-ttu-id="520cb-297">El sistema de configuración [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona su propio elemento de identidad para designar al usuario concreto que se suplanta.</span><span class="sxs-lookup"><span data-stu-id="520cb-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration system provides its own identity element for designating a particular user to impersonate.</span></span> <span data-ttu-id="520cb-298">Además, los clientes y servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden configurarse de manera independiente para la suplantación.</span><span class="sxs-lookup"><span data-stu-id="520cb-298">Also, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients and services can be independently configured for impersonation.</span></span> <span data-ttu-id="520cb-299">Los clientes pueden configurarse para suplantar al usuario actual cuando transmiten las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="520cb-299">Clients can be configured to impersonate the current user when they transmit requests.</span></span>  
  
```xml  
<behaviors>  
     <behavior name="DerivativesCalculatorClientBehavior">  
      <clientCredentials>  
      <windows allowedImpersonationLevel="Impersonation"/>  
      </clientCredentials>  
     </behavior>  
</behaviors>  
```  
  
 <span data-ttu-id="520cb-300">Las operaciones del servicio pueden configurarse para suplantar cualquier credencial de usuario proporcionada con la solicitud actual.</span><span class="sxs-lookup"><span data-stu-id="520cb-300">Service operations can be configured to impersonate whichever user’s credentials are provided with the current request.</span></span>  
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public void Receive(Message input)  
```  
  
### <a name="security-authorization-using-access-control-lists"></a><span data-ttu-id="520cb-301">Seguridad: autorización mediante las listas de control de acceso</span><span class="sxs-lookup"><span data-stu-id="520cb-301">Security: Authorization using Access Control Lists</span></span>  
 <span data-ttu-id="520cb-302">Las listas de control de acceso (ACL) pueden utilizarse para restringir el acceso a los archivos .asmx.</span><span class="sxs-lookup"><span data-stu-id="520cb-302">Access Control Lists (ACLs) can be used to restrict access to .asmx files.</span></span> <span data-ttu-id="520cb-303">Sin embargo, las ACL de los archivos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].svc se omiten excepto en el modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-303">However, ACLs on [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .svc files are ignored except in ASP.NET compatibility mode.</span></span>  
  
### <a name="security-role-based-authorization"></a><span data-ttu-id="520cb-304">Seguridad: autorización basada en funciones</span><span class="sxs-lookup"><span data-stu-id="520cb-304">Security: Role-based Authorization</span></span>  
 <span data-ttu-id="520cb-305">La opción de autenticación de Windows de IIS puede utilizarse, junto con el elemento de autorización proporcionado por el lenguaje de configuración de ASP.NET, para facilitar la autorización basada en las funciones de los servicios web ASP.NET basados en los grupos de Windows a los que están asignados los usuarios.</span><span class="sxs-lookup"><span data-stu-id="520cb-305">The IIS Windows Authentication option can be used in conjunction with the authorization element provided by the ASP.NET configuration language to facilitate role-based authorization for ASP.NET Web services based on the Windows groups to which users are assigned.</span></span> <span data-ttu-id="520cb-306">ASP.NET 2.0 introdujo un mecanismo de autorización basado en funciones más general: proveedores de funciones.</span><span class="sxs-lookup"><span data-stu-id="520cb-306">ASP.NET 2.0 introduced a more general role-based authorization mechanism: role providers.</span></span>  
  
 <span data-ttu-id="520cb-307">Los proveedores de funciones son clases que implementan una interfaz básica para informarse sobre las funciones a las que está asignado un usuario, pero cada proveedor de funciones sabe cómo recuperar esa información desde un origen diferente.</span><span class="sxs-lookup"><span data-stu-id="520cb-307">Role providers are classes that all implement a basic interface for enquiring about the roles to which a user is assigned, but each role provider knows how to retrieve that information from a different source.</span></span> <span data-ttu-id="520cb-308">ASP.NET 2.0 proporciona un proveedor de funciones que puede recuperar las asignaciones de funciones de una base de datos de Microsoft SQL Server ,y otro que puede recuperar las asignaciones de funciones del administrador de autorización de Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="520cb-308">ASP.NET 2.0 provides a role provider that can retrieve role assignments from a Microsoft SQL Server database, and another that can retrieve role assignments from the Windows Server 2003 Authorization Manager.</span></span>  
  
 <span data-ttu-id="520cb-309">El mecanismo del proveedor de funciones puede utilizarse de manera independiente de ASP.NET en cualquier aplicación de .NET, incluso una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="520cb-309">The role provider mechanism can actually be used independently of ASP.NET in any .NET application, including a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="520cb-310">La siguiente configuración de ejemplo para una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] muestra cómo el uso de un proveedor de roles de ASP.NET es una opción seleccionada mediante <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span><span class="sxs-lookup"><span data-stu-id="520cb-310">The following sample configuration for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application shows how the use of an ASP.NET role provider is an option selected by means of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>  
  
```xml  
<system.serviceModel>  
     <services>  
         <service name="Service.ResourceAccessServiceType"   
             behaviorConfiguration="ServiceBehavior">  
             <endpoint   
              address="ResourceAccessService"   
              binding="wsHttpBinding"   
              contract="Service.IResourceAccessContract"/>  
         </service>  
     </services>  
     <behaviors>  
       <behavior name="ServiceBehavior">  
       <serviceAuthorization principalPermissionMode="UseAspNetRoles"/>  
      </behavior>  
     </behaviors>  
</system.serviceModel>  
```  
  
### <a name="security-claims-based-authorization"></a><span data-ttu-id="520cb-311">Seguridad: autorización basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="520cb-311">Security: Claims-based Authorization</span></span>  
 <span data-ttu-id="520cb-312">Una de las innovaciones más importantes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es su compatibilidad para autorizar el acceso a los recursos protegidos basándose en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="520cb-312">One of the most important innovations of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is its thorough support for authorizing access to protected resources based on claims.</span></span> <span data-ttu-id="520cb-313">Las notificaciones se componen de un tipo, un derecho y un valor, por ejemplo, el número del permiso de conducir.</span><span class="sxs-lookup"><span data-stu-id="520cb-313">Claims consist of a type, a right and a value, a drivers’ license, for example.</span></span> <span data-ttu-id="520cb-314">Realiza un conjunto de notificaciones sobre el portador, una de las cuales es la fecha de nacimiento del portador.</span><span class="sxs-lookup"><span data-stu-id="520cb-314">It makes a set of claims about the bearer, one of which is the bearer’s date of birth.</span></span> <span data-ttu-id="520cb-315">El tipo de esa notificación es “fecha de nacimiento”, y el valor de la notificación la fecha de nacimiento del conductor.</span><span class="sxs-lookup"><span data-stu-id="520cb-315">The type of that claim is date of birth, while the value of the claim is the driver’s birth date.</span></span> <span data-ttu-id="520cb-316">El derecho que confiere una notificación al portador especifica lo que el portador puede hacer con el valor de la notificación.</span><span class="sxs-lookup"><span data-stu-id="520cb-316">The right that a claim confers on the bearer specifies what the bearer can do with the claim’s value.</span></span> <span data-ttu-id="520cb-317">En el caso de la notificación de la fecha de nacimiento del conductor, el derecho es la posesión: el conductor posee esa fecha de nacimiento pero, por ejemplo, no puede modificarla.</span><span class="sxs-lookup"><span data-stu-id="520cb-317">In the case of the claim of the driver’s date of birth, the right is possession: the driver possesses that date of birth but cannot, for example, alter it.</span></span> <span data-ttu-id="520cb-318">La autorización basada en notificaciones engloba a la autorización basada en funciones, ya que las funciones son un tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="520cb-318">Claims-based authorization encloses role-based authorization, because roles are a type of claim.</span></span>  
  
 <span data-ttu-id="520cb-319">La autorización basada en notificaciones finaliza con la comparación de un conjunto de notificaciones con los requisitos de acceso de la operación y, dependiendo del resultado de esa comparación, se otorga o se deniega el acceso a la operación.</span><span class="sxs-lookup"><span data-stu-id="520cb-319">Authorization based on claims is accomplished by comparing a set of claims to the access requirements of the operation and, depending on the outcome of that comparison, granting or denying access to the operation.</span></span> <span data-ttu-id="520cb-320">En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], puede especificar una clase para ejecutar la autorización basada en notificaciones, una vez más asignando un valor a la propiedad `ServiceAuthorizationManager` de <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span><span class="sxs-lookup"><span data-stu-id="520cb-320">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you can specify a class to use to run claims-based authorization, once again by assigning a value to the `ServiceAuthorizationManager` property of <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>  
  
```xml  
<behaviors>  
     <behavior name='ServiceBehavior'>  
     <serviceAuthorization   
     serviceAuthorizationManagerType=  
                   'Service.AccessChecker, Service' />  
     </behavior>  
</behaviors>  
```  
  
 <span data-ttu-id="520cb-321">Las clases usadas para ejecutar la autorización basada en notificaciones deben derivar de <xref:System.ServiceModel.ServiceAuthorizationManager>, que tiene un solo método para reemplazar, `AccessCheck()`.</span><span class="sxs-lookup"><span data-stu-id="520cb-321">Classes used to run claims-based authorization must derive from <xref:System.ServiceModel.ServiceAuthorizationManager>, which has just one method to override, `AccessCheck()`.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="520cb-322"> llama a ese método siempre que se invoca una operación del servicio y proporciona un objeto <xref:System.ServiceModel.OperationContext>, que tiene las notificaciones para el usuario en su propiedad `ServiceSecurityContext.AuthorizationContext`.</span><span class="sxs-lookup"><span data-stu-id="520cb-322"> calls that method whenever an operation of the service is invoked and provides a <xref:System.ServiceModel.OperationContext> object, which has the claims for the user in its `ServiceSecurityContext.AuthorizationContext` property.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="520cb-323"> ensambla las notificaciones sobre el usuario del token de seguridad suministrado por el usuario para la autenticación, que deja la tarea de evaluar si esas notificaciones son suficientes para la operación en cuestión.</span><span class="sxs-lookup"><span data-stu-id="520cb-323"> does the work of assembling claims about the user from whatever security token the user provided for authentication, which leaves the of task of evaluating whether those claims suffice for the operation in question.</span></span>  
  
 <span data-ttu-id="520cb-324">Que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ensamble automáticamente las notificaciones de cualquier tipo de token de seguridad es una innovación muy significativa, ya que independiza totalmente el código para la autorización basada en notificaciones del mecanismo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="520cb-324">That [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically assembles claims from any kind of security token is a highly significant innovation, because it makes the code for authorization based on the claims entirely independent of the authentication mechanism.</span></span> <span data-ttu-id="520cb-325">Por el contrario, la autorización mediante las ACL o las funciones de ASP.NET está estrechamente vinculada a la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="520cb-325">By contrast, authorization using ACLs or roles in ASP.NET is closely tied to Windows authentication.</span></span>  
  
### <a name="security-confidentiality"></a><span data-ttu-id="520cb-326">Seguridad: confidencialidad</span><span class="sxs-lookup"><span data-stu-id="520cb-326">Security: Confidentiality</span></span>  
 <span data-ttu-id="520cb-327">La confidencialidad de los mensajes intercambiados con los servicios web de ASP.NET puede protegerse en el nivel de transporte configurando la aplicación de IIS para que utilice el protocolo de transferencia segura de hipertexto (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="520cb-327">The confidentiality of messages exchanged with ASP.NET Web services can be ensured at the transport level by configuring the application within IIS to use the Secure Hypertext Transfer Protocol (HTTPS).</span></span> <span data-ttu-id="520cb-328">Esto mismo puede hacerse con las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedadas en IIS.</span><span class="sxs-lookup"><span data-stu-id="520cb-328">The same can be done for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications hosted within IIS.</span></span> <span data-ttu-id="520cb-329">No obstante, las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedadas fuera de IIS también pueden configurarse para que utilicen un protocolo de transporte seguro.</span><span class="sxs-lookup"><span data-stu-id="520cb-329">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications hosted outside of IIS can also be configured to use a secure transport protocol.</span></span> <span data-ttu-id="520cb-330">Lo que es más importante, las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también pueden configurarse para proteger los mensajes antes de su transportarse, mediante el protocolo WS-Security.</span><span class="sxs-lookup"><span data-stu-id="520cb-330">More important, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can also be configured to secure the messages before they are transported, using the WS-Security protocol.</span></span> <span data-ttu-id="520cb-331">Simplemente protegiendo el cuerpo de un mensaje mediante WS-Security, permite su transmisión confidencial a través de intermediarios antes de alcanzar su último destino.</span><span class="sxs-lookup"><span data-stu-id="520cb-331">Securing just the body of a message using WS-Security allows it to be transmitted confidentially across intermediaries before reaching its final destination.</span></span>  
  
## <a name="globalization"></a><span data-ttu-id="520cb-332">Globalización</span><span class="sxs-lookup"><span data-stu-id="520cb-332">Globalization</span></span>  
 <span data-ttu-id="520cb-333">El lenguaje de configuración de ASP.NET permite especificar una referencia cultural para los servicios individuales.</span><span class="sxs-lookup"><span data-stu-id="520cb-333">The ASP.NET configuration language allows you to specify the culture for individual services.</span></span> <span data-ttu-id="520cb-334">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no es compatible con ese valor de configuración excepto en el modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="520cb-334">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not support that configuration setting except in ASP.NET compatibility mode.</span></span> <span data-ttu-id="520cb-335">Para adaptar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que no utiliza el modo de compatibilidad de ASP.NET, compile el tipo de servicio en los ensamblados específicos de la referencia cultural, y defina extremos específicos de la referencia cultural independientes para cada ensamblado específico de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="520cb-335">To localize a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that does not use ASP.NET compatibility mode, compile the service type into culture-specific assemblies, and have separate culture-specific endpoints for each culture-specific assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="520cb-336">Vea también</span><span class="sxs-lookup"><span data-stu-id="520cb-336">See Also</span></span>  
 [<span data-ttu-id="520cb-337">Comparación de los servicios Web de ASP.NET a WCF basado en el propósito y las normas utilizadas</span><span class="sxs-lookup"><span data-stu-id="520cb-337">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
