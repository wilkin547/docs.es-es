---
title: Comparación de los servicios web ASP.NET con el WCF basado en desarrollo
ms.date: 03/30/2017
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
ms.openlocfilehash: e5d249514ecad7507235bb8bd354c80bdc17c5dc
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679754"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a><span data-ttu-id="a4d56-102">Comparación de los servicios web ASP.NET con el WCF basado en desarrollo</span><span class="sxs-lookup"><span data-stu-id="a4d56-102">Comparing ASP.NET Web Services to WCF Based on Development</span></span>

<span data-ttu-id="a4d56-103">Windows Communication Foundation (WCF) tiene una opción de modo de compatibilidad ASP.NET para habilitar aplicaciones de WCF para programar y configurar como servicios Web ASP.NET e imitar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a4d56-103">Windows Communication Foundation (WCF) has an ASP.NET compatibility mode option to enable WCF applications to be programmed and configured like ASP.NET Web services, and mimic their behavior.</span></span> <span data-ttu-id="a4d56-104">Las secciones siguientes comparan los servicios Web ASP.NET y WCF se basa en lo que se necesita para desarrollar aplicaciones mediante ambas tecnologías.</span><span class="sxs-lookup"><span data-stu-id="a4d56-104">The following sections compare ASP.NET Web services and WCF based on what is required to develop applications using both technologies.</span></span>

## <a name="data-representation"></a><span data-ttu-id="a4d56-105">Representación de datos</span><span class="sxs-lookup"><span data-stu-id="a4d56-105">Data Representation</span></span>

<span data-ttu-id="a4d56-106">Normalmente, el desarrollo de un servicio web con ASP.NET comienza con la definición de todos los tipos de datos complejos que utilizará el servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-106">The development of a Web service with ASP.NET typically begins with defining any complex data types the service is to use.</span></span> <span data-ttu-id="a4d56-107">ASP.NET se basa en <xref:System.Xml.Serialization.XmlSerializer> para traducir los datos representados por los tipos de .NET Framework a XML para la transmisión hacia o desde un servicio, y para traducir los datos recibidos como XML en los objetos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a4d56-107">ASP.NET relies on the <xref:System.Xml.Serialization.XmlSerializer> to translate data represented by .NET Framework types to XML for transmission to or from a service and to translate data received as XML into .NET Framework objects.</span></span> <span data-ttu-id="a4d56-108">La definición de los tipos de datos complejos que utilizará un servicio de ASP.NET requiere la definición de las clases de .NET Framework que <xref:System.Xml.Serialization.XmlSerializer> puede serializar a y desde XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-108">Defining the complex data types that an ASP.NET service is to use requires the definition of .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML.</span></span> <span data-ttu-id="a4d56-109">Estas clases pueden escribirse manualmente o generarse a partir de las definiciones de los tipos de Esquema XML, mediante la línea de comandos de la utilidad de compatibilidad de tipos de datos de XML, xsd.exe.</span><span class="sxs-lookup"><span data-stu-id="a4d56-109">Such classes can be written manually, or generated from definitions of the types in XML Schema using the command-line XML Schemas/Data Types Support Utility, xsd.exe.</span></span>

<span data-ttu-id="a4d56-110">La siguiente lista muestra problemas clave que deben tenerse en cuenta al definir las clases de .NET Framework que <xref:System.Xml.Serialization.XmlSerializer> puede serializar a y desde XML:</span><span class="sxs-lookup"><span data-stu-id="a4d56-110">The following is a list of key issues to know when defining .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML:</span></span>

- <span data-ttu-id="a4d56-111">Solo los campos y propiedades públicas de los objetos de .NET Framework se traducen a XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-111">Only the public fields and properties of .NET Framework objects are translated into XML.</span></span>

- <span data-ttu-id="a4d56-112">Las instancias de las clases de colección solo pueden serializarse a XML si las clases implementan <xref:System.Collections.IEnumerable>, o la interfaz <xref:System.Collections.ICollection>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-112">Instances of collection classes can be serialized into XML only if the classes implement either the <xref:System.Collections.IEnumerable> or <xref:System.Collections.ICollection> interface.</span></span>

- <span data-ttu-id="a4d56-113">Las clases que implementan la interfaz <xref:System.Collections.IDictionary>, como <xref:System.Collections.Hashtable>, no pueden serializarse en XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-113">Classes that implement the <xref:System.Collections.IDictionary> interface, such as <xref:System.Collections.Hashtable>, cannot be serialized into XML.</span></span>

- <span data-ttu-id="a4d56-114">La gran cantidad de tipos de atributo existente en el espacio de nombres <xref:System.Xml.Serialization>, puede agregarse a una clase de .NET Framework y sus miembros para controlar la representación de las instancias de la clase en XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-114">The great many attribute types in the <xref:System.Xml.Serialization> namespace can be added to a .NET Framework class and its members to control how instances of the class are represented in XML.</span></span>

<span data-ttu-id="a4d56-115">Desarrollo de aplicaciones WCF normalmente también se comienza con la definición de tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="a4d56-115">WCF application development usually also begins with the definition of complex types.</span></span> <span data-ttu-id="a4d56-116">WCF se puede realizar para usar los mismos tipos de .NET Framework como servicios Web de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-116">WCF can be made to use the same .NET Framework types as ASP.NET Web services.</span></span>

<span data-ttu-id="a4d56-117">WCF<xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> pueden agregarse a tipos de .NET Framework para indicar que son instancias del tipo deben serializarse en XML, y qué campos o propiedades concretas del tipo son serializarse, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a4d56-117">The WCF<xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> can be added to .NET Framework types to indicate that instances of the type are to be serialized into XML, and which particular fields or properties of the type are to be serialized, as shown in the following sample code.</span></span>

```csharp
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

<span data-ttu-id="a4d56-118">
  <xref:System.Runtime.Serialization.DataContractAttribute> significa que cero o más campos o propiedades de un tipo deberán serializarse, mientras que <xref:System.Runtime.Serialization.DataMemberAttribute> indica que se serializará un campo o propiedad concreta.</span><span class="sxs-lookup"><span data-stu-id="a4d56-118">The <xref:System.Runtime.Serialization.DataContractAttribute> signifies that zero or more of a type’s fields or properties are to be serialized, while the <xref:System.Runtime.Serialization.DataMemberAttribute> indicates that a particular field or property is to be serialized.</span></span> <span data-ttu-id="a4d56-119">El atributo <xref:System.Runtime.Serialization.DataContractAttribute> se puede aplicar a una clase o a una estructura.</span><span class="sxs-lookup"><span data-stu-id="a4d56-119">The <xref:System.Runtime.Serialization.DataContractAttribute> can be applied to a class or structure.</span></span> <span data-ttu-id="a4d56-120">
  <xref:System.Runtime.Serialization.DataMemberAttribute> se puede aplicar a un campo o una propiedad, y los campos y propiedades a las que se aplica el atributo pueden ser públicos o privados.</span><span class="sxs-lookup"><span data-stu-id="a4d56-120">The <xref:System.Runtime.Serialization.DataMemberAttribute> can be applied to a field or a property, and the fields and properties to which the attribute is applied can be either public or private.</span></span> <span data-ttu-id="a4d56-121">Las instancias de tipos que tienen el <xref:System.Runtime.Serialization.DataContractAttribute> aplicado a ellos se conocen como contratos de datos en WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-121">Instances of types that have the <xref:System.Runtime.Serialization.DataContractAttribute> applied to them are referred to as data contracts in WCF.</span></span> <span data-ttu-id="a4d56-122">Se serializan en XML mediante <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-122">They are serialized into XML using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

<span data-ttu-id="a4d56-123">La siguiente lista enumera las principales diferencias entre la utilización de <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>, así como los distintos atributos del espacio de nombres <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-123">The following is a list of the important differences between using the <xref:System.Runtime.Serialization.DataContractSerializer> and using the <xref:System.Xml.Serialization.XmlSerializer> and the various attributes of the <xref:System.Xml.Serialization> namespace.</span></span>

- <span data-ttu-id="a4d56-124"><xref:System.Xml.Serialization.XmlSerializer> y los atributos del espacio de nombres <xref:System.Xml.Serialization> están diseñados para permitir asignar los tipos de .NET Framework a cualquier tipo válido definido en Esquema XML, de modo que ofrecen un control muy preciso de la representación de un tipo en XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-124">The <xref:System.Xml.Serialization.XmlSerializer> and the attributes of the <xref:System.Xml.Serialization> namespace are designed to allow you to map .NET Framework types to any valid type defined in XML Schema, and so they provide for very precise control over how a type is represented in XML.</span></span> <span data-ttu-id="a4d56-125"><xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> proporcionan un control muy preciso sobre la representación de un tipo en XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-125">The <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> provide very little control over how a type is represented in XML.</span></span> <span data-ttu-id="a4d56-126">Solo pueden especificarse los espacios de nombres y los nombres utilizados para representar el tipo y sus campos, o propiedades en XML, así como la secuencia de aparición en XML de los campos y propiedades:</span><span class="sxs-lookup"><span data-stu-id="a4d56-126">You can only specify the namespaces and names used to represent the type and its fields or properties in the XML, and the sequence in which the fields and properties appear in the XML:</span></span>

    ```csharp
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

    <span data-ttu-id="a4d56-127">El resto de información sobre la estructura de XML utilizada para representar el tipo .NET está determinada por <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-127">Everything else about the structure of the XML used to represent the .NET type is determined by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

