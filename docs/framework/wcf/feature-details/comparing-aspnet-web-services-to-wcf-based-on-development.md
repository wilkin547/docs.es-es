---
title: "Comparaci&#243;n de los servicios web ASP.NET con el WCF basado en desarrollo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Comparaci&#243;n de los servicios web ASP.NET con el WCF basado en desarrollo
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ofrece una opción de modo de compatibilidad de ASP.NET que permite programar y configurar aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] como servicios web ASP.NET, e imitar su comportamiento.  Las secciones siguientes comparan los servicios web ASP.NET y [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] basado en los requisitos para desarrollar aplicaciones mediante ambas tecnologías.  
  
## Representación de datos  
 Normalmente, el desarrollo de un servicio web con ASP.NET comienza con la definición de todos los tipos de datos complejos que utilizará el servicio.  ASP.NET se basa en <xref:System.Xml.Serialization.XmlSerializer> para traducir los datos representados por los tipos de .NET Framework a XML para la transmisión hacia o desde un servicio, y para traducir los datos recibidos como XML en los objetos de .NET Framework.  La definición de los tipos de datos complejos que utilizará un servicio de ASP.NET requiere la definición de las clases de .NET Framework que <xref:System.Xml.Serialization.XmlSerializer> puede serializar a y desde XML.  Estas clases pueden escribirse manualmente o generarse a partir de las definiciones de los tipos de Esquema XML, mediante la línea de comandos de la utilidad de compatibilidad de tipos de datos de XML, xsd.exe.  
  
 La siguiente lista muestra problemas clave que deben tenerse en cuenta al definir las clases de .NET Framework que <xref:System.Xml.Serialization.XmlSerializer> puede serializar a y desde XML:  
  
-   Solo los campos y propiedades públicas de los objetos de .NET Framework se traducen a XML.  
  
-   Las instancias de las clases de colección solo pueden serializarse a XML si las clases implementan <xref:System.Collections.IEnumerable>, o la interfaz <xref:System.Collections.ICollection>.  
  
-   Las clases que implementan la interfaz <xref:System.Collections.IDictionary>, como <xref:System.Collections.Hashtable>, no pueden serializarse en XML.  
  
