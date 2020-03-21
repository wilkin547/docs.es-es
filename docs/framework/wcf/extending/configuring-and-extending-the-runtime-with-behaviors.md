---
title: Configuración y extensión del tiempo de ejecución con comportamientos
ms.date: 03/30/2017
helpviewer_keywords:
- attaching extensions using behaviors [WCF]
ms.assetid: 149b99b6-6eb6-4f45-be22-c967279677d9
ms.openlocfilehash: 67db06649d6059ff6b6e6fb8d84058621fcc7dab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185655"
---
# <a name="configuring-and-extending-the-runtime-with-behaviors"></a>Configuración y extensión del tiempo de ejecución con comportamientos
Los comportamientos permiten modificar el comportamiento predeterminado y agregar extensiones personalizadas que inspeccionan y validan la configuración del servicio o modifican el comportamiento en tiempo de ejecución en aplicaciones cliente y de servicio de Windows Communication Foundation (WCF). En este tema se describen las interfaces de comportamiento, cómo implementarlas y cómo agregarlas mediante programación a la descripción del servicio (en una aplicación de servicio) o punto de conexión (en una aplicación cliente) o en un archivo de configuración. Para obtener más información sobre el uso de comportamientos proporcionados por el sistema, vea Especificar el comportamiento en tiempo de [ejecución](../specifying-service-run-time-behavior.md) del servicio y Especificar el comportamiento en tiempo de ejecución del [cliente](../specifying-client-run-time-behavior.md).  
  
## <a name="behaviors"></a>Comportamientos  
 Los tipos de comportamiento se agregan a los objetos de descripción de extremo de servicio o servicio (en el servicio o cliente, respectivamente) antes de que Windows Communication Foundation (WCF) use esos objetos para crear un tiempo de ejecución que ejecute un servicio WCF o un cliente WCF. Cuando se llama a estos comportamientos durante el proceso de construcción en tiempo de ejecución, podrá tener acceso a las propiedades y métodos en tiempo de ejecución que modifican el tiempo de ejecución construido por el contrato, enlaces y direcciones.  
  
### <a name="behavior-methods"></a>Métodos de comportamiento  
 Todo los comportamientos tienen un método `AddBindingParameters`, un método `ApplyDispatchBehavior`, un método `Validate` y un método `ApplyClientBehavior` con una excepción: como <xref:System.ServiceModel.Description.IServiceBehavior> no puede ejecutarse en un cliente, no implementará `ApplyClientBehavior`.  
  
- Utilice el método `AddBindingParameters` para modificar o agregar los objetos personalizados a una colección a la que los enlaces personalizados pueden tener acceso para su uso cuando se construya el tiempo de ejecución. Por ejemplo, la forma en que se especifican los requisitos de protección que afectan a la manera en que se crea el canal pero no es conocido por el desarrollador de canales.  
  
- Utilice el método `Validate` para examinar el árbol de descripción y el objeto del tiempo de ejecución correspondiente para garantizar que se ajusta a algún conjunto de criterios.  
  
- Utilice los métodos `ApplyDispatchBehavior` y `ApplyClientBehavior` para examinar el árbol de descripción y modificar el tiempo de ejecución para un ámbito determinado en el servicio o el cliente. También puede insertar los objetos de extensión.  
  
    > [!NOTE]
    > Aunque se proporciona un árbol de descripción en estos métodos, solo es para el examen. Si se modifica un árbol de descripción, el comportamiento es indefinido.  
  
 Se tiene acceso a las propiedades que puede modificar y las interfaces de personalización que puede implementar a través de las clases de tiempo de ejecución de servicio y de cliente. Los tipos de servicio son las clases <xref:System.ServiceModel.Dispatcher.DispatchRuntime> y <xref:System.ServiceModel.Dispatcher.DispatchOperation>. Los tipos de cliente con las clases <xref:System.ServiceModel.Dispatcher.ClientRuntime> y <xref:System.ServiceModel.Dispatcher.ClientOperation>. Las clases <xref:System.ServiceModel.Dispatcher.ClientRuntime> y <xref:System.ServiceModel.Dispatcher.DispatchRuntime> son los puntos de entrada de la extensibilidad para tener acceso a las propiedades en tiempo de ejecución del cliente y del servicio y las colecciones de extensión, respectivamente. De igual forma, las clases <xref:System.ServiceModel.Dispatcher.ClientOperation> y <xref:System.ServiceModel.Dispatcher.DispatchOperation> exponen las propiedades del tiempo de ejecución de la operación del cliente y de la operación de servicio, y las colecciones de extensiones, respectivamente. Puede, sin embargo, tener acceso al objeto en tiempo de ejecución de un ámbito más amplio a partir del objeto de tiempo de ejecución de la operación y viceversa, si fuera necesario.  
  