- <span data-ttu-id="a4d56-128">Al no permitir un mayor control sobre la representación de un tipo en XML, el proceso de serialización se vuelve extremadamente predecible para <xref:System.Runtime.Serialization.DataContractSerializer>y, por lo tanto, más fácil de optimizar.</span><span class="sxs-lookup"><span data-stu-id="a4d56-128">By not permitting much control over how a type is to be represented in XML, the serialization process becomes highly predictable for the <xref:System.Runtime.Serialization.DataContractSerializer>, and, thereby, easier to optimize.</span></span> <span data-ttu-id="a4d56-129">Una ventaja práctica del diseño de <xref:System.Runtime.Serialization.DataContractSerializer> es un mejor rendimiento, aproximadamente un diez por ciento mejor.</span><span class="sxs-lookup"><span data-stu-id="a4d56-129">A practical benefit of the design of the <xref:System.Runtime.Serialization.DataContractSerializer> is better performance, approximately ten percent better performance.</span></span>

- <span data-ttu-id="a4d56-130">Los atributos utilizados con <xref:System.Xml.Serialization.XmlSerializer> no indican qué campos o propiedades del tipo se serializan en XML, mientras que <xref:System.Runtime.Serialization.DataMemberAttribute> utilizado con <xref:System.Runtime.Serialization.DataContractSerializer> muestra explícitamente qué campos o propiedades se serializan.</span><span class="sxs-lookup"><span data-stu-id="a4d56-130">The attributes for use with the <xref:System.Xml.Serialization.XmlSerializer> do not indicate which fields or properties of the type are serialized into XML, whereas the <xref:System.Runtime.Serialization.DataMemberAttribute> for use with the <xref:System.Runtime.Serialization.DataContractSerializer> shows explicitly which fields or properties are serialized.</span></span> <span data-ttu-id="a4d56-131">Por consiguiente, los contratos de datos son contratos explícitos de la estructura de datos que una aplicación enviará y recibirá.</span><span class="sxs-lookup"><span data-stu-id="a4d56-131">Therefore, data contracts are explicit contracts about the structure of the data that an application is to send and receive.</span></span>

- <span data-ttu-id="a4d56-132"><xref:System.Xml.Serialization.XmlSerializer> solo puede traducir a XML los miembros públicos de un objeto .NET, <xref:System.Runtime.Serialization.DataContractSerializer> puede traducir a XML los miembros de objetos independientemente de los modificadores de acceso de esos miembros.</span><span class="sxs-lookup"><span data-stu-id="a4d56-132">The <xref:System.Xml.Serialization.XmlSerializer> can only translate the public members of a .NET object into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> can translate the members of objects into XML regardless of the access modifiers of those members.</span></span>

- <span data-ttu-id="a4d56-133">Como consecuencia de poder serializar en XML los miembros no públicos de tipos, <xref:System.Runtime.Serialization.DataContractSerializer> posee menos restricciones en la variedad de tipos .NET que puede serializar en XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-133">As a consequence of being able to serialize the non-public members of types into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> has fewer restrictions on the variety of .NET types that it can serialize into XML.</span></span> <span data-ttu-id="a4d56-134">En concreto, puede traducir a XML tipos como <xref:System.Collections.Hashtable> que implementa la interfaz <xref:System.Collections.IDictionary>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-134">In particular, it can translate into XML types like <xref:System.Collections.Hashtable> that implement the <xref:System.Collections.IDictionary> interface.</span></span> <span data-ttu-id="a4d56-135">Es mucho más probable que <xref:System.Runtime.Serialization.DataContractSerializer> pueda serializar en XML las instancias de cualquiera tipo .NET existentes previamente, sin tener que modificar la definición del tipo o desarrollar un contenedor para él.</span><span class="sxs-lookup"><span data-stu-id="a4d56-135">The <xref:System.Runtime.Serialization.DataContractSerializer> is much more likely to be able to serialize the instances of any pre-existing .NET type into XML without having to either modify the definition of the type or develop a wrapper for it.</span></span>

- <span data-ttu-id="a4d56-136">Otra consecuencia de que <xref:System.Runtime.Serialization.DataContractSerializer> pueda tener acceso a los miembros no públicos de un tipo es que requiere plena confianza, al contrario que <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-136">Another consequence of the <xref:System.Runtime.Serialization.DataContractSerializer> being able to access the non-public members of a type is that it requires full trust, whereas the <xref:System.Xml.Serialization.XmlSerializer> does not.</span></span> <span data-ttu-id="a4d56-137">Permiso de acceso del código de plena confianza otorga acceso completo a todos los recursos en un equipo que se puede acceder mediante las credenciales bajo las que se está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="a4d56-137">The Full Trust code access permission gives complete access to all resources on a machine that can be accessed using the credentials under which the code is executing.</span></span> <span data-ttu-id="a4d56-138">Esta opción debe usarse con cuidado como código de plena confianza tiene acceso a todos los recursos en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a4d56-138">This option should be used with care as fully trusted code accesses all resources on your machine.</span></span>

- <span data-ttu-id="a4d56-139">
  <xref:System.Runtime.Serialization.DataContractSerializer> incorpora cierta compatibilidad para el control de versiones:</span><span class="sxs-lookup"><span data-stu-id="a4d56-139">The <xref:System.Runtime.Serialization.DataContractSerializer> incorporates some support for versioning:</span></span>

    - <span data-ttu-id="a4d56-140"><xref:System.Runtime.Serialization.DataMemberAttribute> posee una propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> a la puede asignarse un valor de falso para los miembros que se agregan a las nuevas versiones de un contrato de datos que no se encontraban en versiones anteriores, con lo que las aplicaciones con la versión más reciente del contrato pueden procesar las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a4d56-140">The <xref:System.Runtime.Serialization.DataMemberAttribute> has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property that can be assigned a value of false for members that are added to new versions of a data contract that were not present in earlier versions, thereby allowing applications with the newer version of the contract to be able to process earlier versions.</span></span>

    - <span data-ttu-id="a4d56-141">Cuando un contrato de datos implementa la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>, es posible permitir a <xref:System.Runtime.Serialization.DataContractSerializer> pasar miembros definidos en versiones más recientes de un contrato de datos a través de aplicaciones con versiones anteriores del contrato.</span><span class="sxs-lookup"><span data-stu-id="a4d56-141">By having a data contract implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface, one can allow the <xref:System.Runtime.Serialization.DataContractSerializer> to pass members defined in newer versions of a data contract through applications with earlier versions of the contract.</span></span>

<span data-ttu-id="a4d56-142">A pesar de todas las diferencias, el XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, siempre y cuando defina explícitamente el espacio de nombres de XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-142">Despite all of the differences, the XML into which the <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="a4d56-143">La clase siguiente, que tiene los atributos que pueden utilizarse con ambos serializadores, se traduce en XML semánticamente idéntico utilizando el <xref:System.Xml.Serialization.XmlSerializer> y por el <xref:System.Runtime.Serialization.DataContractAttribute>:</span><span class="sxs-lookup"><span data-stu-id="a4d56-143">The following class, which has attributes for use with both of the serializers, is translated into semantically identical XML by the <xref:System.Xml.Serialization.XmlSerializer> and by the <xref:System.Runtime.Serialization.DataContractAttribute>:</span></span>

```csharp
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

<span data-ttu-id="a4d56-144">El kit de desarrollo de software (SDK) de Windows incluye una herramienta de línea de comandos denominada el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="a4d56-144">The Windows software development kit (SDK) includes a command-line tool called the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="a4d56-145">Al igual que la herramienta xsd.exe utilizada con servicios Web de ASP.NET, Svcutil.exe puede generar definiciones de tipos de datos de .NET del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="a4d56-145">Like the xsd.exe tool used with ASP.NET Web services, Svcutil.exe can generate definitions of .NET data types from XML Schema.</span></span> <span data-ttu-id="a4d56-146">Los tipos son contratos de datos si <xref:System.Runtime.Serialization.DataContractSerializer> puede emitir XML con el formato definido por esquema XML; de lo contrario, están diseñados para serializarse mediante <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-146">The types are data contracts if the <xref:System.Runtime.Serialization.DataContractSerializer> can emit XML in the format defined by the XML Schema; otherwise, they are intended for serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="a4d56-147">Svcutil.exe puede generar también un esquema XML de los contratos de datos mediante su `dataContractOnly` cambiar.</span><span class="sxs-lookup"><span data-stu-id="a4d56-147">Svcutil.exe can also generate an XML schema from data contracts by using its `dataContractOnly` switch.</span></span>

> [!NOTE]
> <span data-ttu-id="a4d56-148">Aunque el uso de servicios Web ASP.NET el <xref:System.Xml.Serialization.XmlSerializer>y el modo de compatibilidad ASP.NET de WCF hace que los servicios WCF imitan el comportamiento de los servicios Web ASP.NET, la opción de compatibilidad ASP.NET no limita al uso de la <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-148">Although ASP.NET Web services use the <xref:System.Xml.Serialization.XmlSerializer>, and WCF ASP.NET compatibility mode makes WCF services mimic the behavior of ASP.NET Web services, the ASP.NET compatibility option does not restrict one to using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="a4d56-149">Puede seguir utilizándose <xref:System.Runtime.Serialization.DataContractSerializer> con servicios que se ejecutan en el modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-149">One can still use the <xref:System.Runtime.Serialization.DataContractSerializer> with services running in the ASP.NET compatibility mode.</span></span>

## <a name="service-development"></a><span data-ttu-id="a4d56-150">Desarrollo del servicio</span><span class="sxs-lookup"><span data-stu-id="a4d56-150">Service Development</span></span>

<span data-ttu-id="a4d56-151">Para desarrollar un servicio mediante ASP.NET, lo habitual era agregar el atributo <xref:System.Web.Services.WebService> a una clase, y <xref:System.Web.Services.WebMethodAttribute> a cualquiera de los métodos de esa clase que serán operaciones del servicio:</span><span class="sxs-lookup"><span data-stu-id="a4d56-151">To develop a service using ASP.NET, it has been customary to add the <xref:System.Web.Services.WebService> attribute to a class, and the <xref:System.Web.Services.WebMethodAttribute> to any of that class’ methods that are to be operations of the service:</span></span>

```csharp
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

