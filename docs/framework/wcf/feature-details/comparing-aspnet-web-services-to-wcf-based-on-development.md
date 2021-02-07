---
description: Más información acerca de la comparación de los servicios Web de ASP.NET con WCF basado en el desarrollo
title: Comparación de los servicios web ASP.NET con el WCF basado en desarrollo
ms.date: 03/30/2017
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
ms.openlocfilehash: fa9db35070bdde32d509f0e9c25dbf179d64da32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743465"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a>Comparación de los servicios web ASP.NET con el WCF basado en desarrollo

Windows Communication Foundation (WCF) tiene una opción de modo de compatibilidad ASP.NET para permitir que las aplicaciones WCF se programen y configuren como los servicios Web de ASP.NET y imiten su comportamiento. En las secciones siguientes se comparan los servicios Web de ASP.NET y WCF en función de lo que se necesita para desarrollar aplicaciones con ambas tecnologías.

## <a name="data-representation"></a>Representación de datos

Normalmente, el desarrollo de un servicio web con ASP.NET comienza con la definición de todos los tipos de datos complejos que utilizará el servicio. ASP.NET se basa en <xref:System.Xml.Serialization.XmlSerializer> para traducir los datos representados por los tipos de .NET Framework a XML para la transmisión hacia o desde un servicio, y para traducir los datos recibidos como XML en los objetos de .NET Framework. La definición de los tipos de datos complejos que utilizará un servicio de ASP.NET requiere la definición de las clases de .NET Framework que <xref:System.Xml.Serialization.XmlSerializer> puede serializar a y desde XML. Estas clases pueden escribirse manualmente o generarse a partir de las definiciones de los tipos de Esquema XML, mediante la línea de comandos de la utilidad de compatibilidad de tipos de datos de XML, xsd.exe.

La siguiente lista muestra problemas clave que deben tenerse en cuenta al definir las clases de .NET Framework que <xref:System.Xml.Serialization.XmlSerializer> puede serializar a y desde XML:

- Solo los campos y propiedades públicas de los objetos de .NET Framework se traducen a XML.

- Las instancias de las clases de colección solo pueden serializarse a XML si las clases implementan <xref:System.Collections.IEnumerable>, o la interfaz <xref:System.Collections.ICollection>.

- Las clases que implementan la interfaz <xref:System.Collections.IDictionary>, como <xref:System.Collections.Hashtable>, no pueden serializarse en XML.

- La gran cantidad de tipos de atributo existente en el espacio de nombres <xref:System.Xml.Serialization>, puede agregarse a una clase de .NET Framework y sus miembros para controlar la representación de las instancias de la clase en XML.

El desarrollo de aplicaciones WCF normalmente también comienza con la definición de tipos complejos. WCF se puede usar para utilizar los mismos tipos de .NET Framework que los servicios Web ASP.NET.

WCF <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> se pueden agregar a tipos de .NET Framework para indicar que las instancias del tipo se van a serializar en XML, y qué campos o propiedades concretos del tipo se van a serializar, como se muestra en el código de ejemplo siguiente.

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

<xref:System.Runtime.Serialization.DataContractAttribute> significa que cero o más campos o propiedades de un tipo deberán serializarse, mientras que <xref:System.Runtime.Serialization.DataMemberAttribute> indica que se serializará un campo o propiedad concreta. El atributo <xref:System.Runtime.Serialization.DataContractAttribute> se puede aplicar a una clase o a una estructura. <xref:System.Runtime.Serialization.DataMemberAttribute> se puede aplicar a un campo o una propiedad, y los campos y propiedades a las que se aplica el atributo pueden ser públicos o privados. Las instancias de tipos a las que <xref:System.Runtime.Serialization.DataContractAttribute> se les aplica se conocen como contratos de datos en WCF. Se serializan en XML mediante <xref:System.Runtime.Serialization.DataContractSerializer>.

La siguiente lista enumera las principales diferencias entre la utilización de <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>, así como los distintos atributos del espacio de nombres <xref:System.Xml.Serialization>.

- <xref:System.Xml.Serialization.XmlSerializer> y los atributos del espacio de nombres <xref:System.Xml.Serialization> están diseñados para permitir asignar los tipos de .NET Framework a cualquier tipo válido definido en Esquema XML, de modo que ofrecen un control muy preciso de la representación de un tipo en XML. <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> proporcionan un control muy preciso sobre la representación de un tipo en XML. Solo pueden especificarse los espacios de nombres y los nombres utilizados para representar el tipo y sus campos, o propiedades en XML, así como la secuencia de aparición en XML de los campos y propiedades:

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

  El resto de información sobre la estructura de XML utilizada para representar el tipo .NET está determinada por <xref:System.Runtime.Serialization.DataContractSerializer>.