-   La gran cantidad de tipos de atributo existente en el espacio de nombres <xref:System.Xml.Serialization>, puede agregarse a una clase de .NET Framework y sus miembros para controlar la representación de las instancias de la clase en XML.  
  
 El desarrollo de aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] normalmente también comienza con la definición de tipos complejos.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede configurarse para usar los mismos tipos de .NET Framework que los servicios web ASP.NET.  
  
 Puede agregarse [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a los tipos de .NET Framework para indicar que las instancias del tipo deben serializarse en XML, y qué campos o propiedades concretas del tipo deben serializarse, como muestra el siguiente código de ejemplo.  
  
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
  
 <xref:System.Runtime.Serialization.DataContractAttribute> significa que cero o más campos o propiedades de un tipo deberán serializarse, mientras que <xref:System.Runtime.Serialization.DataMemberAttribute> indica que se serializará un campo o propiedad concreta.  El atributo <xref:System.Runtime.Serialization.DataContractAttribute> se puede aplicar a una clase o a una estructura.  <xref:System.Runtime.Serialization.DataMemberAttribute> se puede aplicar a un campo o una propiedad, y los campos y propiedades a las que se aplica el atributo pueden ser públicos o privados.  Las instancias de tipos a los que se aplica <xref:System.Runtime.Serialization.DataContractAttribute> se conocen como contratos de datos en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Se serializan en XML mediante <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 La siguiente lista enumera las principales diferencias entre la utilización de <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>, así como los distintos atributos del espacio de nombres <xref:System.Xml.Serialization>.  
  
-   <xref:System.Xml.Serialization.XmlSerializer> y los atributos del espacio de nombres <xref:System.Xml.Serialization> están diseñados para permitir asignar los tipos de .NET Framework a cualquier tipo válido definido en Esquema XML, de modo que ofrecen un control muy preciso de la representación de un tipo en XML.  <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> proporcionan un control muy preciso sobre la representación de un tipo en XML.  Solo pueden especificarse los espacios de nombres y los nombres utilizados para representar el tipo y sus campos, o propiedades en XML, así como la secuencia de aparición en XML de los campos y propiedades:  
  
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
  
     El resto de información sobre la estructura de XML utilizada para representar el tipo .NET está determinada por <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
-   Al no permitir un mayor control sobre la representación de un tipo en XML, el proceso de serialización se vuelve extremadamente predecible para <xref:System.Runtime.Serialization.DataContractSerializer>y, por lo tanto, más fácil de optimizar.  Una ventaja práctica del diseño de <xref:System.Runtime.Serialization.DataContractSerializer> es un mejor rendimiento, aproximadamente un diez por ciento mejor.  
  
-   Los atributos utilizados con <xref:System.Xml.Serialization.XmlSerializer> no indican qué campos o propiedades del tipo se serializan en XML, mientras que <xref:System.Runtime.Serialization.DataMemberAttribute> utilizado con <xref:System.Runtime.Serialization.DataContractSerializer> muestra explícitamente qué campos o propiedades se serializan.  Por consiguiente, los contratos de datos son contratos explícitos de la estructura de datos que una aplicación enviará y recibirá.  
  
-   <xref:System.Xml.Serialization.XmlSerializer> solo puede traducir a XML los miembros públicos de un objeto .NET, <xref:System.Runtime.Serialization.DataContractSerializer> puede traducir a XML los miembros de objetos independientemente de los modificadores de acceso de esos miembros.  
  
-   Como consecuencia de poder serializar en XML los miembros no públicos de tipos, <xref:System.Runtime.Serialization.DataContractSerializer> posee menos restricciones en la variedad de tipos .NET que puede serializar en XML.  En concreto, puede traducir a XML tipos como <xref:System.Collections.Hashtable> que implementa la interfaz <xref:System.Collections.IDictionary>.  Es mucho más probable que <xref:System.Runtime.Serialization.DataContractSerializer> pueda serializar en XML las instancias de cualquiera tipo .NET existentes previamente, sin tener que modificar la definición del tipo o desarrollar un contenedor para él.  
  
-   Otra consecuencia de que <xref:System.Runtime.Serialization.DataContractSerializer> pueda tener acceso a los miembros no públicos de un tipo es que requiere plena confianza, al contrario que <xref:System.Xml.Serialization.XmlSerializer>.  El permiso de acceso al código de plena confianza otorga acceso total a todos los recursos de un equipo al que puede accederse mediante las credenciales con las que se ejecuta el código.  Esta opción debería utilizarse con cuidado ya que el código de plena confianza puede acceder a todos los recursos del equipo.  
  
-   <xref:System.Runtime.Serialization.DataContractSerializer> incorpora cierta compatibilidad para el control de versiones:  
  
    -   <xref:System.Runtime.Serialization.DataMemberAttribute> posee una propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> a la puede asignarse un valor de falso para los miembros que se agregan a las nuevas versiones de un contrato de datos que no se encontraban en versiones anteriores, con lo que las aplicaciones con la versión más reciente del contrato pueden procesar las versiones anteriores.  
  
    -   Cuando un contrato de datos implementa la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>, es posible permitir a <xref:System.Runtime.Serialization.DataContractSerializer> pasar miembros definidos en versiones más recientes de un contrato de datos a través de aplicaciones con versiones anteriores del contrato.  
  
 A pesar de todas las diferencias, el XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, siempre y cuando defina explícitamente el espacio de nombres de XML.  La siguiente clase, que posee atributos que pueden utilizarse con ambos serializadores, se traduce a un XML semánticamente idéntico utilizando <xref:System.Xml.Serialization.XmlSerializer> y <xref:System.Runtime.Serialization.DataContractAttribute>:  
  
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
  
 El kit de desarrollo de software de Windows \(SDK\) incluye una herramienta de línea de comandos denominada [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Al igual que la herramienta xsd.exe utilizada con los servicios web ASP.NET, Svcutil.exe puede generar definiciones de tipos de datos .NET a partir de Esquema XML.  Los tipos son contratos de datos si <xref:System.Runtime.Serialization.DataContractSerializer> puede emitir XML con el formato definido por esquema XML; de lo contrario, están diseñados para serializarse mediante <xref:System.Xml.Serialization.XmlSerializer>.  La herramienta, Svcutil.exe, también puede generar Esquema XML a partir de contratos de datos mediante su modificador `/dataContractOnly`.  
  
> [!NOTE]
>  Aunque los servicios web ASP.NET utilizan <xref:System.Xml.Serialization.XmlSerializer>, y el modo de compatibilidad de ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hace que los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] imiten el comportamiento de los servicios web ASP.NET, la opción de compatibilidad de ASP.NET no limita a la utilización del <xref:System.Xml.Serialization.XmlSerializer>.  Puede seguir utilizándose <xref:System.Runtime.Serialization.DataContractSerializer> con servicios que se ejecutan en el modo de compatibilidad de ASP.NET.  
  
## Desarrollo del servicio  
 Para desarrollar un servicio mediante ASP.NET, lo habitual era agregar el atributo <xref:System.Web.Services.WebService> a una clase, y <xref:System.Web.Services.WebMethodAttribute> a cualquiera de los métodos de esa clase que serán operaciones del servicio:  
  
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
  
 ASP.NET 2.0 introdujo la opción de agregar el atributo <xref:System.Web.Services.WebService> y <xref:System.Web.Services.WebMethodAttribute> a una interfaz en lugar de a una clase, y de escribir una clase para implementar la interfaz:  
  
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
  
 La utilización de esta opción es preferible porque la interfaz con el atributo <xref:System.Web.Services.WebService> constituye un contrato para las operaciones realizadas por el servicio, que puede reutilizarse con diferentes clases que podrían implementar ese mismo contrato de distintas maneras.  
  
 Se puede proporcionar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante la definición de uno o más extremos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Un extremo se define mediante una dirección, un enlace y un contrato de servicio.  La dirección define la ubicación del servicio.  El enlace especifica cómo comunicar con el servicio.  El contrato de servicio define las operaciones que puede realizar el servicio.  
  
 Normalmente, primero se define el contrato de servicios agregando <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> a una interfaz:  
  
```  
[ServiceContract]  
public interface IEcho  
{  
     [OperationContract]  
     string Echo(string input);  
}  
```  
  
 <xref:System.ServiceModel.ServiceContractAttribute> especifica que la interfaz define un contrato del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], y <xref:System.ServiceModel.OperationContractAttribute> indica el método de la interfaz que define las operaciones del contrato de servicios, en caso de que alguno lo haga.  
  
 Una vez definido un contrato de servicios, se implementa en una clase, para ello la clase implementa la interfaz que define el contrato de servicios:  
  