<span data-ttu-id="a4d56-152">ASP.NET 2.0 introdujo la opción de agregar el atributo <xref:System.Web.Services.WebService> y <xref:System.Web.Services.WebMethodAttribute> a una interfaz en lugar de a una clase, y de escribir una clase para implementar la interfaz:</span><span class="sxs-lookup"><span data-stu-id="a4d56-152">ASP.NET 2.0 introduced the option of adding the attribute <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> to an interface rather than to a class, and writing a class to implement the interface:</span></span>

```csharp
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

<span data-ttu-id="a4d56-153">La utilización de esta opción es preferible porque la interfaz con el atributo <xref:System.Web.Services.WebService> constituye un contrato para las operaciones realizadas por el servicio, que puede reutilizarse con diferentes clases que podrían implementar ese mismo contrato de distintas maneras.</span><span class="sxs-lookup"><span data-stu-id="a4d56-153">Using this option is to be preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>

<span data-ttu-id="a4d56-154">Se proporciona un servicio WCF mediante la definición de uno o varios extremos WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-154">A WCF service is provided by defining one or more WCF endpoints.</span></span> <span data-ttu-id="a4d56-155">Un punto de conexión se define mediante una dirección, un enlace y un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-155">An endpoint is defined by an address, a binding and a service contract.</span></span> <span data-ttu-id="a4d56-156">La dirección define la ubicación del servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-156">The address defines where the service is located.</span></span> <span data-ttu-id="a4d56-157">El enlace especifica cómo comunicar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-157">The binding specifies how to communicate with the service.</span></span> <span data-ttu-id="a4d56-158">El contrato de servicio define las operaciones que puede realizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-158">The service contract defines the operations that the service can perform.</span></span>

<span data-ttu-id="a4d56-159">Normalmente, primero se define el contrato de servicios agregando <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> a una interfaz:</span><span class="sxs-lookup"><span data-stu-id="a4d56-159">The service contract is usually defined first, by adding <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> to an interface:</span></span>

```csharp
[ServiceContract]
public interface IEcho
{
     [OperationContract]
     string Echo(string input);
}
```

<span data-ttu-id="a4d56-160">El <xref:System.ServiceModel.ServiceContractAttribute> especifica que la interfaz define un contrato de servicio WCF y el <xref:System.ServiceModel.OperationContractAttribute> indica que, si los hay, de los métodos de la interfaz definen las operaciones del contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-160">The <xref:System.ServiceModel.ServiceContractAttribute> specifies that the interface defines a WCF service contract, and the <xref:System.ServiceModel.OperationContractAttribute> indicates which, if any, of the methods of the interface define operations of the service contract.</span></span>

<span data-ttu-id="a4d56-161">Una vez definido un contrato de servicios, se implementa en una clase, para ello la clase implementa la interfaz que define el contrato de servicios:</span><span class="sxs-lookup"><span data-stu-id="a4d56-161">Once a service contract has been defined, it is implemented in a class, by having the class implement the interface by which the service contract is defined:</span></span>

```csharp
public class Service : IEcho
{
    public string Echo(string input)
    {
       return input;
    }
}
```

<span data-ttu-id="a4d56-162">Una clase que implementa un contrato de servicio se conoce como un servicio de tipo en WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-162">A class that implements a service contract is referred to as a service type in WCF.</span></span>

<span data-ttu-id="a4d56-163">El paso siguiente es asociar una dirección y un enlace a un tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-163">The next step is to associate an address and a binding with a service type.</span></span> <span data-ttu-id="a4d56-164">Que normalmente se realiza en un archivo de configuración, ya sea editando el archivo directamente o mediante un editor de configuración proporcionado con WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-164">That is typically done in a configuration file, either by editing the file directly, or by using a configuration editor provided with WCF.</span></span> <span data-ttu-id="a4d56-165">El siguiente es un ejemplo de archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a4d56-165">Here is an example of a configuration file.</span></span>

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

<span data-ttu-id="a4d56-166">El enlace especifica el conjunto de protocolos de comunicación con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-166">The binding specifies the set of protocols for communicating with the application.</span></span> <span data-ttu-id="a4d56-167">La tabla siguiente enumera los enlaces proporcionados por el sistema que representan las opciones habituales.</span><span class="sxs-lookup"><span data-stu-id="a4d56-167">The following table lists the system-provided bindings that represent common options.</span></span>

|<span data-ttu-id="a4d56-168">Name</span><span class="sxs-lookup"><span data-stu-id="a4d56-168">Name</span></span>|<span data-ttu-id="a4d56-169">Finalidad</span><span class="sxs-lookup"><span data-stu-id="a4d56-169">Purpose</span></span>|
|----------|-------------|
|<span data-ttu-id="a4d56-170">BasicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-170">BasicHttpBinding</span></span>|<span data-ttu-id="a4d56-171">Interoperabilidad con los servicio y clientes web que admiten WS-BasicProfile 1.1 y Basic Security Profile 1.0.</span><span class="sxs-lookup"><span data-stu-id="a4d56-171">Interoperability with Web services and clients supporting the WS-BasicProfile 1.1 and Basic Security Profile 1.0.</span></span>|
|<span data-ttu-id="a4d56-172">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-172">WSHttpBinding</span></span>|<span data-ttu-id="a4d56-173">Interoperabilidad con los servicio y clientes web que admiten los protocolos WS-\* sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="a4d56-173">Interoperability with Web services and clients that support the WS-\* protocols over HTTP.</span></span>|
|<span data-ttu-id="a4d56-174">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-174">WSDualHttpBinding</span></span>|<span data-ttu-id="a4d56-175">Comunicación HTTP dúplex, por la que el receptor de un mensaje inicial no responde directamente al remitente inicial, pero puede transmitir, durante un período de tiempo, cualquier número de respuestas utilizando HTTP de conformidad con los protocolos WS-\*.</span><span class="sxs-lookup"><span data-stu-id="a4d56-175">Duplex HTTP communication, by which the receiver of an initial message does not reply directly to the initial sender, but may transmit any number of responses over a period of time by using HTTP in conformity with WS-\* protocols.</span></span>|
|<span data-ttu-id="a4d56-176">WSFederationBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-176">WSFederationBinding</span></span>|<span data-ttu-id="a4d56-177">Comunicación HTTP, en la que el acceso a los recursos de un servicio puede controlarse en base a las credenciales emitidas por un proveedor de credenciales identificado explícitamente.</span><span class="sxs-lookup"><span data-stu-id="a4d56-177">HTTP communication, in which access to the resources of a service can be controlled based on credentials issued by an explicitly-identified credential provider.</span></span>|
|<span data-ttu-id="a4d56-178">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-178">NetTcpBinding</span></span>|<span data-ttu-id="a4d56-179">Comunicación segura, confiable y de alto rendimiento entre las entidades de software WCF a través de una red.</span><span class="sxs-lookup"><span data-stu-id="a4d56-179">Secure, reliable, high-performance communication between WCF software entities across a network.</span></span>|
|<span data-ttu-id="a4d56-180">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-180">NetNamedPipeBinding</span></span>|<span data-ttu-id="a4d56-181">Comunicación segura, confiable y de alto rendimiento entre las entidades de software WCF en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="a4d56-181">Secure, reliable, high-performance communication between WCF software entities on the same machine.</span></span>|
|<span data-ttu-id="a4d56-182">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-182">NetMsmqBinding</span></span>|<span data-ttu-id="a4d56-183">Comunicación entre las entidades de software WCF mediante MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a4d56-183">Communication between WCF software entities by using MSMQ.</span></span>|
|<span data-ttu-id="a4d56-184">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-184">MsmqIntegrationBinding</span></span>|<span data-ttu-id="a4d56-185">Comunicación entre una entidad de software WCF y otra entidad de software mediante MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a4d56-185">Communication between a WCF software entity and another software entity by using MSMQ.</span></span>|
|<span data-ttu-id="a4d56-186">NetPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="a4d56-186">NetPeerTcpBinding</span></span>|<span data-ttu-id="a4d56-187">Comunicación entre las entidades de software WCF mediante el uso de Windows Peer-to-Peer Networking.</span><span class="sxs-lookup"><span data-stu-id="a4d56-187">Communication between WCF software entities by using Windows Peer-to-Peer Networking.</span></span>|

<span data-ttu-id="a4d56-188">El enlace proporcionado por el sistema, <xref:System.ServiceModel.BasicHttpBinding>, incorpora el conjunto de protocolos admitido por los servicios web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-188">The system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>, incorporates the set of protocols supported by ASP.NET Web services.</span></span>

<span data-ttu-id="a4d56-189">Los enlaces personalizados para aplicaciones WCF se definen fácilmente como colecciones de las clases de elementos de enlace que WCF usa para implementar los protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="a4d56-189">Custom bindings for WCF applications are easily defined as collections of the binding element classes that WCF uses to implement individual protocols.</span></span> <span data-ttu-id="a4d56-190">Los nuevos elementos de enlace pueden escribirse para representar los protocolos adicionales.</span><span class="sxs-lookup"><span data-stu-id="a4d56-190">New binding elements can be written to represent additional protocols.</span></span>

<span data-ttu-id="a4d56-191">El comportamiento interno de los tipos de servicio puede ajustarse mediante las propiedades de una familia de clases denominadas comportamientos.</span><span class="sxs-lookup"><span data-stu-id="a4d56-191">The internal behavior of service types can be adjusted using the properties of a family of classes called behaviors.</span></span> <span data-ttu-id="a4d56-192">Aquí, la clase <xref:System.ServiceModel.ServiceBehaviorAttribute> se utiliza para especificar que el tipo de servicio es multiproceso.</span><span class="sxs-lookup"><span data-stu-id="a4d56-192">Here, the <xref:System.ServiceModel.ServiceBehaviorAttribute> class is used to specify that the service type is to be multithreaded.</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple]
public class DerivativesCalculatorServiceType: IDerivativesCalculator
```