- Al no permitir un mayor control sobre la representación de un tipo en XML, el proceso de serialización se vuelve extremadamente predecible para <xref:System.Runtime.Serialization.DataContractSerializer>y, por lo tanto, más fácil de optimizar. Una ventaja práctica del diseño de <xref:System.Runtime.Serialization.DataContractSerializer> es un mejor rendimiento, aproximadamente un diez por ciento mejor.

- Los atributos utilizados con <xref:System.Xml.Serialization.XmlSerializer> no indican qué campos o propiedades del tipo se serializan en XML, mientras que <xref:System.Runtime.Serialization.DataMemberAttribute> utilizado con <xref:System.Runtime.Serialization.DataContractSerializer> muestra explícitamente qué campos o propiedades se serializan. Por consiguiente, los contratos de datos son contratos explícitos de la estructura de datos que una aplicación enviará y recibirá.

- <xref:System.Xml.Serialization.XmlSerializer> solo puede traducir a XML los miembros públicos de un objeto .NET, <xref:System.Runtime.Serialization.DataContractSerializer> puede traducir a XML los miembros de objetos independientemente de los modificadores de acceso de esos miembros.

- Como consecuencia de poder serializar en XML los miembros no públicos de tipos, <xref:System.Runtime.Serialization.DataContractSerializer> posee menos restricciones en la variedad de tipos .NET que puede serializar en XML. En concreto, puede traducir a XML tipos como <xref:System.Collections.Hashtable> que implementa la interfaz <xref:System.Collections.IDictionary>. Es mucho más probable que <xref:System.Runtime.Serialization.DataContractSerializer> pueda serializar en XML las instancias de cualquiera tipo .NET existentes previamente, sin tener que modificar la definición del tipo o desarrollar un contenedor para él.

- Otra consecuencia de que <xref:System.Runtime.Serialization.DataContractSerializer> pueda tener acceso a los miembros no públicos de un tipo es que requiere plena confianza, al contrario que <xref:System.Xml.Serialization.XmlSerializer>. El permiso de acceso al código de plena confianza proporciona acceso completo a todos los recursos de un equipo al que se puede tener acceso mediante las credenciales con las que se ejecuta el código. Esta opción debe usarse con cuidado, ya que el código de plena confianza accede a todos los recursos de la máquina.

- <xref:System.Runtime.Serialization.DataContractSerializer> incorpora cierta compatibilidad para el control de versiones:

  - <xref:System.Runtime.Serialization.DataMemberAttribute> posee una propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> a la puede asignarse un valor de falso para los miembros que se agregan a las nuevas versiones de un contrato de datos que no se encontraban en versiones anteriores, con lo que las aplicaciones con la versión más reciente del contrato pueden procesar las versiones anteriores.

  - Cuando un contrato de datos implementa la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>, es posible permitir a <xref:System.Runtime.Serialization.DataContractSerializer> pasar miembros definidos en versiones más recientes de un contrato de datos a través de aplicaciones con versiones anteriores del contrato.

A pesar de todas las diferencias, el XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, siempre y cuando defina explícitamente el espacio de nombres de XML. La siguiente clase, que tiene atributos para su uso con ambos serializadores, se convierte en XML semánticamente idéntico por <xref:System.Xml.Serialization.XmlSerializer> y mediante <xref:System.Runtime.Serialization.DataContractAttribute> :

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