```  
public class Service : IEcho  
{  
    public string Echo(string input)  
    {  
       return input;  
    }  
}  
```  
  
 Una clase que implementa un contrato de servicios se conoce como un tipo de servicio en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 El paso siguiente es asociar una dirección y un enlace a un tipo de servicio.  Generalmente, esto se hace en un archivo de configuración, bien editando directamente el archivo, o utilizando un editor de configuración proporcionado con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  El siguiente es un ejemplo de archivo de configuración.  
  
```  
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
  
 El enlace especifica el conjunto de protocolos de comunicación con la aplicación.  La tabla siguiente enumera los enlaces proporcionados por el sistema que representan las opciones habituales.  
  
|Name|Finalidad|  
|----------|---------------|  
|BasicHttpBinding|Interoperabilidad con los servicio y clientes web que admiten WS\-BasicProfile 1.1 y Basic Security Profile 1.0.|  
|WSHttpBinding|Interoperabilidad con los servicio y clientes web que admiten los protocolos WS\-\* sobre HTTP.|  
|WSDualHttpBinding|Comunicación HTTP dúplex, por la que el receptor de un mensaje inicial no responde directamente al remitente inicial, pero puede transmitir, durante un período de tiempo, cualquier número de respuestas utilizando HTTP de conformidad con los protocolos WS\-\*.|  
|WSFederationBinding|Comunicación HTTP, en la que el acceso a los recursos de un servicio puede controlarse en base a las credenciales emitidas por un proveedor de credenciales identificado explícitamente.|  
|NetTcpBinding|Comunicación segura, de confianza y de alto rendimiento entre las entidades de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de una red.|  
|NetNamedPipeBinding|Comunicación segura, de confianza y de alto rendimiento entre las entidades de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del mismo equipo.|  
|NetMsmqBinding|Comunicación entre las entidades de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizando MSMQ.|  
|MsmqIntegrationBinding|Comunicación entre una entidad de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y otra entidad de software mediante MSMQ.|  
|NetPeerTcpBinding|Comunicación entre las entidades de software [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizando la conexión de red punto a punto de Windows.|  
  
 El enlace proporcionado por el sistema, <xref:System.ServiceModel.BasicHttpBinding>, incorpora el conjunto de protocolos admitido por los servicios web ASP.NET.  
  
 Los enlaces personalizados para aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se definen fácilmente como colecciones de las clases de elementos de enlace que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza para implementar los protocolos individuales.  Los nuevos elementos de enlace pueden escribirse para representar los protocolos adicionales.  
  
 El comportamiento interno de los tipos de servicio puede ajustarse mediante las propiedades de una familia de clases denominadas comportamientos.  Aquí, la clase <xref:System.ServiceModel.ServiceBehaviorAttribute> se utiliza para especificar que el tipo de servicio es multiproceso.  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple]  
public class DerivativesCalculatorServiceType: IDerivativesCalculator  
  
```  
  
 Algunos comportamientos, como <xref:System.ServiceModel.ServiceBehaviorAttribute>, son atributos.  Otros, aquellos con las propiedades que desean establecer los administradores, pueden modificarse en la configuración de una aplicación.  
  
 A la hora de programar los tipos de servicio, se utiliza con frecuencia la clase <xref:System.ServiceModel.OperationContext>.  Su propiedad <xref:System.ServiceModel.OperationContext.Current%2A> estática proporciona acceso a información sobre el contexto en el que una operación se ejecuta.  <xref:System.ServiceModel.OperationContext> es similar a las clases <xref:System.Web.HttpContext> y <xref:System.EnterpriseServices.ContextUtil>.  
  