<span data-ttu-id="a4d56-193">Algunos comportamientos, como <xref:System.ServiceModel.ServiceBehaviorAttribute>, son atributos.</span><span class="sxs-lookup"><span data-stu-id="a4d56-193">Some behaviors, like <xref:System.ServiceModel.ServiceBehaviorAttribute>, are attributes.</span></span> <span data-ttu-id="a4d56-194">Otros, aquellos con las propiedades que desean establecer los administradores, pueden modificarse en la configuración de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-194">Others, the ones with properties that administrators would want to set, can be modified in the configuration of an application.</span></span>

<span data-ttu-id="a4d56-195">A la hora de programar los tipos de servicio, se utiliza con frecuencia la clase <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-195">In programming service types, frequent use is made of the <xref:System.ServiceModel.OperationContext> class.</span></span> <span data-ttu-id="a4d56-196">Su propiedad <xref:System.ServiceModel.OperationContext.Current%2A> estática proporciona acceso a información sobre el contexto en el que una operación se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="a4d56-196">Its static <xref:System.ServiceModel.OperationContext.Current%2A> property provides access to information about the context in which an operation is running.</span></span> <span data-ttu-id="a4d56-197"><xref:System.ServiceModel.OperationContext> es similar a las clases <xref:System.Web.HttpContext> y <xref:System.EnterpriseServices.ContextUtil>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-197"><xref:System.ServiceModel.OperationContext> is similar to both the <xref:System.Web.HttpContext> and <xref:System.EnterpriseServices.ContextUtil> classes.</span></span>

## <a name="hosting"></a><span data-ttu-id="a4d56-198">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="a4d56-198">Hosting</span></span>

<span data-ttu-id="a4d56-199">Los servicios web ASP.NET están compilados en un ensamblado de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="a4d56-199">ASP.NET Web services are compiled into a class library assembly.</span></span> <span data-ttu-id="a4d56-200">Se proporciona un archivo, denominado archivo de servicio, que posee la extensión .asmx y contiene una directiva `@ WebService`, que identifica la clase que contiene el código del servicio y el ensamblado en el que se encuentra.</span><span class="sxs-lookup"><span data-stu-id="a4d56-200">A file called the service file is provided that has the extension .asmx and contains an `@ WebService` directive that identifies the class that contains the code for the service and the assembly in which it is located.</span></span>

```
<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>
```

<span data-ttu-id="a4d56-201">El archivo de servicio se copia en una raíz de la aplicación ASP.NET de Internet Information Services (IIS), y el ensamblado se copia en el subdirectorio \bin de esa raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-201">The service file is copied into an ASP.NET application root in Internet Information Services (IIS), and the assembly is copied into the \bin subdirectory of that application root.</span></span> <span data-ttu-id="a4d56-202">Después, puede accederse a la aplicación mediante el identificador uniforme de recursos (URL) del archivo de servicio de la raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-202">The application is then accessible by using the uniform resource locator (URL) of the service file in the application root.</span></span>

<span data-ttu-id="a4d56-203">Se pueden hospedar fácilmente los servicios WCF en IIS 5.1 ó 6.0, el servicio de activación de proceso Windows (WAS) que se proporciona como parte de IIS 7.0, y en cualquier aplicación. NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-203">WCF services can readily be hosted within IIS 5.1 or 6.0, the Windows Process Activation Service (WAS) that is provided as part of IIS 7.0, and within any .NET application.</span></span> <span data-ttu-id="a4d56-204">Para hospedar un servicio en IIS 5.1 ó 6.0, el servicio debe utilizar HTTP como protocolo de transporte de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="a4d56-204">To host a service in IIS 5.1 or 6.0, the service must use HTTP as the communications transport protocol.</span></span>

<span data-ttu-id="a4d56-205">Para hospedar un servicio en IIS 5.1, 6.0, o en WAS, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4d56-205">To host a service within IIS 5.1, 6.0 or within WAS, use the follows steps:</span></span>

1. <span data-ttu-id="a4d56-206">Compile el tipo de servicio en un ensamblado de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="a4d56-206">Compile the service type into a class library assembly.</span></span>

2. <span data-ttu-id="a4d56-207">Cree un archivo de servicio con una extensión .svc y una directiva `@ ServiceHost` que identifique el tipo de servicio:</span><span class="sxs-lookup"><span data-stu-id="a4d56-207">Create a service file with a .svc extension with an `@ ServiceHost` directive to identify the service type:</span></span>

    ```
    <%@ServiceHost language="c#" Service="MyService" %>
    ```

3. <span data-ttu-id="a4d56-208">Copie el archivo de servicio en un directorio virtual, y el ensamblado en el subdirectorio \bin de dicho directorio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-208">Copy the service file into a virtual directory, and the assembly into the \bin subdirectory of that virtual directory.</span></span>

4. <span data-ttu-id="a4d56-209">Copie el archivo de configuración en el directorio virtual y denomínelo Web.config.</span><span class="sxs-lookup"><span data-stu-id="a4d56-209">Copy the configuration file into the virtual directory, and name it Web.config.</span></span>

 <span data-ttu-id="a4d56-210">A continuación, puede accederse a la aplicación mediante la dirección URL del archivo de servicio de la raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-210">The application is then accessible by using the URL of the service file in the application root.</span></span>

 <span data-ttu-id="a4d56-211">Para hospedar un servicio WCF en una aplicación. NET, compile el tipo de servicio en un ensamblado de biblioteca de clases hace referencia la aplicación y programar la aplicación para hospedar el servicio mediante el <xref:System.ServiceModel.ServiceHost> clase.</span><span class="sxs-lookup"><span data-stu-id="a4d56-211">To host a WCF service within a .NET application, compile the service type into a class library assembly referenced by the application, and program the application to host the service using the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="a4d56-212">El siguiente ejemplo muestra la programación básica requerida:</span><span class="sxs-lookup"><span data-stu-id="a4d56-212">The following is an example of the basic programming required:</span></span>

```csharp
string httpBaseAddress = "http://www.contoso.com:8000/";
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";

Uri httpBaseAddressUri = new Uri(httpBaseAddress);
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);

Uri[] baseAddresses = new Uri[] {
 httpBaseAddressUri,
 tcpBaseAddressUri};

using(ServiceHost host = new ServiceHost(
typeof(Service), //"Service" is the name of the service type baseAddresses))
{
     host.Open();

     […] //Wait to receive messages
     host.Close();
}
```

<span data-ttu-id="a4d56-213">Este ejemplo muestra cómo se especifican las direcciones de uno o más protocolos de transporte en la construcción de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-213">This example shows how addresses for one or more transport protocols are specified in the construction of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="a4d56-214">Estas direcciones se conocen como direcciones base.</span><span class="sxs-lookup"><span data-stu-id="a4d56-214">These addresses are referred to as base addresses.</span></span>

<span data-ttu-id="a4d56-215">La dirección proporcionada para cualquier punto de conexión de un servicio WCF es una dirección relativa a una dirección base del host del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a4d56-215">The address provided for any endpoint of a WCF service is an address relative to a base address of the endpoint’s host.</span></span> <span data-ttu-id="a4d56-216">El host puede contar con una dirección base para cada protocolo de transporte de comunicación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-216">The host can have one base address for each communication transport protocol.</span></span> <span data-ttu-id="a4d56-217">En la configuración de ejemplo del archivo de configuración anterior, el <xref:System.ServiceModel.BasicHttpBinding> seleccionado para el extremo utiliza HTTP como protocolo de transporte, por lo que la dirección del extremo, `EchoService`, es relativa a la dirección base HTTP del host.</span><span class="sxs-lookup"><span data-stu-id="a4d56-217">In the sample configuration in the preceding configuration file, the <xref:System.ServiceModel.BasicHttpBinding> selected for the endpoint uses HTTP as the transport protocol, so the address of the endpoint, `EchoService`, is relative to the host’s HTTP base address.</span></span> <span data-ttu-id="a4d56-218">En el caso de host en el ejemplo anterior, es la dirección base HTTP `http://www.contoso.com:8000/`.</span><span class="sxs-lookup"><span data-stu-id="a4d56-218">In the case of the host in the preceding example, the HTTP base address is `http://www.contoso.com:8000/`.</span></span> <span data-ttu-id="a4d56-219">Para un servicio hospedado en IIS o WAS, la dirección base es la dirección URL del archivo de servicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-219">For a service hosted within IIS or WAS, the base address is the URL of the service’s service file.</span></span>

<span data-ttu-id="a4d56-220">Solo los servicios hospedados en IIS o WAS, y que se configuran con HTTP como protocolo de transporte exclusivamente, se pueden realizar para usar la opción de modo de compatibilidad ASP.NET de WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-220">Only services hosted in IIS or WAS, and which are configured with HTTP as the transport protocol exclusively, can be made to use WCF ASP.NET compatibility mode option.</span></span> <span data-ttu-id="a4d56-221">Los pasos siguientes son necesarios para activar esa opción.</span><span class="sxs-lookup"><span data-stu-id="a4d56-221">Turning that option on requires the following steps.</span></span>

1. <span data-ttu-id="a4d56-222">El programador debe agregar el atributo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> al tipo de servicio y especificar que el modo de compatibilidad de ASP.NET está permitido o es necesario.</span><span class="sxs-lookup"><span data-stu-id="a4d56-222">The programmer must add the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> attribute to the service type and specify that ASP.NET compatibility mode is either allowed or required.</span></span>

    ```csharp
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(
          RequirementsMode=AspNetCompatibilityRequirementsMode.Require)]
    public class DerivativesCalculatorServiceType: IDerivativesCalculator
    ```