El kit de desarrollo de software (SDK) de Windows incluye una herramienta de línea de comandos denominada [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Al igual que la herramienta xsd.exe que se usa con los servicios Web de ASP.NET, Svcutil.exe puede generar definiciones de tipos de datos .NET a partir del esquema XML. Los tipos son contratos de datos si <xref:System.Runtime.Serialization.DataContractSerializer> puede emitir XML con el formato definido por esquema XML; de lo contrario, están diseñados para serializarse mediante <xref:System.Xml.Serialization.XmlSerializer>. Svcutil.exe también puede generar un esquema XML a partir de contratos de datos utilizando su `dataContractOnly` modificador.

> [!NOTE]
> Aunque los servicios Web de ASP.NET usan el <xref:System.Xml.Serialization.XmlSerializer> , y el modo de compatibilidad de ASP.net de WCF hace que los servicios WCF imiten el comportamiento de los servicios Web de ASP.net, la opción de compatibilidad de ASP.net no limita uno al uso de <xref:System.Xml.Serialization.XmlSerializer> . Puede seguir utilizándose <xref:System.Runtime.Serialization.DataContractSerializer> con servicios que se ejecutan en el modo de compatibilidad de ASP.NET.

## <a name="service-development"></a>Desarrollo del servicio

Para desarrollar un servicio mediante ASP.NET, lo habitual era agregar el atributo <xref:System.Web.Services.WebService> a una clase, y <xref:System.Web.Services.WebMethodAttribute> a cualquiera de los métodos de esa clase que serán operaciones del servicio:

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

ASP.NET 2.0 introdujo la opción de agregar el atributo <xref:System.Web.Services.WebService> y <xref:System.Web.Services.WebMethodAttribute> a una interfaz en lugar de a una clase, y de escribir una clase para implementar la interfaz:

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

La utilización de esta opción es preferible porque la interfaz con el atributo <xref:System.Web.Services.WebService> constituye un contrato para las operaciones realizadas por el servicio, que puede reutilizarse con diferentes clases que podrían implementar ese mismo contrato de distintas maneras.

Un servicio WCF se proporciona mediante la definición de uno o varios extremos de WCF. Un punto de conexión se define mediante una dirección, un enlace y un contrato de servicio. La dirección define la ubicación del servicio. El enlace especifica cómo comunicar con el servicio. El contrato de servicio define las operaciones que puede realizar el servicio.

Normalmente, primero se define el contrato de servicios agregando <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> a una interfaz:

```csharp
[ServiceContract]
public interface IEcho
{
     [OperationContract]
     string Echo(string input);
}
```

<xref:System.ServiceModel.ServiceContractAttribute>Especifica que la interfaz define un contrato de servicio de WCF y <xref:System.ServiceModel.OperationContractAttribute> que indica que, si existe, de los métodos de la interfaz definen las operaciones del contrato de servicio.

Una vez definido un contrato de servicios, se implementa en una clase, para ello la clase implementa la interfaz que define el contrato de servicios:

```csharp
public class Service : IEcho
{
    public string Echo(string input)
    {
       return input;
    }
}
```

Una clase que implementa un contrato de servicio se conoce como tipo de servicio en WCF.

El paso siguiente es asociar una dirección y un enlace a un tipo de servicio. Normalmente, esto se hace en un archivo de configuración, ya sea editando el archivo directamente o usando un editor de configuración proporcionado con WCF. El siguiente es un ejemplo de archivo de configuración.

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

El enlace especifica el conjunto de protocolos de comunicación con la aplicación. La tabla siguiente enumera los enlaces proporcionados por el sistema que representan las opciones habituales.

|Nombre|Propósito|
|----------|-------------|
|BasicHttpBinding|Interoperabilidad con los servicio y clientes web que admiten WS-BasicProfile 1.1 y Basic Security Profile 1.0.|
|WSHttpBinding|Interoperabilidad con los servicio y clientes web que admiten los protocolos WS-* sobre HTTP.|
|WSDualHttpBinding|Comunicación HTTP dúplex, por la que el receptor de un mensaje inicial no responde directamente al remitente inicial, pero puede transmitir, durante un período de tiempo, cualquier número de respuestas utilizando HTTP de conformidad con los protocolos WS-*.|
|WSFederationBinding|Comunicación HTTP, en la que el acceso a los recursos de un servicio puede controlarse en base a las credenciales emitidas por un proveedor de credenciales identificado explícitamente.|
|NetTcpBinding|Comunicación segura, confiable y de alto rendimiento entre las entidades de software de WCF a través de una red.|
|NetNamedPipeBinding|Comunicación segura, confiable y de alto rendimiento entre las entidades de software de WCF en el mismo equipo.|
|NetMsmqBinding|Comunicación entre las entidades de software de WCF mediante MSMQ.|
|MsmqIntegrationBinding|Comunicación entre una entidad de software de WCF y otra entidad de software mediante MSMQ.|
|NetPeerTcpBinding|Comunicación entre entidades de software WCF mediante el uso de redes punto a punto de Windows.|

El enlace proporcionado por el sistema, <xref:System.ServiceModel.BasicHttpBinding>, incorpora el conjunto de protocolos admitido por los servicios web ASP.NET.

Los enlaces personalizados para aplicaciones WCF se definen fácilmente como colecciones de las clases de elementos de enlace que WCF usa para implementar protocolos individuales. Los nuevos elementos de enlace pueden escribirse para representar los protocolos adicionales.

El comportamiento interno de los tipos de servicio puede ajustarse mediante las propiedades de una familia de clases denominadas comportamientos. Aquí, la clase <xref:System.ServiceModel.ServiceBehaviorAttribute> se utiliza para especificar que el tipo de servicio es multiproceso.

```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple)]
public class DerivativesCalculatorServiceType: IDerivativesCalculator
```

Algunos comportamientos, como <xref:System.ServiceModel.ServiceBehaviorAttribute>, son atributos. Otros, aquellos con las propiedades que desean establecer los administradores, pueden modificarse en la configuración de una aplicación.

A la hora de programar los tipos de servicio, se utiliza con frecuencia la clase <xref:System.ServiceModel.OperationContext>. Su propiedad <xref:System.ServiceModel.OperationContext.Current%2A> estática proporciona acceso a información sobre el contexto en el que una operación se ejecuta. <xref:System.ServiceModel.OperationContext> es similar a las clases <xref:System.Web.HttpContext> y <xref:System.EnterpriseServices.ContextUtil>.

## <a name="hosting"></a>Hospedaje

Los servicios web ASP.NET están compilados en un ensamblado de biblioteca de clases. Se proporciona un archivo, denominado archivo de servicio, que posee la extensión .asmx y contiene una directiva `@ WebService`, que identifica la clase que contiene el código del servicio y el ensamblado en el que se encuentra.

`<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>`

El archivo de servicio se copia en una raíz de la aplicación ASP.NET de Internet Information Services (IIS), y el ensamblado se copia en el subdirectorio \bin de esa raíz de la aplicación. Después, puede accederse a la aplicación mediante el identificador uniforme de recursos (URL) del archivo de servicio de la raíz de la aplicación.

Los servicios WCF se pueden hospedar fácilmente en IIS 5,1 o 6,0, el servicio de activación de procesos de Windows (WAS) que se proporciona como parte de IIS 7,0 y en cualquier aplicación .NET. Para hospedar un servicio en IIS 5.1 ó 6.0, el servicio debe utilizar HTTP como protocolo de transporte de comunicaciones.

Para hospedar un servicio en IIS 5.1, 6.0, o en WAS, realice los pasos siguientes:

1. Compile el tipo de servicio en un ensamblado de biblioteca de clases.

2. Cree un archivo de servicio con una extensión .svc y una directiva `@ ServiceHost` que identifique el tipo de servicio:

    `<%@ServiceHost language="c#" Service="MyService" %>`

3. Copie el archivo de servicio en un directorio virtual, y el ensamblado en el subdirectorio \bin de dicho directorio.

4. Copie el archivo de configuración en el directorio virtual y denomínelo Web.config.

A continuación, puede accederse a la aplicación mediante la dirección URL del archivo de servicio de la raíz de la aplicación.

Para hospedar un servicio WCF en una aplicación .NET, compile el tipo de servicio en un ensamblado de biblioteca de clases al que hace referencia la aplicación y programe la aplicación para hospedar el servicio utilizando la <xref:System.ServiceModel.ServiceHost> clase. El siguiente ejemplo muestra la programación básica requerida:

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

Este ejemplo muestra cómo se especifican las direcciones de uno o más protocolos de transporte en la construcción de <xref:System.ServiceModel.ServiceHost>. Estas direcciones se conocen como direcciones base.

La dirección proporcionada para cualquier extremo de un servicio WCF es una dirección relativa a una dirección base del host del extremo. El host puede contar con una dirección base para cada protocolo de transporte de comunicación. En la configuración de ejemplo del archivo de configuración anterior, el <xref:System.ServiceModel.BasicHttpBinding> seleccionado para el extremo utiliza HTTP como protocolo de transporte, por lo que la dirección del extremo, `EchoService`, es relativa a la dirección base HTTP del host. En el caso del host en el ejemplo anterior, la dirección base HTTP es `http://www.contoso.com:8000/` . Para un servicio hospedado en IIS o WAS, la dirección base es la dirección URL del archivo de servicio del servicio.

Solo los servicios hospedados en IIS o WAS, y que se configuran con HTTP como protocolo de transporte exclusivamente, se pueden establecer para usar la opción de modo de compatibilidad ASP.NET de WCF. Los pasos siguientes son necesarios para activar esa opción.

1. El programador debe agregar el atributo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> al tipo de servicio y especificar que el modo de compatibilidad de ASP.NET está permitido o es necesario.

    ```csharp
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(
          RequirementsMode=AspNetCompatibilityRequirementsMode.Require)]
    public class DerivativesCalculatorServiceType: IDerivativesCalculator
    ```

2. El administrador debe configurar la aplicación para utilizar el modo de compatibilidad de ASP.NET.

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

    Las aplicaciones WCF también se pueden configurar para usar. asmx como extensión para sus archivos de servicio en lugar de. SVC.

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

    Esta opción puede evitar tener que modificar los clientes que están configurados para usar las direcciones URL de los archivos de servicio. asmx al modificar un servicio para usar WCF.

## <a name="client-development"></a>Desarrollo del cliente

Los clientes de los servicios web ASP.NET se generan mediante la herramienta de línea de comandos, WSDL.exe, que proporciona la dirección URL del archivo .asmx como entrada. La herramienta correspondiente proporcionada por WCF es la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Genera un módulo de código con la definición del contrato de servicio y la definición de una clase de cliente de WCF. También genera un archivo de configuración con la dirección y el enlace del servicio.

Generalmente, cuando se programa un cliente de un servicio remoto resulta aconsejable realizar la programación de acuerdo con un patrón asincrónico. El código generado por la herramienta WSDL.exe siempre proporciona, de manera predeterminada, un patrón sincrónico y otro asincrónico. El código generado por la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) puede proporcionar ambos patrones. Proporciona el patrón sincrónico de forma predeterminada. Si se ejecuta la herramienta con el modificador `/async`, el código generado proporciona el patrón asincrónico.

