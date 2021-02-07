---
description: 'Más información sobre: Introducción a la creación de puntos de conexión'
title: Información general acerca de la creación de puntos finales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: ff806428922f2097f0d570118d6b5f7836c1797b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756830"
---
# <a name="endpoint-creation-overview"></a>Información general acerca de la creación de puntos finales

Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de los *extremos* del servicio. Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF. Esta sección describe la estructura de un punto de conexión, y detalla cómo definir un punto de conexión en la configuración y el código.

## <a name="the-structure-of-an-endpoint"></a>Estructura de un extremo

Cada punto de conexión contiene una dirección que indica dónde se encuentra el punto de conexión, un enlace que especifica cómo puede comunicarse un cliente con el punto de conexión, y un contrato que identifica los métodos disponibles.

- **Dirección**. La dirección identifica únicamente el punto de conexión e indica a los consumidores potenciales dónde se ubica el servicio. Se representa en el modelo de objetos WCF mediante la <xref:System.ServiceModel.EndpointAddress> dirección, que contiene un identificador uniforme de recursos (URI) y propiedades de dirección que incluyen una identidad, algunos elementos del lenguaje de descripción de servicios web (WSDL) y una colección de encabezados opcionales. Los encabezados opcionales proporcionan información de direccionamiento adicional para identificar o interactuar con el punto de conexión. Para obtener más información, vea [especificar una dirección de extremo](specifying-an-endpoint-address.md).

- **Enlace**. El enlace especifica cómo comunicarse con el punto de conexión. El enlace especifica cómo se comunica el punto de conexión con el mundo, incluido el protocolo de transporte que utiliza (por ejemplo, TCP o HTTP), la codificación utilizada en los mensajes (por ejemplo, texto o binario) y los requisitos de seguridad necesarios (por ejemplo, capa de sockets seguros [SSL] o seguridad del mensaje SOAP). Para obtener más información, consulte [uso de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md).

- **Contrato de servicio**. El contrato de servicios describe qué funcionalidad expone el extremo al cliente. Un contrato especifica las operaciones a las que puede llamar un cliente, la forma del mensaje y el tipo de parámetros de entrada o los datos necesarios para llamar a la operación, así como el tipo de mensaje de procesamiento o respuesta que puede esperar el cliente. Existen tres tipos básicos de contratos que se corresponden con los patrones de intercambio de mensajes básicos (MEP): datagrama (unidireccional), solicitud/respuesta y dúplex (bidireccional). El contrato de servicio también puede emplear contratos de datos y mensajes para exigir tipos de datos y formatos de mensaje específicos cuando se obtiene acceso. Para obtener más información sobre cómo definir un contrato de servicios, consulte [diseño de contratos](designing-service-contracts.md)de servicio. Tenga en cuenta que también pueden exigírsele a un cliente que implemente un contrato definido por servicio, denominado un contrato de devolución de llamada, para recibir los mensajes del servicio en un MEP dúplex. Para obtener más información, vea [servicios dúplex](./feature-details/duplex-services.md).

El punto de conexión de un servicio puede especificarse de manera imperativa, mediante el código, o de manera declarativa a través de la configuración. Si no se especifica ningún extremo, el tiempo de ejecución proporciona extremos predeterminados, agregando uno para cada dirección base de cada contrato de servicio implementado por el servicio. Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio. Generalmente, es más práctico definir extremos de servicio mediante la configuración en lugar del código. Mantener la información del enlace y el direccionamiento fuera del código les permite cambiar sin tener que recompilar e implementar la aplicación.

> [!NOTE]
> Cuando se agrega un extremo de servicio que realiza la suplantación, debe utilizarse uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>, o el método <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> para cargar correctamente el contrato en un nuevo objeto <xref:System.ServiceModel.Description.ServiceDescription>.

## <a name="defining-endpoints-in-code"></a>Definir los extremos en código

El siguiente ejemplo muestra cómo especificar un extremo en código:

- Defina un contrato para un `IEcho` tipo de servicio que acepte el nombre de alguien y echo con la respuesta "Hello \<name> !".

- Implemente un servicio `Echo` del tipo definido por el contrato `IEcho`.

- Especifique una dirección de extremo de `http://localhost:8000/Echo` para el servicio.

- Configure el servicio `Echo` mediante un enlace <xref:System.ServiceModel.WSHttpBinding>.

```csharp
namespace Echo
{
   // Define the contract for the IEcho service
   [ServiceContract]
   public interface IEcho
   {
       [OperationContract]
       String Hello(string name)
   }

   // Create an Echo service that implements IEcho contract
   class Echo : IEcho
   {
      public string Hello(string name)
      {
         return "Hello" + name + "!";
      }
      public static void Main ()
      {
          //Specify the base address for Echo service.
          Uri echoUri = new Uri("http://localhost:8000/");

          //Create a ServiceHost for the Echo service.
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);

          // Use a predefined WSHttpBinding to configure the service.
          WSHttpBinding binding = new WSHttpBinding();

          // Add the endpoint for this service to the service host.
          serviceHost.AddServiceEndpoint(
             typeof(IEcho),
             binding,
             echoUri
           );

          // Open the service host to run it.
          serviceHost.Open();
     }
  }
}
```