2. <span data-ttu-id="a4d56-223">El administrador debe configurar la aplicación para utilizar el modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-223">The administrator must configure the application to use the ASP.NET compatibility mode.</span></span>

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

    <span data-ttu-id="a4d56-224">Aplicaciones WCF también pueden configurarse para utilizar .asmx como extensión para sus archivos de servicio en lugar de .svc.</span><span class="sxs-lookup"><span data-stu-id="a4d56-224">WCF applications can also be configured to use .asmx as the extension for their service files rather than .svc.</span></span>

    ```xml
    <system.web>
         <compilation>
          <compilation debug="true">
          <buildProviders>
           <remove extension=".asmx"/>
           <add extension=".asmx"
            type="System.ServiceModel.ServiceBuildProvider,
            System.ServiceModel,
            Version=3.0.0.0,
            Culture=neutral,
            PublicKeyToken=b77a5c561934e089" />
          </buildProviders>
          </compilation>
         </compilation>
    </system.web>
    ```

    <span data-ttu-id="a4d56-225">Esta opción puede ahorrarle de tener que modificar a los clientes que están configurados para usar las direcciones URL de los archivos .asmx de servicio cuando se modifica un servicio para usar WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-225">That option can save you from having to modify clients that are configured to use the URLs of .asmx service files when modifying a service to use WCF.</span></span>

## <a name="client-development"></a><span data-ttu-id="a4d56-226">Desarrollo del cliente</span><span class="sxs-lookup"><span data-stu-id="a4d56-226">Client Development</span></span>