## Hospedaje  
 Los servicios web ASP.NET están compilados en un ensamblado de biblioteca de clases.  Se proporciona un archivo, denominado archivo de servicio, que posee la extensión .asmx y contiene una directiva `@ WebService`, que identifica la clase que contiene el código del servicio y el ensamblado en el que se encuentra.  
  
```  
<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>  
```  
  
 El archivo de servicio se copia en una raíz de la aplicación ASP.NET de Internet Information Services \(IIS\), y el ensamblado se copia en el subdirectorio \\bin de esa raíz de la aplicación.  Después, puede accederse a la aplicación mediante el identificador uniforme de recursos \(URL\) del archivo de servicio de la raíz de la aplicación.  
  
 Los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se pueden hospedar fácilmente en IIS 5.1 ó 6.0, el servicio de activación de procesos de Windows \(WAS\) que se proporciona junto con IIS 7.0, y en cualquier aplicación .NET.  Para hospedar un servicio en IIS 5.1 ó 6.0, el servicio debe utilizar HTTP como protocolo de transporte de comunicaciones.  
  
 Para hospedar un servicio en IIS 5.1, 6.0, o en WAS, realice los pasos siguientes:  
  
1.  Compile el tipo de servicio en un ensamblado de biblioteca de clases.  
  
2.  Cree un archivo de servicio con una extensión .svc y una directiva `@ ServiceHost` que identifique el tipo de servicio:  
  
    ```  
    <%@ServiceHost language=”c#” Service="MyService" %>  
    ```  
  
3.  Copie el archivo de servicio en un directorio virtual, y el ensamblado en el subdirectorio \\bin de dicho directorio.  
  
4.  Copie el archivo de configuración en el directorio virtual y denomínelo Web.config.  
  
 A continuación, puede accederse a la aplicación mediante la dirección URL del archivo de servicio de la raíz de la aplicación.  
  
 Para hospedar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en una aplicación .NET, compile el tipo de servicio en un ensamblado de biblioteca de clases a la que haga referencia la aplicación, y programe la aplicación para que hospede el servicio utilizando la clase <xref:System.ServiceModel.ServiceHost>.  El siguiente ejemplo muestra la programación básica requerida:  
  
```  
string httpBaseAddress = "http://www.contoso.com:8000/";  
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";  
  
Uri httpBaseAddressUri = new Uri(httpBaseAddress);  
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);  
  
Uri[] baseAdresses = new Uri[] {   
 httpBaseAddressUri,  
 tcpBaseAddressUri};  
  
using(ServiceHost host = new ServiceHost(  
typeof(Service), //”Service” is the name of the service type baseAdresses))  
{  
     host.Open();  
  
     […] //Wait to receive messages  
     host.Close();  
}  
```  
  
 Este ejemplo muestra cómo se especifican las direcciones de uno o más protocolos de transporte en la construcción de <xref:System.ServiceModel.ServiceHost>.  Estas direcciones se conocen como direcciones base.  
  
 La dirección proporcionada para cualquier extremo de un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está relacionada con la dirección base del host del extremo.  El host puede contar con una dirección base para cada protocolo de transporte de comunicación.  En la configuración de ejemplo del archivo de configuración anterior, el <xref:System.ServiceModel.BasicHttpBinding> seleccionado para el extremo utiliza HTTP como protocolo de transporte, por lo que la dirección del extremo, `EchoService`, es relativa a la dirección base HTTP del host.  En el caso del host del ejemplo anterior, la dirección base HTTP es http:\/\/www.contoso.com:8000\/.  Para un servicio hospedado en IIS o WAS, la dirección base es la dirección URL del archivo de servicio del servicio.  
  
 Solo los servicios hospedados en IIS o WAS, y configurados exclusivamente con HTTP como protocolo de transporte, pueden configurarse para utilizar la opción de modo de compatibilidad de ASP.NET de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Los pasos siguientes son necesarios para activar esa opción.  
  