No hay ninguna garantía de que los nombres de las clases de cliente de WCF generadas por ASP. De forma predeterminada, la herramienta WSDL.exe de red coincide con los nombres de las clases de cliente de WCF generadas por la herramienta Svcutil.exe. En concreto, a los nombres de las propiedades de clases que deben serializarse mediante <xref:System.Xml.Serialization.XmlSerializer>, se les asigna, de forma predeterminada, el sufijo Property en el código generado por la herramienta Svcutil.exe, lo que no ocurre en el caso de la herramienta WSDL.exe.

## <a name="message-representation"></a>Representación de mensajes

Los encabezados de los mensajes SOAP enviados y recibidos por los servicios web ASP.NET puede personalizarse. Una clase se deriva de <xref:System.Web.Services.Protocols.SoapHeader> para definir la estructura del encabezado y, a continuación, <xref:System.Web.Services.Protocols.SoapHeaderAttribute> se utiliza para indicar la presencia del mismo.

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

WCF proporciona los atributos,, <xref:System.ServiceModel.MessageContractAttribute> <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute> para describir la estructura de los mensajes SOAP enviados y recibidos por un servicio.

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

Esta sintaxis produce una representación explícita de la estructura de los mensajes, mientras que en el código de un servicio web ASP.NET la estructura de mensajes está implícita. Además, en la sintaxis de ASP.NET, los encabezados de mensaje se representan como propiedades del servicio, como la `ProtocolHeader` propiedad en el ejemplo anterior, mientras que en la sintaxis de WCF, se representan de forma más precisa como propiedades de los mensajes. Además, WCF permite agregar encabezados de mensaje a la configuración de puntos de conexión.

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