<span data-ttu-id="a4d56-227">Los clientes de los servicios web ASP.NET se generan mediante la herramienta de línea de comandos, WSDL.exe, que proporciona la dirección URL del archivo .asmx como entrada.</span><span class="sxs-lookup"><span data-stu-id="a4d56-227">Clients for ASP.NET Web services are generated using the command-line tool, WSDL.exe, which provides the URL of the .asmx file as input.</span></span> <span data-ttu-id="a4d56-228">Es la herramienta correspondiente proporcionada por WCF [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="a4d56-228">The corresponding tool provided by WCF is [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="a4d56-229">Genera un módulo de código con la definición del contrato de servicio y la definición de una clase de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-229">It generates a code module with the definition of the service contract and the definition of a WCF client class.</span></span> <span data-ttu-id="a4d56-230">También genera un archivo de configuración con la dirección y el enlace del servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-230">It also generates a configuration file with the address and binding of the service.</span></span>

<span data-ttu-id="a4d56-231">Generalmente, cuando se programa un cliente de un servicio remoto resulta aconsejable realizar la programación de acuerdo con un patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a4d56-231">In programming a client of a remote service it is generally advisable to program according to an asynchronous pattern.</span></span> <span data-ttu-id="a4d56-232">El código generado por la herramienta WSDL.exe siempre proporciona, de manera predeterminada, un patrón sincrónico y otro asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a4d56-232">The code generated by the WSDL.exe tool always provides for both a synchronous and an asynchronous pattern by default.</span></span> <span data-ttu-id="a4d56-233">El código generado por el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) puede proporcionar cualquier modelo.</span><span class="sxs-lookup"><span data-stu-id="a4d56-233">The code generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can provide for either pattern.</span></span> <span data-ttu-id="a4d56-234">Proporciona el patrón sincrónico de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a4d56-234">It provides for the synchronous pattern by default.</span></span> <span data-ttu-id="a4d56-235">Si se ejecuta la herramienta con el modificador `/async`, el código generado proporciona el patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a4d56-235">If the tool is executed with the `/async` switch, then the generated code provides for the asynchronous pattern.</span></span>

<span data-ttu-id="a4d56-236">No hay ninguna garantía de que los nombres en las clases de cliente WCF generadas por ASP. Herramienta WSDL.exe de la red, de forma predeterminada, coinciden con los nombres de las clases de cliente WCF generados por la herramienta Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="a4d56-236">There is no guarantee that names in the WCF client classes generated by ASP.NET’s WSDL.exe tool, by default, match the names in WCF client classes generated by the Svcutil.exe tool.</span></span> <span data-ttu-id="a4d56-237">En concreto, a los nombres de las propiedades de clases que deben serializarse mediante <xref:System.Xml.Serialization.XmlSerializer>, se les asigna, de forma predeterminada, el sufijo Property en el código generado por la herramienta Svcutil.exe, lo que no ocurre en el caso de la herramienta WSDL.exe.</span><span class="sxs-lookup"><span data-stu-id="a4d56-237">In particular, the names of the properties of classes that have to be serialized using the <xref:System.Xml.Serialization.XmlSerializer> are, by default, given the suffix Property in the code generated by the Svcutil.exe tool, which is not the case with the WSDL.exe tool.</span></span>

## <a name="message-representation"></a><span data-ttu-id="a4d56-238">Representación de mensajes</span><span class="sxs-lookup"><span data-stu-id="a4d56-238">Message Representation</span></span>

<span data-ttu-id="a4d56-239">Los encabezados de los mensajes SOAP enviados y recibidos por los servicios web ASP.NET puede personalizarse.</span><span class="sxs-lookup"><span data-stu-id="a4d56-239">The headers of the SOAP messages sent and received by ASP.NET Web services can be customized.</span></span> <span data-ttu-id="a4d56-240">Una clase se deriva de <xref:System.Web.Services.Protocols.SoapHeader> para definir la estructura del encabezado y, a continuación, <xref:System.Web.Services.Protocols.SoapHeaderAttribute> se utiliza para indicar la presencia del mismo.</span><span class="sxs-lookup"><span data-stu-id="a4d56-240">A class is derived from <xref:System.Web.Services.Protocols.SoapHeader> to define the structure of the header, and then the <xref:System.Web.Services.Protocols.SoapHeaderAttribute> is used to indicate the presence of the header.</span></span>

```csharp
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

<span data-ttu-id="a4d56-241">WCF proporciona los atributos, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, y <xref:System.ServiceModel.MessageBodyMemberAttribute> para describir la estructura de los mensajes SOAP enviados y recibidos por un servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-241">The WCF provides the attributes, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, and <xref:System.ServiceModel.MessageBodyMemberAttribute> to describe the structure of the SOAP messages sent and received by a service.</span></span>

```csharp
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
public class ItemMessage
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

<span data-ttu-id="a4d56-242">Esta sintaxis produce una representación explícita de la estructura de los mensajes, mientras que en el código de un servicio web ASP.NET la estructura de mensajes está implícita.</span><span class="sxs-lookup"><span data-stu-id="a4d56-242">This syntax yields an explicit representation of the structure of the messages, whereas the structure of messages is implied by the code of an ASP.NET Web service.</span></span> <span data-ttu-id="a4d56-243">Además, en la sintaxis ASP.NET, los encabezados del mensaje se representan como propiedades del servicio, como el `ProtocolHeader` propiedad en el ejemplo anterior, mientras que en la sintaxis WCF, representan con más precisión como propiedades de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a4d56-243">Also, in the ASP.NET syntax, message headers are represented as properties of the service, such as the `ProtocolHeader` property in the previous example, whereas in WCF syntax, they are more accurately represented as properties of messages.</span></span> <span data-ttu-id="a4d56-244">Además, WCF permite a los encabezados del mensaje que se agregarán a la configuración de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a4d56-244">Also, WCF allows message headers to be added to the configuration of endpoints.</span></span>

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

<span data-ttu-id="a4d56-245">Esa opción permite evitar cualquier referencia a los encabezados de protocolo de la infraestructura en el código de un cliente o servicio: los encabezados se agregan a los mensajes debido a cómo se configura el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a4d56-245">That option allows you to avoid any reference to infrastructural protocol headers in the code for a client or service: the headers are added to messages because of how the endpoint is configured.</span></span>

## <a name="service-description"></a><span data-ttu-id="a4d56-246">Descripción del servicio</span><span class="sxs-lookup"><span data-stu-id="a4d56-246">Service Description</span></span>

<span data-ttu-id="a4d56-247">Emitir una solicitud GET de HTTP para el archivo .asmx de un servicio web ASP.NET con el WSDL de la consulta, provoca que ASP.NET genere WSDL para describir el servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-247">Issuing an HTTP GET request for the .asmx file of an ASP.NET Web service with the query WSDL causes ASP.NET to generate WSDL to describe the service.</span></span> <span data-ttu-id="a4d56-248">Devuelve ese WSDL como respuesta a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a4d56-248">It returns that WSDL as the response to the request.</span></span>

<span data-ttu-id="a4d56-249">ASP.NET 2.0 permitió validar si un servicio es conforme a Basic Profile 1.1 de Web Services-Interoperability Organization (WS-I), e insertar una notificación informando de que el servicio es conforme a su WSDL.</span><span class="sxs-lookup"><span data-stu-id="a4d56-249">ASP.NET 2.0 made it possible to validate that a service is compliant with the Basic Profile 1.1 of the Web Services-Interoperability Organization (WS-I), and to insert a claim that the service is compliant into its WSDL.</span></span> <span data-ttu-id="a4d56-250">Esto se lleva a cabo utilizando `ConformsTo` y los parámetros `EmitConformanceClaims` del atributo <xref:System.Web.Services.WebServiceBindingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-250">That is done using the `ConformsTo` and `EmitConformanceClaims` parameters of the <xref:System.Web.Services.WebServiceBindingAttribute> attribute.</span></span>

```csharp
[WebService(Namespace = "http://tempuri.org/")]
[WebServiceBinding(
     ConformsTo = WsiProfiles.BasicProfile1_1,
     EmitConformanceClaims=true)]
public interface IEcho
```

<span data-ttu-id="a4d56-251">Se puede personalizar el WSDL que genera ASP.NET para un servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-251">The WSDL that ASP.NET generates for a service can be customized.</span></span> <span data-ttu-id="a4d56-252">Las personalización se realiza creando una clase derivada de <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension>, para agregar elementos a WSDL.</span><span class="sxs-lookup"><span data-stu-id="a4d56-252">Customizations are made by creating a derived class of <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> to add items to the WSDL.</span></span>

<span data-ttu-id="a4d56-253">Emitir una solicitud HTTP GET con el WSDL de la consulta para el archivo .svc de un servicio WCF con un extremo HTTP hospedado en IIS 51, 6.0 o WAS hace que WCF responda con WSDL para describir el servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-253">Issuing an HTTP GET request with the query WSDL for the .svc file of a WCF service with an HTTP endpoint hosted within IIS 51, 6.0 or WAS causes WCF to respond with WSDL to describe the service.</span></span> <span data-ttu-id="a4d56-254">Establecer httpGetEnabled en true tiene el mismo efecto que enviar una solicitud HTTP GET con el WSDL de la consulta a la dirección base HTTP de un servicio hospedado en una aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-254">Issuing an HTTP GET request with the query WSDL to the HTTP base address of a service hosted within a .NET application has the same effect if httpGetEnabled is set to true.</span></span>

<span data-ttu-id="a4d56-255">Sin embargo, WCF también responde a las solicitudes de WS-MetadataExchange con WSDL que genera para describir un servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-255">However, WCF also responds to WS-MetadataExchange requests with WSDL that it generates to describe a service.</span></span> <span data-ttu-id="a4d56-256">Los servicios web ASP.NET no tienen compatibilidad integrada con las solicitudes de WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="a4d56-256">ASP.NET Web services do not have built-in support for WS-MetadataExchange requests.</span></span>

<span data-ttu-id="a4d56-257">Se puede personalizar ampliamente el WSDL que genera de WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-257">The WSDL that WCF generates can be extensively customized.</span></span> <span data-ttu-id="a4d56-258">La clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> proporciona algunas funciones para personalizar el WSDL.</span><span class="sxs-lookup"><span data-stu-id="a4d56-258">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class provides some facilities for customizing the WSDL.</span></span> <span data-ttu-id="a4d56-259">WCF también puede configurarse para no generar WSDL, sino usar un archivo WSDL estático en una dirección URL dada.</span><span class="sxs-lookup"><span data-stu-id="a4d56-259">The WCF can also be configured to not generate WSDL, but rather to use a static WSDL file at a given URL.</span></span>

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

## <a name="exception-handling"></a><span data-ttu-id="a4d56-260">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="a4d56-260">Exception Handling</span></span>

<span data-ttu-id="a4d56-261">En los servicios web ASP.NET, las excepciones no controladas se devuelven a los clientes como errores de SOAP.</span><span class="sxs-lookup"><span data-stu-id="a4d56-261">In ASP.NET Web services, unhandled exceptions are returned to clients as SOAP faults.</span></span> <span data-ttu-id="a4d56-262">También puede iniciar explícitamente instancias de la clase <xref:System.Web.Services.Protocols.SoapException> y tener más control sobre el contenido del error de SOAP que se transmite al cliente.</span><span class="sxs-lookup"><span data-stu-id="a4d56-262">You can also explicitly throw instances of the <xref:System.Web.Services.Protocols.SoapException> class and have more control over the content of the SOAP fault that gets transmitted to the client.</span></span>

<span data-ttu-id="a4d56-263">En los servicios WCF, las excepciones no controladas no se devuelven a los clientes como errores de SOAP para impedir que información confidencial accidentalmente que se exponen a través de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="a4d56-263">In WCF services, unhandled exceptions are not returned to clients as SOAP faults to prevent sensitive information being inadvertently exposed through the exceptions.</span></span> <span data-ttu-id="a4d56-264">Se proporciona un valor de configuración para devolver las excepciones no controladas a los clientes con el propósito de depurarlas.</span><span class="sxs-lookup"><span data-stu-id="a4d56-264">A configuration setting is provided to have unhandled exceptions returned to clients for the purpose of debugging.</span></span>

<span data-ttu-id="a4d56-265">Para devolver los errores de SOAP a los clientes, puede iniciar las instancias del tipo genérico, <xref:System.ServiceModel.FaultException%601>, utilizando el tipo de contrato de datos como tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="a4d56-265">To return SOAP faults to clients, you can throw instances of the generic type, <xref:System.ServiceModel.FaultException%601>, using the data contract type as the generic type.</span></span> <span data-ttu-id="a4d56-266">Además, puede agregar los atributos <xref:System.ServiceModel.FaultContractAttribute> a las operaciones para especificar los errores que podría producir una operación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-266">You can also add <xref:System.ServiceModel.FaultContractAttribute> attributes to operations to specify the faults that an operation might yield.</span></span>

```csharp
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

<span data-ttu-id="a4d56-267">Con esto, los posibles errores podrían anunciarse en el WSDL del servicio, lo que permitiría a los desarrolladores del cliente anticipar qué errores pueden ser el resultado de una operación, y escribir las instrucciones de captura adecuadas.</span><span class="sxs-lookup"><span data-stu-id="a4d56-267">Doing so results in the possible faults being advertised in the WSDL for the service, allowing client programmers to anticipate which faults can result from an operation, and write the appropriate catch statements.</span></span>

```csharp
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

## <a name="state-management"></a><span data-ttu-id="a4d56-268">Administración de estado</span><span class="sxs-lookup"><span data-stu-id="a4d56-268">State Management</span></span>

<span data-ttu-id="a4d56-269">La clase utilizada para implementar un servicio web ASP.NET se puede derivar de <xref:System.Web.Services.WebService>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-269">The class used to implement an ASP.NET Web service may be derived from <xref:System.Web.Services.WebService>.</span></span>

```csharp
public class Service : WebService, IEcho
{

 public string Echo(string input)
 {
  return input;
 }
}
```

<span data-ttu-id="a4d56-270">En ese caso, la clase puede programarse para utilizar la propiedad del contexto de la clase base <xref:System.Web.Services.WebService> para tener acceso a un objeto <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-270">In that case, the class can be programmed to use the <xref:System.Web.Services.WebService> base class’ Context property to access a <xref:System.Web.HttpContext> object.</span></span> <span data-ttu-id="a4d56-271">Se puede utilizar el objeto <xref:System.Web.HttpContext> para actualizar y recuperar información del estado de la aplicación mediante su propiedad Application, y puede utilizarse para actualizar y recuperar información del estado de la sesión utilizando su propiedad Session.</span><span class="sxs-lookup"><span data-stu-id="a4d56-271">The <xref:System.Web.HttpContext> object can be used to update and retrieve application state information by using its Application property, and can be used to update and retrieve session state information by using its Session property.</span></span>

<span data-ttu-id="a4d56-272">ASP.NET proporciona un control considerable sobre dónde se almacena realmente la información del estado de la sesión a la que se accedió mediante la propiedad Session de <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-272">ASP.NET provides considerable control over where the session state information accessed by using the Session property of the <xref:System.Web.HttpContext> is actually stored.</span></span> <span data-ttu-id="a4d56-273">Puede almacenarse en cookies, en una base de datos, en la memoria del servidor actual o en la memoria de un servidor designado.</span><span class="sxs-lookup"><span data-stu-id="a4d56-273">It may be stored in cookies, in a database, in the memory of the current server, or in the memory of a designated server.</span></span> <span data-ttu-id="a4d56-274">La elección se realiza en el archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-274">The choice is made in the service’s configuration file.</span></span>

<span data-ttu-id="a4d56-275">WCF proporciona objetos extensibles para la administración de estado.</span><span class="sxs-lookup"><span data-stu-id="a4d56-275">The WCF provides extensible objects for state management.</span></span> <span data-ttu-id="a4d56-276">Los objetos extensibles son objetos que implementan <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-276">Extensible objects are objects that implement <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="a4d56-277">Los objetos extensibles más importantes son <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-277">The most important extensible objects are <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="a4d56-278">`ServiceHostBase` permite mantener el estado al que pueden tener acceso todas las instancias de todos los tipos de servicio en el mismo host, mientras que `InstanceContext` permite mantener el estado al que puede tener acceso cualquier código que se ejecute dentro de la misma instancia de un tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-278">`ServiceHostBase` allows you to maintain state that all of the instances of all of the service types on the same host can access, while `InstanceContext` allows you to maintain state that can be accessed by any code running within the same instance of a service type.</span></span>

<span data-ttu-id="a4d56-279">Aquí, el tipo de servicio `TradingSystem`, tiene un <xref:System.ServiceModel.ServiceBehaviorAttribute> que especifica que todas las llamadas desde la misma instancia de cliente WCF se enrutan a la misma instancia del tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-279">Here, the service type, `TradingSystem`, has a <xref:System.ServiceModel.ServiceBehaviorAttribute> that specifies that all calls from the same WCF client instance are routed to the same instance of the service type.</span></span>

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class TradingSystem: ITradingService
```

<span data-ttu-id="a4d56-280">La clase, `DealData`, define el estado al que puede acceder cualquier código que se ejecute en la misma instancia de un tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-280">The class, `DealData`, defines state that can be accessed by any code running in the same instance of a service type.</span></span>

```csharp
internal class DealData: IExtension<InstanceContext>
{
 public string DealIdentifier = null;
 public Trade[] Trades = null;
}
```

<span data-ttu-id="a4d56-281">En el código del tipo de servicio que implementa una de las operaciones del contrato de servicios, se agrega un objeto de estados `DealData` al estado de la instancia actual del tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4d56-281">In the code of the service type that implements one of the operations of the service contract, a `DealData` state object is added to the state of the current instance of the service type.</span></span>

```csharp
string ITradingService.BeginDeal()
{
 string dealIdentifier = Guid.NewGuid().ToString();
 DealData state = new DealData(dealIdentifier);
 OperationContext.Current.InstanceContext.Extensions.Add(state);
 return dealIdentifier;
}
```

<span data-ttu-id="a4d56-282">Después, el código que implementa otras operaciones del contrato de servicio puede recuperar y modificar ese objeto de estados.</span><span class="sxs-lookup"><span data-stu-id="a4d56-282">That state object can then be retrieved and modified by the code that implements another of the service contract’s operations.</span></span>

```csharp
void ITradingService.AddTrade(Trade trade)
{
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();
 dealData.AddTrade(trade);
}
```

<span data-ttu-id="a4d56-283">Mientras que ASP.NET permite controlar dónde información de estado en el <xref:System.Web.HttpContext> clase se almacena realmente, WCF, al menos en su versión inicial, no proporciona ningún control sobre dónde se almacenan los objetos extensibles.</span><span class="sxs-lookup"><span data-stu-id="a4d56-283">Whereas ASP.NET provides control over where state information in the <xref:System.Web.HttpContext> class is actually stored, WCF, at least in its initial version, provides no control over where extensible objects are stored.</span></span> <span data-ttu-id="a4d56-284">Que constituye la mejor razón para seleccionar el modo de compatibilidad ASP.NET para un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-284">That constitutes the very best reason for selecting the ASP.NET compatibility mode for a WCF service.</span></span> <span data-ttu-id="a4d56-285">Si la administración de estados configurable es imperativa, optar por el modo de compatibilidad de ASP.NET permite utilizar las funciones de la clase <xref:System.Web.HttpContext> exactamente igual a como se utilizan en ASP.NET, y, además, configurar dónde se almacena la información gestionada mediante la clase <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-285">If configurable state management is imperative, then opting for the ASP.NET compatibility mode allows you to use the facilities of the <xref:System.Web.HttpContext> class exactly as they are used in ASP.NET, and also to configure where state information managed by using the <xref:System.Web.HttpContext> class is stored.</span></span>

## <a name="security"></a><span data-ttu-id="a4d56-286">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a4d56-286">Security</span></span>

<span data-ttu-id="a4d56-287">Las opciones para proteger los servicios web ASP.NET son las mismas que para proteger cualquier aplicación IIS.</span><span class="sxs-lookup"><span data-stu-id="a4d56-287">The options for securing ASP.NET Web services are those for securing any IIS application.</span></span> <span data-ttu-id="a4d56-288">Dado que las aplicaciones WCF pueden hospedarse no solo dentro de IIS, sino también dentro de cualquier archivo ejecutable. NET, las opciones para proteger las aplicaciones WCF deben realizarse independientes de las funciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="a4d56-288">Because WCF applications can be hosted not only within IIS but also within any .NET executable, the options for securing WCF applications must be made independent from the facilities of IIS.</span></span> <span data-ttu-id="a4d56-289">Sin embargo, las funciones proporcionadas para los servicios Web de ASP.NET también están disponibles para los servicios WCF que se ejecuta en modo de compatibilidad ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-289">However, the facilities provided for ASP.NET Web services are also available for WCF services running in ASP.NET compatibility mode.</span></span>

### <a name="security-authentication"></a><span data-ttu-id="a4d56-290">Seguridad: Autenticación</span><span class="sxs-lookup"><span data-stu-id="a4d56-290">Security: Authentication</span></span>

<span data-ttu-id="a4d56-291">IIS proporciona funciones para controlar el acceso a las aplicaciones que puede seleccionar el acceso anónimo o una variedad de modos de autenticación: Autenticación de Windows, la autenticación implícita, autenticación básica y autenticación de .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="a4d56-291">IIS provides facilities for controlling access to applications by which you can select either anonymous access or a variety of modes of authentication: Windows Authentication, Digest Authentication, Basic Authentication, and .NET Passport Authentication.</span></span> <span data-ttu-id="a4d56-292">La opción de autenticación de Windows puede utilizarse para controlar el acceso a los servicios web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-292">The Windows Authentication option can be used to control access to ASP.NET Web services.</span></span> <span data-ttu-id="a4d56-293">Sin embargo, cuando se hospedan aplicaciones WCF en IIS, IIS debe configurarse para permitir el acceso anónimo a la aplicación, por lo que la autenticación puede administrarse mediante WCF, que es compatible con la autenticación de Windows entre otras opciones.</span><span class="sxs-lookup"><span data-stu-id="a4d56-293">However, when WCF applications are hosted within IIS, IIS must be configured to permit anonymous access to the application, so that authentication can be managed by WCF itself, which does support Windows authentication among various other options.</span></span> <span data-ttu-id="a4d56-294">Las otras opciones integradas incluyen tokens del nombre de usuario, certificados X.509, tokens SAML, y tarjeta CardSpace, aunque también pueden definirse otros mecanismos de autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="a4d56-294">The other options that are built-in include username tokens, X.509 certificates, SAML tokens, and CardSpace card, but custom authentication mechanisms can also be defined.</span></span>

### <a name="security-impersonation"></a><span data-ttu-id="a4d56-295">Seguridad: Suplantación</span><span class="sxs-lookup"><span data-stu-id="a4d56-295">Security: Impersonation</span></span>

<span data-ttu-id="a4d56-296">ASP.NET proporciona un elemento de identidad por el que un servicio web ASP.NET puede suplantar a un usuario determinado, o a cualquier credencial de usuario proporcionada por la solicitud actual.</span><span class="sxs-lookup"><span data-stu-id="a4d56-296">ASP.NET provides an identity element by which an ASP.NET Web service can be made to impersonate a particular user or whichever user’s credentials are provided with the current request.</span></span> <span data-ttu-id="a4d56-297">Ese elemento puede utilizarse para configurar la suplantación en aplicaciones de WCF que se ejecutan en modo de compatibilidad ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-297">That element can be used to configure impersonation in WCF applications running in ASP.NET compatibility mode.</span></span>

<span data-ttu-id="a4d56-298">El sistema de configuración de WCF proporciona su propio elemento de identidad para designar a un usuario determinado para suplantar.</span><span class="sxs-lookup"><span data-stu-id="a4d56-298">The WCF configuration system provides its own identity element for designating a particular user to impersonate.</span></span> <span data-ttu-id="a4d56-299">Además, servicios y clientes WCF pueden independientemente configurarse para la suplantación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-299">Also, WCF clients and services can be independently configured for impersonation.</span></span> <span data-ttu-id="a4d56-300">Los clientes pueden configurarse para suplantar al usuario actual cuando transmiten las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="a4d56-300">Clients can be configured to impersonate the current user when they transmit requests.</span></span>

```xml
<behaviors>
     <behavior name="DerivativesCalculatorClientBehavior">
      <clientCredentials>
      <windows allowedImpersonationLevel="Impersonation"/>
      </clientCredentials>
     </behavior>
</behaviors>
```

<span data-ttu-id="a4d56-301">Las operaciones del servicio pueden configurarse para suplantar cualquier credencial de usuario proporcionada con la solicitud actual.</span><span class="sxs-lookup"><span data-stu-id="a4d56-301">Service operations can be configured to impersonate whichever user’s credentials are provided with the current request.</span></span>

```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]
public void Receive(Message input)
```

### <a name="security-authorization-using-access-control-lists"></a><span data-ttu-id="a4d56-302">Seguridad: Uso de listas de Control de acceso de autorización</span><span class="sxs-lookup"><span data-stu-id="a4d56-302">Security: Authorization using Access Control Lists</span></span>

<span data-ttu-id="a4d56-303">Las listas de control de acceso (ACL) pueden utilizarse para restringir el acceso a los archivos .asmx.</span><span class="sxs-lookup"><span data-stu-id="a4d56-303">Access Control Lists (ACLs) can be used to restrict access to .asmx files.</span></span> <span data-ttu-id="a4d56-304">Sin embargo, las ACL en los archivos .svc de WCF se ignoran, excepto en el modo de compatibilidad ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-304">However, ACLs on WCF .svc files are ignored except in ASP.NET compatibility mode.</span></span>

### <a name="security-role-based-authorization"></a><span data-ttu-id="a4d56-305">Seguridad: Autorización basada en roles</span><span class="sxs-lookup"><span data-stu-id="a4d56-305">Security: Role-based Authorization</span></span>

<span data-ttu-id="a4d56-306">La opción de autenticación de Windows de IIS puede utilizarse, junto con el elemento de autorización proporcionado por el lenguaje de configuración de ASP.NET, para facilitar la autorización basada en las funciones de los servicios web ASP.NET basados en los grupos de Windows a los que están asignados los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a4d56-306">The IIS Windows Authentication option can be used in conjunction with the authorization element provided by the ASP.NET configuration language to facilitate role-based authorization for ASP.NET Web services based on the Windows groups to which users are assigned.</span></span> <span data-ttu-id="a4d56-307">ASP.NET 2.0 introdujo un mecanismo de autorización basado en funciones más general: proveedores de funciones.</span><span class="sxs-lookup"><span data-stu-id="a4d56-307">ASP.NET 2.0 introduced a more general role-based authorization mechanism: role providers.</span></span>

<span data-ttu-id="a4d56-308">Los proveedores de funciones son clases que implementan una interfaz básica para informarse sobre las funciones a las que está asignado un usuario, pero cada proveedor de funciones sabe cómo recuperar esa información desde un origen diferente.</span><span class="sxs-lookup"><span data-stu-id="a4d56-308">Role providers are classes that all implement a basic interface for enquiring about the roles to which a user is assigned, but each role provider knows how to retrieve that information from a different source.</span></span> <span data-ttu-id="a4d56-309">ASP.NET 2.0 proporciona un proveedor de funciones que puede recuperar las asignaciones de funciones de una base de datos de Microsoft SQL Server ,y otro que puede recuperar las asignaciones de funciones del administrador de autorización de Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="a4d56-309">ASP.NET 2.0 provides a role provider that can retrieve role assignments from a Microsoft SQL Server database, and another that can retrieve role assignments from the Windows Server 2003 Authorization Manager.</span></span>

<span data-ttu-id="a4d56-310">El mecanismo de proveedores de funciones realmente puede usarse independientemente de ASP.NET en cualquier aplicación. NET, incluidos una aplicación de WCF.</span><span class="sxs-lookup"><span data-stu-id="a4d56-310">The role provider mechanism can actually be used independently of ASP.NET in any .NET application, including a WCF application.</span></span> <span data-ttu-id="a4d56-311">Para una aplicación WCF la configuración del ejemplo siguiente muestra cómo el uso de un proveedor de funciones ASP.NET es una opción seleccionada por medio de la <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-311">The following sample configuration for a WCF application shows how the use of an ASP.NET role provider is an option selected by means of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>

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

### <a name="security-claims-based-authorization"></a><span data-ttu-id="a4d56-312">Seguridad: Autorización basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="a4d56-312">Security: Claims-based Authorization</span></span>

<span data-ttu-id="a4d56-313">Una de las innovaciones más importantes de WCF es su compatibilidad para autorizar el acceso a recursos protegidos basado en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="a4d56-313">One of the most important innovations of WCF is its thorough support for authorizing access to protected resources based on claims.</span></span> <span data-ttu-id="a4d56-314">Las notificaciones se componen de un tipo, un derecho y un valor, por ejemplo, el número del permiso de conducir.</span><span class="sxs-lookup"><span data-stu-id="a4d56-314">Claims consist of a type, a right and a value, a drivers’ license, for example.</span></span> <span data-ttu-id="a4d56-315">Realiza un conjunto de notificaciones sobre el portador, una de las cuales es la fecha de nacimiento del portador.</span><span class="sxs-lookup"><span data-stu-id="a4d56-315">It makes a set of claims about the bearer, one of which is the bearer’s date of birth.</span></span> <span data-ttu-id="a4d56-316">El tipo de esa notificación es “fecha de nacimiento”, y el valor de la notificación la fecha de nacimiento del conductor.</span><span class="sxs-lookup"><span data-stu-id="a4d56-316">The type of that claim is date of birth, while the value of the claim is the driver’s birth date.</span></span> <span data-ttu-id="a4d56-317">El derecho que confiere una notificación al portador especifica lo que el portador puede hacer con el valor de la notificación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-317">The right that a claim confers on the bearer specifies what the bearer can do with the claim’s value.</span></span> <span data-ttu-id="a4d56-318">En el caso de la notificación de la fecha de nacimiento del conductor, el derecho es la posesión: el conductor posee esa fecha de nacimiento pero, por ejemplo, no puede modificarla.</span><span class="sxs-lookup"><span data-stu-id="a4d56-318">In the case of the claim of the driver’s date of birth, the right is possession: the driver possesses that date of birth but cannot, for example, alter it.</span></span> <span data-ttu-id="a4d56-319">La autorización basada en notificaciones engloba a la autorización basada en funciones, ya que las funciones son un tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-319">Claims-based authorization encloses role-based authorization, because roles are a type of claim.</span></span>

<span data-ttu-id="a4d56-320">La autorización basada en notificaciones finaliza con la comparación de un conjunto de notificaciones con los requisitos de acceso de la operación y, dependiendo del resultado de esa comparación, se otorga o se deniega el acceso a la operación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-320">Authorization based on claims is accomplished by comparing a set of claims to the access requirements of the operation and, depending on the outcome of that comparison, granting or denying access to the operation.</span></span> <span data-ttu-id="a4d56-321">En WCF, puede especificar una clase se utiliza para ejecutar la autorización basada en notificaciones, una vez más asignando un valor para el `ServiceAuthorizationManager` propiedad de <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a4d56-321">In WCF, you can specify a class to use to run claims-based authorization, once again by assigning a value to the `ServiceAuthorizationManager` property of <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>

```xml
<behaviors>
     <behavior name='ServiceBehavior'>
     <serviceAuthorization
     serviceAuthorizationManagerType=
                   'Service.AccessChecker, Service' />
     </behavior>