> [!NOTE]
> Para obtener una explicación de las propiedades en tiempo de ejecución y los tipos de extensión que puede usar para modificar el comportamiento de ejecución de un cliente, vea [Extender clientes](extending-clients.md). Para obtener una explicación de las propiedades en tiempo de ejecución y los tipos de extensión que puede usar para modificar el comportamiento de ejecución de un distribuidor de servicios, vea [Extender distribuidores](extending-dispatchers.md).  
  
 La mayoría de los usuarios de WCF no interactúan directamente con el tiempo de ejecución; en su lugar, usan construcciones de modelos de programación principales como puntos de conexión, contratos, enlaces, direcciones y atributos de comportamiento en clases o comportamientos en archivos de configuración. Estas construcciones conforman el árbol de *descripción,* que es la especificación completa para construir un tiempo de ejecución para admitir un servicio o cliente descrito por el árbol de descripción.  
  
 Hay cuatro tipos de comportamientos en WCF:  
  
- Los comportamientos de servicio (tipos <xref:System.ServiceModel.Description.IServiceBehavior>) permiten la personalización del tiempo de ejecución del servicio completo incluido <xref:System.ServiceModel.ServiceHostBase>.  
  
- Los comportamientos del extremo (tipos <xref:System.ServiceModel.Description.IEndpointBehavior>) permiten la personalización de los extremos de servicio y sus objetos <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> asociados.  
  
- Los comportamientos del contrato (tipos <xref:System.ServiceModel.Description.IContractBehavior>) permiten la personalización de las clases <xref:System.ServiceModel.Dispatcher.ClientRuntime> y <xref:System.ServiceModel.Dispatcher.DispatchRuntime> en las aplicaciones de cliente y servicio, respectivamente.  
  
- Los comportamientos de la operación (tipos <xref:System.ServiceModel.Description.IOperationBehavior>) permiten la personalización de las clases <xref:System.ServiceModel.Dispatcher.ClientOperation> y <xref:System.ServiceModel.Dispatcher.DispatchOperation>, de nuevo, en el cliente y el servicio.  
  
 Puede agregar estos comportamientos a los distintos objetos de descripción implementando los atributos personalizados, utilizando los archivos de configuración de la aplicación, o directamente agregándolos a la colección de comportamientos en el objeto de descripción adecuado. Sin embargo, deben agregarse a la descripción del servicio o a un objeto de descripción del punto de conexión del servicio antes de llamar a <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ServiceHost> o <xref:System.ServiceModel.ChannelFactory%601>.  
  
### <a name="behavior-scopes"></a>Ámbitos de comportamiento  
 Hay cuatro tipos de comportamiento, cada uno de los cuales se corresponde con un ámbito determinado de acceso en tiempo de ejecución.  
  
#### <a name="service-behaviors"></a>Comportamientos de servicio  
 Los comportamientos de servicio, que implementan <xref:System.ServiceModel.Description.IServiceBehavior>, son el mecanismo principal por medio del cual modifica el tiempo de ejecución del servicio completo. Hay tres mecanismos para agregar los comportamientos de servicio a un servicio.  
  
1. Utilizar un atributo en la clase de servicio.  Cuando se construye un <xref:System.ServiceModel.ServiceHost>, la implementación de <xref:System.ServiceModel.ServiceHost> utiliza la reflexión para detectar el conjunto de atributos en el tipo del servicio. Si cualquiera de estos atributos es una implementación de <xref:System.ServiceModel.Description.IServiceBehavior>, se agregan a la colección de comportamientos en <xref:System.ServiceModel.Description.ServiceDescription>. Esto permite a esos comportamientos participar en la construcción del tiempo de ejecución del servicio.  
  