1.  El programador debe agregar el atributo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> al tipo de servicio y especificar que el modo de compatibilidad de ASP.NET está permitido o es necesario.  
  
    ```  
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(  
          RequirementsMode=AspNetCompatbilityRequirementsMode.Require)]  
    public class DerivativesCalculatorServiceType: IDerivativesCalculator  
    ```  
  
2.  El administrador debe configurar la aplicación para utilizar el modo de compatibilidad de ASP.NET.  
  
    ```  
    <configuration>  
         <system.serviceModel>  
          <services>  
          […]  
          </services>  
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     Las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también pueden configurarse para utilizar .asmx como extensión de sus archivos de servicio en lugar de .svc.  
  
    ```  
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
  
     Esa opción puede evitarle tener que modificar clientes configurados para utilizar las direcciones URL de archivos de servicio .asmx, cuando modifique un servicio para utilizar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Desarrollo del cliente  
 Los clientes de los servicios web ASP.NET se generan mediante la herramienta de línea de comandos, WSDL.exe, que proporciona la dirección URL del archivo .asmx como entrada.  La herramienta correspondiente proporcionada por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  Genera un módulo de código con la definición del contrato de servicios y la definición de una clase de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  También genera un archivo de configuración con la dirección y el enlace del servicio.  
  
 Generalmente, cuando se programa un cliente de un servicio remoto resulta aconsejable realizar la programación de acuerdo con un patrón asincrónico.  El código generado por la herramienta WSDL.exe siempre proporciona, de manera predeterminada, un patrón sincrónico y otro asincrónico.  El código generado por [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) puede proporcionar cualquier modelo.  Proporciona el patrón sincrónico de forma predeterminada.  Si se ejecuta la herramienta con el modificador `/async`, el código generado proporciona el patrón asincrónico.  
  
 No existe garantía de que los nombres en las clases de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generadas, de forma predeterminada, por la herramienta WSDL.exe de ASP.NET coincidan con los nombres en las clases de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generadas por la herramienta Svcutil.exe.  En concreto, a los nombres de las propiedades de clases que deben serializarse mediante <xref:System.Xml.Serialization.XmlSerializer>, se les asigna, de forma predeterminada, el sufijo Property en el código generado por la herramienta Svcutil.exe, lo que no ocurre en el caso de la herramienta WSDL.exe.  
  
## Representación de mensajes  
 Los encabezados de los mensajes SOAP enviados y recibidos por los servicios web ASP.NET puede personalizarse.  Una clase se deriva de <xref:System.Web.Services.Protocols.SoapHeader> para definir la estructura del encabezado y, a continuación, <xref:System.Web.Services.Protocols.SoapHeaderAttribute> se utiliza para indicar la presencia del mismo.  
  
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
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona los atributos, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>y <xref:System.ServiceModel.MessageBodyMemberAttribute> para describir la estructura de los mensajes SOAP enviados y recibidos por un servicio.  
  
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
  
 Esta sintaxis produce una representación explícita de la estructura de los mensajes, mientras que en el código de un servicio web ASP.NET la estructura de mensajes está implícita.  Además, en la sintaxis ASP.NET, los encabezados del mensaje se representan como propiedades del servicio, como la propiedad `ProtocolHeader` en el ejemplo anterior, mientras que en la sintaxis [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se representan con más precisión, como propiedades de mensajes.  Asimismo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite agregar los encabezados del mensaje a la configuración de extremos.  
  
```  
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
  
 Esa opción permite evitar cualquier referencia a los encabezados de protocolo de la infraestructura en el código de un cliente o servicio: los encabezados se agregan a los mensajes debido a cómo se configura el extremo.  
  
## Descripción del servicio  
 Emitir una solicitud GET de HTTP para el archivo .asmx de un servicio web ASP.NET con el WSDL de la consulta, provoca que ASP.NET genere WSDL para describir el servicio.  Devuelve ese WSDL como respuesta a la solicitud.  
  
 ASP.NET 2.0 permitió validar si un servicio es conforme a Basic Profile 1.1 de Web Services\-Interoperability Organization \(WS\-I\), e insertar una notificación informando de que el servicio es conforme a su WSDL.  Esto se lleva a cabo utilizando `ConformsTo` y los parámetros `EmitConformanceClaims` del atributo <xref:System.Web.Services.WebServiceBindingAttribute>.  
  
```  
  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Se puede personalizar el WSDL que genera ASP.NET para un servicio.  Las personalización se realiza creando una clase derivada de <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension>, para agregar elementos a WSDL.  
  
 La emisión de una solicitud GET de HTTP con el WSDL de la consulta para el archivo .svc de un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], con un extremo HTTP hospedado en IIS 51, 6.0 o WAS, da lugar a que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responda con WSDL para describir el servicio.  Establecer httpGetEnabled en true tiene el mismo efecto que enviar una solicitud HTTP GET con el WSDL de la consulta a la dirección base HTTP de un servicio hospedado en una aplicación .NET.  
  
 Sin embargo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también responde a las solicitudes de WS\-MetadataExchange con el WSDL que genera para describir un servicio.  Los servicios web ASP.NET no tienen compatibilidad integrada con las solicitudes de WS\-MetadataExchange.  
  
 Se puede personalizar ampliamente el WSDL que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera.  La clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> proporciona algunas funciones para personalizar el WSDL.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también puede configurarse para no generar WSDL, sino usar un archivo WSDL estático en una dirección URL determinada.  
  