Esa opción permite evitar cualquier referencia a los encabezados de protocolo de la infraestructura en el código de un cliente o servicio: los encabezados se agregan a los mensajes debido a cómo se configura el punto de conexión.

## <a name="service-description"></a>Descripción del servicio

Emitir una solicitud GET de HTTP para el archivo .asmx de un servicio web ASP.NET con el WSDL de la consulta, provoca que ASP.NET genere WSDL para describir el servicio. Devuelve ese WSDL como respuesta a la solicitud.

ASP.NET 2.0 permitió validar si un servicio es conforme a Basic Profile 1.1 de Web Services-Interoperability Organization (WS-I), e insertar una notificación informando de que el servicio es conforme a su WSDL. Esto se lleva a cabo utilizando `ConformsTo` y los parámetros `EmitConformanceClaims` del atributo <xref:System.Web.Services.WebServiceBindingAttribute>.

```csharp
[WebService(Namespace = "http://tempuri.org/")]
[WebServiceBinding(
     ConformsTo = WsiProfiles.BasicProfile1_1,
     EmitConformanceClaims=true)]
public interface IEcho
```

Se puede personalizar el WSDL que genera ASP.NET para un servicio. Las personalización se realiza creando una clase derivada de <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension>, para agregar elementos a WSDL.