2. Agregar mediante programación el comportamiento a la colección de comportamientos en <xref:System.ServiceModel.Description.ServiceDescription>. Esto se puede lograr con las siguientes líneas de código:  
  
    ```csharp
    ServiceHost host = new ServiceHost(/* Parameters */);  
    host.Description.Behaviors.Add(/* Service Behavior */);  
    ```  
  
3. Implementar un <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> personalizado que extiende la configuración. Esto permite el uso del comportamiento de servicio a partir de los archivos de configuración de la aplicación.  
  
 Ejemplos de comportamientos de <xref:System.ServiceModel.ServiceBehaviorAttribute> servicio en <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>WCF <xref:System.ServiceModel.Description.ServiceMetadataBehavior> incluyen el atributo, el , y el comportamiento.  
  
#### <a name="contract-behaviors"></a>Comportamientos de contrato  
 Los comportamientos de contrato, que implementan la interfaz <xref:System.ServiceModel.Description.IContractBehavior>, se utilizan para extender el tiempo de ejecución del cliente y el servicio en un contrato.  
  
 Hay dos mecanismos para agregar los comportamientos del contrato a un contrato.  El primer mecanismo es crear un atributo personalizado que se va a utilizar en la interfaz de contrato. Cuando se pasa una interfaz de contrato a a <xref:System.ServiceModel.ServiceHost> o a <xref:System.ServiceModel.ChannelFactory%601>, WCF examina los atributos de la interfaz. Si los atributos son implementaciones de <xref:System.ServiceModel.Description.IContractBehavior>, se agregarán a la colección de comportamientos en el <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType> creado para esa interfaz.  
  
 También puede implementar <xref:System.ServiceModel.Description.IContractBehaviorAttribute?displayProperty=nameWithType> en el atributo de comportamiento de contrato personalizado. En este caso, el comportamiento es como sigue cuando se aplica a:  
  
 •Una interfaz de contrato. En este caso, el comportamiento se aplica a todos los contratos de <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A?displayProperty=nameWithType> ese tipo en cualquier extremo y WCF omite el valor de la propiedad.  
  
 •Una clase de servicio. En este caso, el comportamiento se aplica solo a los puntos de conexión cuyo contrato es el valor de la propiedad <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A>.  
  
 •Una clase de devolución de llamada. En este caso, el comportamiento se aplica al extremo del cliente <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> dúplex y WCF omite el valor de la propiedad.  
  
 El segundo mecanismo es agregar el comportamiento a la colección de comportamientos en <xref:System.ServiceModel.Description.ContractDescription>.  
  
 Ejemplos de comportamientos de <xref:System.ServiceModel.DeliveryRequirementsAttribute?displayProperty=nameWithType> contrato en WCF incluyen el atributo. Para obtener más información y un ejemplo, vea el tema de referencia.  
  
#### <a name="endpoint-behaviors"></a>Comportamientos del extremo  
 Los comportamientos del punto de conexión, que implementan <xref:System.ServiceModel.Description.IEndpointBehavior>, son el mecanismo principal por medio del cual modifica todo el servicio o el tiempo de ejecución del cliente para un punto de conexión concreto.  
  
 Hay dos mecanismos para agregar los comportamientos del extremo a un servicio.  
  
1. Agregue el comportamiento a la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>.  
  
2. Implementar un <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> personalizado que extiende la configuración.  
  
 Para obtener más información y un ejemplo, vea el tema de referencia.  
  