```  
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
  
## Control de excepciones  
 En los servicios web ASP.NET, las excepciones no controladas se devuelven a los clientes como errores de SOAP.  También puede iniciar explícitamente instancias de la clase <xref:System.Web.Services.Protocols.SoapException> y tener más control sobre el contenido del error de SOAP que se transmite al cliente.  
  
 En servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las excepciones no controladas no se devuelven a los clientes como errores de SOAP para evitar la exposición involuntaria de información confidencial a través de las excepciones.  Se proporciona un valor de configuración para devolver las excepciones no controladas a los clientes con el propósito de depurarlas.  
  
 Para devolver los errores de SOAP a los clientes, puede iniciar las instancias del tipo genérico, <xref:System.ServiceModel.FaultException%601>, utilizando el tipo de contrato de datos como tipo genérico.  Además, puede agregar los atributos <xref:System.ServiceModel.FaultContractAttribute> a las operaciones para especificar los errores que podría producir una operación.  
  
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
  
 Con esto, los posibles errores podrían anunciarse en el WSDL del servicio, lo que permitiría a los desarrolladores del cliente anticipar qué errores pueden ser el resultado de una operación, y escribir las instrucciones de captura adecuadas.  
  
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
  
## Administración de estado  
 La clase utilizada para implementar un servicio web ASP.NET se puede derivar de <xref:System.Web.Services.WebService>.  
  
```  
public class Service : WebService, IEcho  
{  
  
 public string Echo(string input)  
 {  
  return input;  
 }  
}  
```  
  
 En ese caso, la clase puede programarse para utilizar la propiedad del contexto de la clase base <xref:System.Web.Services.WebService> para tener acceso a un objeto <xref:System.Web.HttpContext>.  Se puede utilizar el objeto <xref:System.Web.HttpContext> para actualizar y recuperar información del estado de la aplicación mediante su propiedad Application, y puede utilizarse para actualizar y recuperar información del estado de la sesión utilizando su propiedad Session.  
  
 ASP.NET proporciona un control considerable sobre dónde se almacena realmente la información del estado de la sesión a la que se accedió mediante la propiedad Session de <xref:System.Web.HttpContext>.  Puede almacenarse en cookies, en una base de datos, en la memoria del servidor actual o en la memoria de un servidor designado.  La elección se realiza en el archivo de configuración del servicio.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona objetos extensibles para la administración de estados.  Los objetos extensibles son objetos que implementan <xref:System.ServiceModel.IExtensibleObject%601>.  Los objetos extensibles más importantes son <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.InstanceContext>.  `ServiceHostBase` permite mantener el estado al que pueden tener acceso todas las instancias de todos los tipos de servicio en el mismo host, mientras que `InstanceContext` permite mantener el estado al que puede tener acceso cualquier código que se ejecute dentro de la misma instancia de un tipo de servicio.  
  
 Aquí, el tipo de servicio, `TradingSystem`, tiene un <xref:System.ServiceModel.ServiceBehaviorAttribute> que especifica que todas las llamadas desde la misma instancia de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se enruten a la misma instancia del tipo de servicio.  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class TradingSystem: ITradingService  
```  
  
 La clase, `DealData`, define el estado al que puede acceder cualquier código que se ejecute en la misma instancia de un tipo de servicio.  
  