Emitir una solicitud HTTP GET con el WSDL de la consulta para el archivo. SVC de un servicio WCF con un punto de conexión HTTP hospedado en IIS 51, 6,0 o WAS hace que WCF responda con WSDL para describir el servicio. Establecer httpGetEnabled en true tiene el mismo efecto que enviar una solicitud HTTP GET con el WSDL de la consulta a la dirección base HTTP de un servicio hospedado en una aplicación .NET.

Sin embargo, WCF también responde a las solicitudes de WS-MetadataExchange con WSDL que genera para describir un servicio. Los servicios web ASP.NET no tienen compatibilidad integrada con las solicitudes de WS-MetadataExchange.

El WSDL que genera WCF se puede personalizar exhaustivamente. La clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> proporciona algunas funciones para personalizar el WSDL. WCF también puede configurarse para no generar WSDL, sino para usar un archivo WSDL estático en una dirección URL determinada.

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

## <a name="exception-handling"></a>Control de excepciones

En los servicios web ASP.NET, las excepciones no controladas se devuelven a los clientes como errores de SOAP. También puede iniciar explícitamente instancias de la clase <xref:System.Web.Services.Protocols.SoapException> y tener más control sobre el contenido del error de SOAP que se transmite al cliente.

En los servicios WCF, las excepciones no controladas no se devuelven a los clientes como errores de SOAP para evitar que la información confidencial se exponga accidentalmente a través de las excepciones. Se proporciona un valor de configuración para devolver las excepciones no controladas a los clientes con el propósito de depurarlas.

Para devolver los errores de SOAP a los clientes, puede iniciar las instancias del tipo genérico, <xref:System.ServiceModel.FaultException%601>, utilizando el tipo de contrato de datos como tipo genérico. Además, puede agregar los atributos <xref:System.ServiceModel.FaultContractAttribute> a las operaciones para especificar los errores que podría producir una operación.

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

Con esto, los posibles errores podrían anunciarse en el WSDL del servicio, lo que permitiría a los desarrolladores del cliente anticipar qué errores pueden ser el resultado de una operación, y escribir las instrucciones de captura adecuadas.

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

## <a name="state-management"></a>Administración de estado

La clase utilizada para implementar un servicio web ASP.NET se puede derivar de <xref:System.Web.Services.WebService>.

```csharp
public class Service : WebService, IEcho
{

 public string Echo(string input)
 {
  return input;
 }
}
```

En ese caso, la clase puede programarse para utilizar la propiedad del contexto de la clase base <xref:System.Web.Services.WebService> para tener acceso a un objeto <xref:System.Web.HttpContext>. Se puede utilizar el objeto <xref:System.Web.HttpContext> para actualizar y recuperar información del estado de la aplicación mediante su propiedad Application, y puede utilizarse para actualizar y recuperar información del estado de la sesión utilizando su propiedad Session.

ASP.NET proporciona un control considerable sobre dónde se almacena realmente la información del estado de la sesión a la que se accedió mediante la propiedad Session de <xref:System.Web.HttpContext>. Puede almacenarse en cookies, en una base de datos, en la memoria del servidor actual o en la memoria de un servidor designado. La elección se realiza en el archivo de configuración del servicio.

WCF proporciona objetos extensibles para la administración de Estados. Los objetos extensibles son objetos que implementan <xref:System.ServiceModel.IExtensibleObject%601>. Los objetos extensibles más importantes son <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.InstanceContext>. `ServiceHostBase` permite mantener el estado al que pueden tener acceso todas las instancias de todos los tipos de servicio en el mismo host, mientras que `InstanceContext` permite mantener el estado al que puede tener acceso cualquier código que se ejecute dentro de la misma instancia de un tipo de servicio.