#### <a name="operation-behaviors"></a>Comportamientos de la operación  
 Los comportamientos de la operación, que implementan la interfaz <xref:System.ServiceModel.Description.IOperationBehavior>, se utilizan para extender el tiempo de ejecución del cliente y el servicio para cada operación.  
  
 Hay dos mecanismos para agregar los comportamientos de la operación a una operación. El primero es crear un atributo personalizado que se va a utilizar en el método que modela la operación. Cuando se agrega una <xref:System.ServiceModel.ServiceHost> operación <xref:System.ServiceModel.ChannelFactory>a a <xref:System.ServiceModel.Description.IOperationBehavior> o a , WCF <xref:System.ServiceModel.Description.OperationDescription> agrega los atributos a la colección de comportamientos en el creado para esa operación.  
  
 El segundo mecanismo es agregar directamente el comportamiento a la colección de comportamientos en un <xref:System.ServiceModel.Description.OperationDescription>construido.  
  
 Ejemplos de comportamientos de <xref:System.ServiceModel.OperationBehaviorAttribute> operación <xref:System.ServiceModel.TransactionFlowAttribute>en WCF incluyen el y el .  
  
 Para obtener más información y un ejemplo, vea el tema de referencia.  
  
### <a name="using-configuration-to-create-behaviors"></a>Uso de la configuración para crear comportamientos  
 Los comportamientos de servicio y extremo, y contrato pueden diseñarse para que se especifiquen en el código o utilicen atributos; solo se pueden configurar los comportamientos de servicio y extremo mediante la aplicación o los archivos de configuración web. La exposición de comportamientos con atributos permite a los desarrolladores especificar un comportamiento en el momento de la compilación que no puede agregarse, eliminarse ni modificarse en el tiempo de ejecución. Esto es a menudo conveniente para los comportamientos que siempre se necesitan para la operación correcta de un servicio (por ejemplo, los parámetros relacionados con la transacción al atributo <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>). Exponer comportamientos que utilizan la configuración permite a los desarrolladores dejar la especificación y la configuración de dichos comportamientos a los que implementan el servicio. Esto es conveniente para los comportamientos que son componentes opcionales u otra configuración específica de la implementación, por ejemplo, si los metadatos se exponen para el servicio o la configuración de autorización determinada para un servicio.  
  
> [!NOTE]
> También puede utilizar comportamientos que admiten la configuración para exigir las directivas de aplicación de la empresa insertándolas en el archivo de configuración machine.config y bloqueando esos elementos. Para obtener una descripción y un ejemplo, consulte [Cómo: bloquear puntos de conexión en la empresa](how-to-lock-down-endpoints-in-the-enterprise.md).  
  
 Para exponer un comportamiento mediante la configuración, un desarrollador debe crear una clase derivada de <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> y, a continuación, registrar esa extensión con la configuración.  
  
 El siguiente ejemplo de código muestra cómo <xref:System.ServiceModel.Description.IEndpointBehavior> implementa <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>:  
  
```csharp
// BehaviorExtensionElement members  
public override Type BehaviorType  
{  
  get { return typeof(EndpointBehaviorMessageInspector); }  
}  
  
protected override object CreateBehavior()  
{  
  return new EndpointBehaviorMessageInspector();  
}  
```  
  
 Para que el sistema de configuración cargue un <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> personalizado, se debe registrar como una extensión. El ejemplo de código siguiente muestra el archivo de configuración para el comportamiento del extremo anterior:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service
        name="Microsoft.WCF.Documentation.SampleService"  
        behaviorConfiguration="metadataSupport"  
      >  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8080/ServiceMetadata" />  
          </baseAddresses>  
        </host>  
        <endpoint  
          address="/SampleService"  
          binding="wsHttpBinding"  
          behaviorConfiguration="withMessageInspector"
          contract="Microsoft.WCF.Documentation.ISampleService"  
        />  
        <endpoint  
           address="mex"  
           binding="mexHttpBinding"  
           contract="IMetadataExchange"  
        />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="metadataSupport">  
        <serviceMetadata httpGetEnabled="true" httpGetUrl=""/>  
      </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="withMessageInspector">  
          <endpointMessageInspector />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <extensions>  
      <behaviorExtensions>  
        <add
          name="endpointMessageInspector"  
          type="Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector, HostApplication, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"  
        />  
      </behaviorExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 Dónde `Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector` está el `HostApplication` tipo de extensión de comportamiento y es el nombre del ensamblado en el que se ha compilado esa clase.  
  
### <a name="evaluation-order"></a>Orden de evaluación  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> y <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> son responsables de generar el tiempo de ejecución del modelo de programación y descripción. Los comportamientos, tal y como se han descritos previamente, contribuyen a ese proceso de creación en el servicio, punto de conexión, contrato y operación.  
  
 <xref:System.ServiceModel.ServiceHost> aplica los comportamientos en el orden siguiente:  
  