```  
internal class DealData: IExtension<InstanceContext>  
{  
 public string DealIdentifier = null;  
 public Trade[] Trades = null;  
}  
```  
  
 En el código del tipo de servicio que implementa una de las operaciones del contrato de servicios, se agrega un objeto de estados `DealData` al estado de la instancia actual del tipo de servicio.  
  
```  
string ITradingService.BeginDeal()  
{  
 string dealIdentifier = Guid.NewGuid().ToString();  
 DealData state = new DealData(dealIdentifier);  
 OperationContext.Current.InstanceContext.Extensions.Add(state);  
 return dealIdentifier;  
}  
```  
  
 Después, el código que implementa otras operaciones del contrato de servicio puede recuperar y modificar ese objeto de estados.  
  
```  
void ITradingService.AddTrade(Trade trade)  
{  
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();  
 dealData.AddTrade(trade);  
}  
```  
  
 Mientras que ASP.NET permite controlar dónde se almacena realmente la información de estado en la clase <xref:System.Web.HttpContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], al menos en su versión inicial, no proporciona ningún control sobre dónde se almacenan los objetos extensibles.  Eso constituye la mejor razón para seleccionar el modo de compatibilidad de ASP.NET para un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Si la administración de estados configurable es imperativa, optar por el modo de compatibilidad de ASP.NET permite utilizar las funciones de la clase <xref:System.Web.HttpContext> exactamente igual a como se utilizan en ASP.NET, y, además, configurar dónde se almacena la información gestionada mediante la clase <xref:System.Web.HttpContext>.  
  
## Seguridad  
 Las opciones para proteger los servicios web ASP.NET son las mismas que para proteger cualquier aplicación IIS.  Dado que las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no solo pueden hospedarse en IIS sino también en cualquier ejecutable de .NET, las opciones para proteger las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deben ser independientes de las funciones de IIS.  No obstante, las funciones proporcionadas para los servicios web ASP.NET también están disponibles para los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en modo de compatibilidad de ASP.NET.  
  
### Seguridad: autenticación  
 IIS proporciona funciones para controlar el acceso a las aplicaciones que permiten seleccionar un acceso anónimo, o una variedad de modos de autenticación: autenticación de Windows, autenticación implícita, autenticación básica y autenticación de .NET Passport.  La opción de autenticación de Windows puede utilizarse para controlar el acceso a los servicios web ASP.NET.  Sin embargo, cuando las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se hospedan en IIS, IIS debe configurarse para permitir el acceso anónimo a la aplicación, de modo que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede administrar la autenticación, lo que, entre otras opciones, es compatible con la autenticación de Windows.  Las otras opciones integradas incluyen tokens del nombre de usuario, certificados X.509, tokens SAML, y tarjeta CardSpace, aunque también pueden definirse otros mecanismos de autenticación personalizada.  
  