Aquí, el tipo de servicio, `TradingSystem` , tiene un <xref:System.ServiceModel.ServiceBehaviorAttribute> que especifica que todas las llamadas de la misma instancia de cliente de WCF se enrutan a la misma instancia del tipo de servicio.

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class TradingSystem: ITradingService
```

La clase, `DealData`, define el estado al que puede acceder cualquier código que se ejecute en la misma instancia de un tipo de servicio.

```csharp
internal class DealData: IExtension<InstanceContext>
{
 public string DealIdentifier = null;
 public Trade[] Trades = null;
}
```

En el código del tipo de servicio que implementa una de las operaciones del contrato de servicios, se agrega un objeto de estados `DealData` al estado de la instancia actual del tipo de servicio.

```csharp
string ITradingService.BeginDeal()
{
 string dealIdentifier = Guid.NewGuid().ToString();
 DealData state = new DealData(dealIdentifier);
 OperationContext.Current.InstanceContext.Extensions.Add(state);
 return dealIdentifier;
}
```

Después, el código que implementa otras operaciones del contrato de servicio puede recuperar y modificar ese objeto de estados.

```csharp
void ITradingService.AddTrade(Trade trade)
{
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();
 dealData.AddTrade(trade);
}
```

Mientras que ASP.NET proporciona control sobre dónde se almacena realmente la información de estado en la <xref:System.Web.HttpContext> clase, WCF, al menos en su versión inicial, no proporciona ningún control sobre dónde se almacenan los objetos extensibles. Esto constituye la mejor razón para seleccionar el modo de compatibilidad de ASP.NET para un servicio WCF. Si la administración de estados configurable es imperativa, optar por el modo de compatibilidad de ASP.NET permite utilizar las funciones de la clase <xref:System.Web.HttpContext> exactamente igual a como se utilizan en ASP.NET, y, además, configurar dónde se almacena la información gestionada mediante la clase <xref:System.Web.HttpContext>.

## <a name="security"></a>Seguridad

Las opciones para proteger los servicios web ASP.NET son las mismas que para proteger cualquier aplicación IIS. Dado que las aplicaciones WCF pueden hospedarse no solo en IIS, sino también en cualquier archivo ejecutable .NET, las opciones para proteger las aplicaciones WCF deben ser independientes de las funciones de IIS. Sin embargo, las funciones proporcionadas para los servicios Web de ASP.NET también están disponibles para los servicios WCF que se ejecutan en el modo de compatibilidad ASP.NET.

### <a name="security-authentication"></a>Seguridad: autenticación

IIS proporciona funciones para controlar el acceso a las aplicaciones que permiten seleccionar un acceso anónimo, o una variedad de modos de autenticación: autenticación de Windows, autenticación implícita, autenticación básica y autenticación de .NET Passport. La opción de autenticación de Windows puede utilizarse para controlar el acceso a los servicios web ASP.NET. Sin embargo, cuando las aplicaciones WCF se hospedan en IIS, IIS debe configurarse para permitir el acceso anónimo a la aplicación, de modo que la autenticación pueda ser administrada por el propio WCF, que admite la autenticación de Windows entre otras opciones. Las otras opciones integradas incluyen tokens del nombre de usuario, certificados X.509, tokens SAML, y tarjeta CardSpace, aunque también pueden definirse otros mecanismos de autenticación personalizada.

### <a name="security-impersonation"></a>Seguridad: suplantación

ASP.NET proporciona un elemento de identidad por el que un servicio web ASP.NET puede suplantar a un usuario determinado, o a cualquier credencial de usuario proporcionada por la solicitud actual. Ese elemento se puede usar para configurar la suplantación en aplicaciones WCF que se ejecutan en modo de compatibilidad de ASP.NET.

El sistema de configuración de WCF proporciona su propio elemento de identidad para designar un usuario determinado que se va a suplantar. Además, los clientes y servicios de WCF se pueden configurar de forma independiente para la suplantación. Los clientes pueden configurarse para suplantar al usuario actual cuando transmiten las solicitudes.

```xml
<behaviors>
     <behavior name="DerivativesCalculatorClientBehavior">
      <clientCredentials>
      <windows allowedImpersonationLevel="Impersonation"/>
      </clientCredentials>
     </behavior>