```vb
' Define the contract for the IEcho service
    <ServiceContract()> _
    Public Interface IEcho
        <OperationContract()> _
        Function Hello(ByVal name As String) As String
    End Interface

' Create an Echo service that implements IEcho contract
    Public Class Echo
        Implements IEcho
        Public Function Hello(ByVal name As String) As String _
 Implements ICalculator.Hello
            Dim result As String = "Hello" + name + "!"
            Return result
        End Function

' Specify the base address for Echo service.
Dim echoUri As Uri = New Uri("http://localhost:8000/")

' Create a ServiceHost for the Echo service.
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)

' Use a predefined WSHttpBinding to configure the service.
Dim binding As New WSHttpBinding()

' Add the endpoint for this service to the service host.
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)

' Open the service host to run it.
serviceHost.Open()
```

> [!NOTE]
> El host del servicio se crea con una dirección base y, a continuación, se especifica el resto de la dirección, relacionada con la dirección base, como parte de un extremo. Esta subdivisión de la dirección permite definir varios extremos de manera más conveniente para los servicios de un host.

> [!NOTE]
> Las propiedades de <xref:System.ServiceModel.Description.ServiceDescription> en la aplicación de servicio no deben modificarse después del método <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ServiceHostBase>. Algunos miembros, como la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> y los métodos `AddServiceEndpoint` en <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.ServiceHost>, inician una excepción si se modifican pasado ese punto. Otros permiten modificarlos, pero el resultado no está definido.
>
> De igual forma, en el cliente no se deben modificar los valores <xref:System.ServiceModel.Description.ServiceEndpoint> después de la llamada a <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ChannelFactory>. La propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A> inicia una excepción si se modifican pasado ese punto. Los otros valores de descripción del cliente pueden modificarse sin el error, pero el resultado no está definido.
>
> Tanto si es para el servicio como para el cliente, se recomienda modificar la descripción antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.

## <a name="defining-endpoints-in-configuration"></a>Definir los puntos de conexión en configuración

Con frecuencia al crear una aplicación se desea delegar las decisiones al administrador que está implementando la aplicación. Por ejemplo, es habitual que no pueda saberse de antemano cuál será la dirección de servicio (una URI). En lugar de incluir una dirección en el código, es preferible permitir a un administrador hacerlo después de crear un servicio. Esta flexibilidad se logra a través de la configuración. Para obtener más información, vea [configuración de servicios](configuring-services.md).

> [!NOTE]
> Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) con el modificador nombre de archivo `/config:`  `[,`  `]` para crear rápidamente archivos de configuración.

## <a name="using-default-endpoints"></a>Usar puntos de conexión predeterminados

Si no se especifica ningún extremo en el código ni en la configuración, el tiempo de ejecución proporciona extremos predeterminados, agregando uno para cada dirección base de cada contrato de servicio implementado por el servicio. La dirección base se puede especificar en el código o en la configuración, y los extremos predeterminados se agregan al llamar al método <xref:System.ServiceModel.ICommunicationObject.Open> en el objeto <xref:System.ServiceModel.ServiceHost>. Este ejemplo es el mismo que el de la sección anterior, pero como no se han especificado puntos de conexión, se agregan los predeterminados.

```csharp
namespace Echo
{
   // Define the contract for the IEcho service
   [ServiceContract]
   public interface IEcho
   {
       [OperationContract]
       String Hello(string name)
   }

   // Create an Echo service that implements IEcho contract
   public class Echo : IEcho
   {
      public string Hello(string name)
      {
         return "Hello" + name + "!";
      }
      public static void Main ()
      {
          //Specify the base address for Echo service.
          Uri echoUri = new Uri("http://localhost:8000/");

          //Create a ServiceHost for the Echo service.
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);

          // Open the service host to run it. Default endpoints
          // are added when the service is opened.
          serviceHost.Open();
     }
  }
}
```

```vb
' Define the contract for the IEcho service
    <ServiceContract()> _
    Public Interface IEcho
        <OperationContract()> _
        Function Hello(ByVal name As String) As String
    End Interface

' Create an Echo service that implements IEcho contract
    Public Class Echo
        Implements IEcho
        Public Function Hello(ByVal name As String) As String _
 Implements ICalculator.Hello
            Dim result As String = "Hello" + name + "!"
            Return result
        End Function

' Specify the base address for Echo service.
Dim echoUri As Uri = New Uri("http://localhost:8000/")

' Open the service host to run it. Default endpoints
' are added when the service is opened.
serviceHost.Open()
```

 Si se proporcionan puntos de conexión de forma explícita, es posible agregar puntos de conexión predeterminados llamando a <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> en el objeto <xref:System.ServiceModel.ServiceHost> antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. Para obtener más información sobre los puntos de conexión predeterminados, vea [configuración simplificada](simplified-configuration.md) y [configuración simplificada para servicios WCF](./samples/simplified-configuration-for-wcf-services.md).

## <a name="see-also"></a>Vea también

- [Implementación de contratos de servicio](implementing-service-contracts.md)