</behaviors>
```

<span data-ttu-id="a4d56-322">Las clases usadas para ejecutar la autorización basada en notificaciones deben derivar de <xref:System.ServiceModel.ServiceAuthorizationManager>, que tiene un solo método para reemplazar, `AccessCheck()`.</span><span class="sxs-lookup"><span data-stu-id="a4d56-322">Classes used to run claims-based authorization must derive from <xref:System.ServiceModel.ServiceAuthorizationManager>, which has just one method to override, `AccessCheck()`.</span></span> <span data-ttu-id="a4d56-323">WCF llama a ese método cada vez que una operación del servicio se invoca y proporciona un <xref:System.ServiceModel.OperationContext> objeto, que tiene las notificaciones para el usuario en su `ServiceSecurityContext.AuthorizationContext` propiedad.</span><span class="sxs-lookup"><span data-stu-id="a4d56-323">WCF calls that method whenever an operation of the service is invoked and provides a <xref:System.ServiceModel.OperationContext> object, which has the claims for the user in its `ServiceSecurityContext.AuthorizationContext` property.</span></span> <span data-ttu-id="a4d56-324">WCF encarga de ensamblar las notificaciones sobre el usuario del token de seguridad el usuario proporcionado para la autenticación, lo que deja la tarea de evaluar si esas notificaciones son suficientes para la operación en cuestión.</span><span class="sxs-lookup"><span data-stu-id="a4d56-324">WCF does the work of assembling claims about the user from whatever security token the user provided for authentication, which leaves the of task of evaluating whether those claims suffice for the operation in question.</span></span>

<span data-ttu-id="a4d56-325">Que WCF ensamble automáticamente las notificaciones de cualquier tipo de seguridad de token es una innovación muy significativa, ya que hace el código de autorización basada en notificaciones completamente independientes de los mecanismos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="a4d56-325">That WCF automatically assembles claims from any kind of security token is a highly significant innovation, because it makes the code for authorization based on the claims entirely independent of the authentication mechanism.</span></span> <span data-ttu-id="a4d56-326">Por el contrario, la autorización mediante las ACL o las funciones de ASP.NET está estrechamente vinculada a la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="a4d56-326">By contrast, authorization using ACLs or roles in ASP.NET is closely tied to Windows authentication.</span></span>

### <a name="security-confidentiality"></a><span data-ttu-id="a4d56-327">Seguridad: Confidencialidad</span><span class="sxs-lookup"><span data-stu-id="a4d56-327">Security: Confidentiality</span></span>

<span data-ttu-id="a4d56-328">La confidencialidad de los mensajes intercambiados con los servicios web de ASP.NET puede protegerse en el nivel de transporte configurando la aplicación de IIS para que utilice el protocolo de transferencia segura de hipertexto (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="a4d56-328">The confidentiality of messages exchanged with ASP.NET Web services can be ensured at the transport level by configuring the application within IIS to use the Secure Hypertext Transfer Protocol (HTTPS).</span></span> <span data-ttu-id="a4d56-329">Lo mismo se puede hacer para aplicaciones de WCF hospedadas en IIS.</span><span class="sxs-lookup"><span data-stu-id="a4d56-329">The same can be done for WCF applications hosted within IIS.</span></span> <span data-ttu-id="a4d56-330">Sin embargo, las aplicaciones de WCF hospedadas fuera de IIS pueden configurarse para usar un protocolo de transporte seguro.</span><span class="sxs-lookup"><span data-stu-id="a4d56-330">However, WCF applications hosted outside of IIS can also be configured to use a secure transport protocol.</span></span> <span data-ttu-id="a4d56-331">Más importante aún, también se pueden configurar las aplicaciones de WCF para proteger los mensajes antes de que se transportan, mediante el protocolo WS-Security.</span><span class="sxs-lookup"><span data-stu-id="a4d56-331">More important, WCF applications can also be configured to secure the messages before they are transported, using the WS-Security protocol.</span></span> <span data-ttu-id="a4d56-332">Simplemente protegiendo el cuerpo de un mensaje mediante WS-Security, permite su transmisión confidencial a través de intermediarios antes de alcanzar su último destino.</span><span class="sxs-lookup"><span data-stu-id="a4d56-332">Securing just the body of a message using WS-Security allows it to be transmitted confidentially across intermediaries before reaching its final destination.</span></span>

## <a name="globalization"></a><span data-ttu-id="a4d56-333">Globalización</span><span class="sxs-lookup"><span data-stu-id="a4d56-333">Globalization</span></span>

<span data-ttu-id="a4d56-334">El lenguaje de configuración de ASP.NET permite especificar una referencia cultural para los servicios individuales.</span><span class="sxs-lookup"><span data-stu-id="a4d56-334">The ASP.NET configuration language allows you to specify the culture for individual services.</span></span> <span data-ttu-id="a4d56-335">WCF no admite ese valor de configuración, excepto en el modo de compatibilidad ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4d56-335">The WCF does not support that configuration setting except in ASP.NET compatibility mode.</span></span> <span data-ttu-id="a4d56-336">Para localizar un servicio WCF que no utiliza el modo de compatibilidad ASP.NET, compile el tipo de servicio en los ensamblados específicos de la referencia cultural y tiene puntos de conexión específicas de referencias culturales independientes para cada ensamblado específico de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="a4d56-336">To localize a WCF service that does not use ASP.NET compatibility mode, compile the service type into culture-specific assemblies, and have separate culture-specific endpoints for each culture-specific assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4d56-337">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4d56-337">See also</span></span>

- [<span data-ttu-id="a4d56-338">Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas</span><span class="sxs-lookup"><span data-stu-id="a4d56-338">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