</behaviors>
```

Las operaciones del servicio pueden configurarse para suplantar cualquier credencial de usuario proporcionada con la solicitud actual.

```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]
public void Receive(Message input)
```

### <a name="security-authorization-using-access-control-lists"></a>Seguridad: autorización mediante las listas de control de acceso

Las listas de control de acceso (ACL) pueden utilizarse para restringir el acceso a los archivos .asmx. Sin embargo, las ACL en los archivos WCF. SVC se omiten, excepto en el modo de compatibilidad ASP.NET.

### <a name="security-role-based-authorization"></a>Seguridad: autorización basada en funciones

La opción de autenticación de Windows de IIS puede utilizarse, junto con el elemento de autorización proporcionado por el lenguaje de configuración de ASP.NET, para facilitar la autorización basada en las funciones de los servicios web ASP.NET basados en los grupos de Windows a los que están asignados los usuarios. ASP.NET 2.0 introdujo un mecanismo de autorización basado en funciones más general: proveedores de funciones.

Los proveedores de funciones son clases que implementan una interfaz básica para informarse sobre las funciones a las que está asignado un usuario, pero cada proveedor de funciones sabe cómo recuperar esa información desde un origen diferente. ASP.NET 2.0 proporciona un proveedor de funciones que puede recuperar las asignaciones de funciones de una base de datos de Microsoft SQL Server ,y otro que puede recuperar las asignaciones de funciones del administrador de autorización de Windows Server 2003.

El mecanismo de proveedor de roles se puede usar con independencia de ASP.NET en cualquier aplicación .NET, incluida una aplicación WCF. La siguiente configuración de ejemplo para una aplicación WCF muestra cómo el uso de un proveedor de roles ASP.NET es una opción seleccionada por medio de <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .

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

### <a name="security-claims-based-authorization"></a>Seguridad: autorización basada en notificaciones

Una de las innovaciones más importantes de WCF es su compatibilidad exhaustiva para autorizar el acceso a los recursos protegidos en función de las notificaciones. Las notificaciones se componen de un tipo, un derecho y un valor, por ejemplo, el número del permiso de conducir. Realiza un conjunto de notificaciones sobre el portador, una de las cuales es la fecha de nacimiento del portador. El tipo de esa notificación es “fecha de nacimiento”, y el valor de la notificación la fecha de nacimiento del conductor. El derecho que confiere una notificación al portador especifica lo que el portador puede hacer con el valor de la notificación. En el caso de la notificación de la fecha de nacimiento del conductor, el derecho es la posesión: el conductor posee esa fecha de nacimiento pero, por ejemplo, no puede modificarla. La autorización basada en notificaciones engloba a la autorización basada en funciones, ya que las funciones son un tipo de notificación.

La autorización basada en notificaciones finaliza con la comparación de un conjunto de notificaciones con los requisitos de acceso de la operación y, dependiendo del resultado de esa comparación, se otorga o se deniega el acceso a la operación. En WCF, puede especificar una clase para ejecutar la autorización basada en notificaciones, una vez más asignando un valor a la `ServiceAuthorizationManager` propiedad de <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .

```xml
<behaviors>
     <behavior name='ServiceBehavior'>
     <serviceAuthorization
     serviceAuthorizationManagerType=
                   'Service.AccessChecker, Service' />
     </behavior>
</behaviors>
```

Las clases usadas para ejecutar la autorización basada en notificaciones deben derivar de <xref:System.ServiceModel.ServiceAuthorizationManager>, que tiene un solo método para reemplazar, `AccessCheck()`. WCF llama a este método cada vez que se invoca una operación del servicio y proporciona un <xref:System.ServiceModel.OperationContext> objeto, que tiene las notificaciones para el usuario en su `ServiceSecurityContext.AuthorizationContext` propiedad. WCF realiza el trabajo de ensamblar notificaciones sobre el usuario desde cualquier token de seguridad proporcionado por el usuario para la autenticación, lo que deja la tarea de evaluar si esas notificaciones son suficientes para la operación en cuestión.

Que WCF ensambla automáticamente las notificaciones de cualquier tipo de token de seguridad es una innovación muy importante, ya que hace que el código para la autorización se base en las notificaciones completamente independientes del mecanismo de autenticación. Por el contrario, la autorización mediante las ACL o las funciones de ASP.NET está estrechamente vinculada a la autenticación de Windows.

### <a name="security-confidentiality"></a>Seguridad: confidencialidad

La confidencialidad de los mensajes intercambiados con los servicios web de ASP.NET puede protegerse en el nivel de transporte configurando la aplicación de IIS para que utilice el protocolo de transferencia segura de hipertexto (HTTPS). Lo mismo se puede hacer para las aplicaciones WCF hospedadas en IIS. Sin embargo, las aplicaciones WCF hospedadas fuera de IIS también se pueden configurar para usar un protocolo de transporte seguro. Y lo que es más importante, las aplicaciones WCF también se pueden configurar para proteger los mensajes antes de que se transporten, mediante el protocolo WS-Security. Simplemente protegiendo el cuerpo de un mensaje mediante WS-Security, permite su transmisión confidencial a través de intermediarios antes de alcanzar su último destino.

## <a name="globalization"></a>Globalización

El lenguaje de configuración de ASP.NET permite especificar una referencia cultural para los servicios individuales. WCF no admite ese valor de configuración excepto en el modo de compatibilidad de ASP.NET. Para localizar un servicio WCF que no utilice el modo de compatibilidad ASP.NET, compile el tipo de servicio en ensamblados específicos de la referencia cultural y tenga extremos específicos de la referencia cultural independientes para cada ensamblado específico de la referencia cultural.

## <a name="see-also"></a>Vea también

- [Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas](comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