### Seguridad: suplantación  
 ASP.NET proporciona un elemento de identidad por el que un servicio web ASP.NET puede suplantar a un usuario determinado, o a cualquier credencial de usuario proporcionada por la solicitud actual.  Ese elemento puede utilizarse para configurar la suplantación en aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en modo de compatibilidad de ASP.NET.  
  
 El sistema de configuración [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona su propio elemento de identidad para designar al usuario concreto que se suplanta.  Además, los clientes y servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden configurarse de manera independiente para la suplantación.  Los clientes pueden configurarse para suplantar al usuario actual cuando transmiten las solicitudes.  
  
```  
<behaviors>  
     <behavior name="DerivativesCalculatorClientBehavior">  
      <clientCredentials>  
      <windows allowedImpersonationLevel="Impersonation"/>  
      </clientCredentials>  
     </behavior>  
</behaviors>  
```  
  
 Las operaciones del servicio pueden configurarse para suplantar cualquier credencial de usuario proporcionada con la solicitud actual.  
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public void Receive(Message input)  
```  
  
### Seguridad: autorización mediante las listas de control de acceso  
 Las listas de control de acceso \(ACL\) pueden utilizarse para restringir el acceso a los archivos .asmx.  Sin embargo, las ACL de los archivos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].svc se omiten excepto en el modo de compatibilidad de ASP.NET.  
  
### Seguridad: autorización basada en funciones  
 La opción de autenticación de Windows de IIS puede utilizarse, junto con el elemento de autorización proporcionado por el lenguaje de configuración de ASP.NET, para facilitar la autorización basada en las funciones de los servicios web ASP.NET basados en los grupos de Windows a los que están asignados los usuarios.  ASP.NET 2.0 introdujo un mecanismo de autorización basado en funciones más general: proveedores de funciones.  
  
 Los proveedores de funciones son clases que implementan una interfaz básica para informarse sobre las funciones a las que está asignado un usuario, pero cada proveedor de funciones sabe cómo recuperar esa información desde un origen diferente.  ASP.NET 2.0 proporciona un proveedor de funciones que puede recuperar las asignaciones de funciones de una base de datos de Microsoft SQL Server ,y otro que puede recuperar las asignaciones de funciones del administrador de autorización de Windows Server 2003.  
  
 El mecanismo del proveedor de funciones puede utilizarse de manera independiente de ASP.NET en cualquier aplicación de .NET, incluso una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  La siguiente configuración de ejemplo para una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] muestra cómo el uso de un proveedor de roles de ASP.NET es una opción seleccionada mediante <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.  
  
```  
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
  
### Seguridad: autorización basada en notificaciones  
 Una de las innovaciones más importantes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es su compatibilidad para autorizar el acceso a los recursos protegidos basándose en notificaciones.  Las notificaciones se componen de un tipo, un derecho y un valor, por ejemplo, el número del permiso de conducir.  Realiza un conjunto de notificaciones sobre el portador, una de las cuales es la fecha de nacimiento del portador.  El tipo de esa notificación es “fecha de nacimiento”, y el valor de la notificación la fecha de nacimiento del conductor.  El derecho que confiere una notificación al portador especifica lo que el portador puede hacer con el valor de la notificación.  En el caso de la notificación de la fecha de nacimiento del conductor, el derecho es la posesión: el conductor posee esa fecha de nacimiento pero, por ejemplo, no puede modificarla.  La autorización basada en notificaciones engloba a la autorización basada en funciones, ya que las funciones son un tipo de notificación.  
  
 La autorización basada en notificaciones finaliza con la comparación de un conjunto de notificaciones con los requisitos de acceso de la operación y, dependiendo del resultado de esa comparación, se otorga o se deniega el acceso a la operación.  En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], puede especificar una clase para ejecutar la autorización basada en notificaciones, una vez más asignando un valor a la propiedad `ServiceAuthorizationManager` de <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.  
  
```  
<behaviors>  
     <behavior name='ServiceBehavior'>  
     <serviceAuthorization   
     serviceAuthorizationManagerType=  
                   'Service.AccessChecker, Service' />  
     </behavior>  
</behaviors>  
```  
  
 Las clases usadas para ejecutar la autorización basada en notificaciones deben derivar de <xref:System.ServiceModel.ServiceAuthorizationManager>, que tiene un solo método para reemplazar, `AccessCheck()`.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] llama a ese método siempre que se invoca una operación del servicio y proporciona un objeto <xref:System.ServiceModel.OperationContext>, que tiene las notificaciones para el usuario en su propiedad `ServiceSecurityContext.AuthorizationContext`.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ensambla las notificaciones sobre el usuario del token de seguridad suministrado por el usuario para la autenticación, que deja la tarea de evaluar si esas notificaciones son suficientes para la operación en cuestión.  
  
 Que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ensamble automáticamente las notificaciones de cualquier tipo de token de seguridad es una innovación muy significativa, ya que independiza totalmente el código para la autorización basada en notificaciones del mecanismo de autenticación.  Por el contrario, la autorización mediante las ACL o las funciones de ASP.NET está estrechamente vinculada a la autenticación de Windows.  
  
### Seguridad: confidencialidad  
 La confidencialidad de los mensajes intercambiados con los servicios web de ASP.NET puede protegerse en el nivel de transporte configurando la aplicación de IIS para que utilice el protocolo de transferencia segura de hipertexto \(HTTPS\).  Esto mismo puede hacerse con las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedadas en IIS.  No obstante, las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedadas fuera de IIS también pueden configurarse para que utilicen un protocolo de transporte seguro.  Lo que es más importante, las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también pueden configurarse para proteger los mensajes antes de su transportarse, mediante el protocolo WS\-Security.  Simplemente protegiendo el cuerpo de un mensaje mediante WS\-Security, permite su transmisión confidencial a través de intermediarios antes de alcanzar su último destino.  
  
## Globalización  
 El lenguaje de configuración de ASP.NET permite especificar una referencia cultural para los servicios individuales.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no es compatible con ese valor de configuración excepto en el modo de compatibilidad de ASP.NET.  Para adaptar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que no utiliza el modo de compatibilidad de ASP.NET, compile el tipo de servicio en los ensamblados específicos de la referencia cultural, y defina extremos específicos de la referencia cultural independientes para cada ensamblado específico de la referencia cultural.  
  
## Vea también  
 [Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)