1. Servicio  
  
2. Contrato  
  
3. Punto de conexión  
  
4. Operación  
  
 Dentro de cualquier colección de comportamientos, no se garantiza ningún orden.  
  
 <xref:System.ServiceModel.ChannelFactory%601> aplica los comportamientos en el orden siguiente:  
  
1. Contrato  
  
2. Punto de conexión  
  
3. Operación  
  
 De nuevo, dentro de cualquier colección de comportamientos, no se garantiza ningún orden.  
  
### <a name="adding-behaviors-programmatically"></a>Adición de comportamientos mediante programación  
 Las propiedades de <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> en la aplicación de servicio no se deben modificar después del método <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=nameWithType> en <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>. Algunos miembros, como la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A?displayProperty=nameWithType> y los métodos `AddServiceEndpoint` en <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, producen una excepción si se modificas pasados ese punto. Otros permiten modificarlos, pero el resultado no está definido.  
  
 De igual forma, en el cliente no se deben modificar los valores <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> después de la llamada a <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> en <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>. La propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A?displayProperty=nameWithType> produce una excepción si se modifica pasado ese punto, pero los otros valores de descripción del cliente se pueden modificar sin el error. El resultado, sin embargo, es indefinido.  
  
 Tanto si es para el servicio como para el cliente, se recomienda modificar la descripción antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType>.  
  
### <a name="inheritance-rules-for-behavior-attributes"></a>La herencia gobierna para los atributos de comportamiento  
 Los cuatro tipos de comportamientos se pueden rellenar utilizando los atributos: los comportamientos de servicio y de contrato. Debido a que los atributos se definen en los objetos y miembros administrados y estos admiten la herencia, será necesario definir cómo funcionan los atributos en el contexto de la herencia.  
  
 En un nivel alto, la regla es que para un ámbito determinado (por ejemplo, servicio, contrato u operación) se aplican todos los atributos de comportamiento en la jerarquía de la herencia para ese ámbito. Si hay dos atributos de comportamiento del mismo tipo, solo se utiliza el tipo más derivado.  
  
#### <a name="service-behaviors"></a>Comportamientos de servicio  
 Para una clase de servicio determinada, se aplicarán todos los atributos de comportamiento del servicio en esa clase y en los elementos primarios de esa clase. Si el mismo tipo de atributo se aplica en varios lugares en la jerarquía de la herencia, se usará el tipo más derivado.  
  
```csharp  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple)]  
[AspNetCompatibilityRequirementsAttribute(  
    AspNetCompatibilityRequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
public class A { /* … */ }  
  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class B : A { /* … */}  
```  
  
 Por ejemplo, en el caso anterior, el servicio B finaliza con un <xref:System.ServiceModel.InstanceContextMode> de <xref:System.ServiceModel.InstanceContextMode.Single>, un modo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> de <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> y un <xref:System.ServiceModel.ConcurrencyMode> de <xref:System.ServiceModel.ConcurrencyMode.Single>. <xref:System.ServiceModel.ConcurrencyMode> es <xref:System.ServiceModel.ConcurrencyMode.Single>, porque el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> en el servicio B está "más derivado" que en el servicio A.  
  
#### <a name="contract-behaviors"></a>Comportamientos de contrato  
 Para un contrato determinado, se aplicarán todos los atributos de comportamiento de contrato en esa interfaz y en los elementos primarios de esa interfaz. Si el mismo tipo de atributo se aplica en varios lugares en la jerarquía de la herencia, se usará el tipo más derivado.  
  
#### <a name="operation-behaviors"></a>Comportamientos de la operación  
 Si una operación determinada no invalida ningún resumen existente ni la operación virtual, no se aplicará ninguna regla de herencia.  
  
 Si una operación invalida una operación existente, se aplicarán todos los atributos de comportamiento de operación en esa operación y en los elementos primarios de esa operación.  Si el mismo tipo de atributo se aplica en varios lugares en la jerarquía de la herencia, se usará el tipo más derivado.
