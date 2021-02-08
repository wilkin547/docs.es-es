---
description: 'Más información acerca de: formateador de operaciones y selector de operaciones'
title: Formateador de operación y selector de operación
ms.date: 03/30/2017
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
ms.openlocfilehash: dedfa92ddd2f8192eef6b11d8ecde133b961d6cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793225"
---
# <a name="operation-formatter-and-operation-selector"></a>Formateador de operación y selector de operación

Este ejemplo muestra cómo se pueden usar los puntos de extensibilidad de Windows Communication Foundation (WCF) para permitir datos de mensaje en un formato diferente del que espera WCF. De forma predeterminada, los formateadores de WCF esperan que los parámetros de método se incluyan en el `soap:body` elemento. El ejemplo muestra cómo implementar un formateador de operación personalizado que analiza los datos de parámetro a partir de una cadena de consulta HTTP GET en su lugar e invoca los métodos que utilizan esos datos.  
  
 El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio. Muestra cómo se pueden cambiar los mensajes de suma, resta, multiplicación y división para usar HTTP GET para las solicitudes de cliente a servidor y HTTP POST con mensajes POX para respuestas de servidor a cliente.  
  
 Para ello, el ejemplo proporciona lo siguiente:  
  
- `QueryStringFormatter`, que implementa <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> y <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> para el cliente y el servidor, respectivamente, y procesa los datos en la cadena de consulta.  
  
- `UriOperationSelector`, que implementa <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> en el servidor para realizar el envío de la operación según el nombre de la operación en la solicitud GET.  
  
- Comportamiento del extremo `EnableHttpGetRequestsBehavior` (y la configuración correspondiente), que agrega el selector de operación necesario al tiempo de ejecución.  
  
- Muestra cómo insertar un nuevo formateador de operación en el tiempo de ejecución.  
  
- En este ejemplo, el cliente y el servicio son aplicaciones de consola (.exe).  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## <a name="key-concepts"></a>Conceptos clave  

 `QueryStringFormatter` -El formateador de la operación es el componente de WCF responsable de convertir un mensaje en una matriz de objetos de parámetro y una matriz de objetos de parámetro en un mensaje. Esto se hace en el cliente utilizando la interfaz <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> y en el servidor con la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>. Estas interfaces le permiten a los usuarios recibir los mensajes de respuesta y solicitud desde los métodos `Serialize` y `Deserialize`.  
  
 En este ejemplo, `QueryStringFormatter` implementa ambas interfaces y se implementa en el cliente y el servidor.  
  
 Solicitud:  
  
- El ejemplo utiliza la clase <xref:System.ComponentModel.TypeConverter> para convertir los datos de parámetro en el mensaje de solicitud en cadenas y viceversa. Si <xref:System.ComponentModel.TypeConverter> no está disponible para un tipo específico, el formateador del ejemplo produce una excepción.  
  
- En el método `IClientMessageFormatter.SerializeRequest` en el cliente, el formateador crea un URI con la dirección A adecuada y añade el nombre de la operación como un sufijo. Este nombre se utiliza para enviar a la operación adecuada en el servidor. Toma a continuación la matriz de objetos de parámetro y serializa los datos de parámetro en la cadena de consulta del URI utilizando nombres de parámetro y los valores convertidos por la clase <xref:System.ComponentModel.TypeConverter>. Las propiedades <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> y <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> se establecen en este URI. Se tiene acceso a <xref:System.ServiceModel.Channels.MessageProperties> mediante la propiedad <xref:System.ServiceModel.Channels.Message.Properties%2A>.  
  
- En el método `IDispatchMessageFormatter.DeserializeRequest` en el servidor, el formateador recupera el URI `Via` en las propiedades del mensaje de solicitud entrante. Analiza los pares nombre-valor en la cadena de consulta del URI en nombres y valores de parámetro y los utiliza para rellenar la matriz de parámetros que se ha pasado en el método. Tenga en cuenta que el envío de la operación ya se ha producido, por lo que el sufijo del nombre de la operación se omite en este método.  
  
 Respuesta:  
  
- En este ejemplo, solo se utiliza HTTP GET para la solicitud. El formateador delega el envío de la respuesta al formateador original que se habría utilizado para generar un mensaje XML. Uno de los objetivos de este ejemplo es mostrar cómo se puede implementar este tipo de formateador que delega.  
  
### <a name="uripathsuffixoperationselector-class"></a>Clase UriPathSuffixOperationSelector  

 La interfaz <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> permite a los usuarios implementar su propia lógica para la que la operación de un mensaje particular debería enviarse.  
  
 En este ejemplo, se debe implementar `UriPathSuffixOperationSelector` en el servidor para seleccionar la operación adecuada porque el nombre de la operación está incluido en el URI de HTTP GET en lugar de en un encabezado de acción en el mensaje. El ejemplo se configura para permitir solo nombres de operación sin distinción entre mayúsculas y minúsculas.  
  
 El método `SelectOperation` toma el mensaje entrante y busca el URI de `Via` en sus propiedades de mensaje. Extrae el sufijo del nombre de operación del URI, busca una tabla interna para obtener el nombre de la operación al que se debería enviar el mensaje y devuelve ese nombre de la operación.  
  
### <a name="enablehttpgetrequestsbehavior-class"></a>Clase EnableHttpGetRequestsBehavior  

 Se puede configurar el componente `UriPathSuffixOperationSelector` mediante programación o a través de un comportamiento del punto de conexión. El ejemplo implementa el comportamiento `EnableHttpGetRequestsBehavior`, que se especifica en el archivo de configuración de la aplicación del servicio.  
  
 En el servidor:  
  
 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> está establecido en la implementación <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.  
  
 De forma predeterminada, WCF usa un filtro de direcciones de coincidencia exacta. El URI en el mensaje entrante contiene un sufijo de nombre de operación seguido por una cadena de consulta que contiene los datos de parámetro, por lo que el comportamiento del extremo también cambia el filtro de la dirección para ser un filtro de coincidencia de prefijo. Usa WCF <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> para este propósito.  
  
### <a name="installing-operation-formatters"></a>Instalación de los formateadores de operación  

 Los comportamientos de la operación que especifican los formateadores son únicos. Dicho comportamiento se implementa siempre de forma predeterminada en cada operación para crear el formateador de operación necesario. Sin embargo, estos comportamientos se parecen a otro comportamiento de la operación; ningún otro atributo los puede identificar. Para instalar un comportamiento de reemplazo, la implementación debe buscar comportamientos de formateador específicos que se instalan de forma predeterminada en el cargador de tipos de WCF y reemplazarlos o agregar un comportamiento compatible para que se ejecute después del comportamiento predeterminado.  
  
 Se pueden configurar estos comportamientos de formateadores de operación mediante programación antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> o especificando un comportamiento de la operación que se ejecuta después del valor predeterminado. Sin embargo, un comportamiento del extremo (y por consiguiente por configuración) no puede configurarse con facilidad, porque el modelo de comportamiento no permite que un comportamiento sustituya a otros comportamientos o que modifique el árbol de descripción.  
  
 En el cliente:  
  
 Se debe implementar la implementación <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> para que pueda convertir las solicitudes en las solicitudes en solicitudes HTTP GET y delegar al formateador original para las respuestas. Esto se hace llamando al método del asistente `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`.  
  
 Este paso se debe realizar antes de llamar a `CreateChannel`.  
  
```csharp  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 En el servidor:  
  
- Se debe implementar la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> para que pueda leer las solicitudes HTTP GET y delegar en el formateador original para escribir las respuestas. Esto se hace llamando al mismo método del asistente `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` como el cliente (vea el ejemplo de código anterior).  
  
- Este paso se debe realizar antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. En este ejemplo, mostramos cómo el formateador se modifica manualmente antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>. Otra manera de lograr lo mismo es derivar una clase de <xref:System.ServiceModel.ServiceHost> que realiza las llamadas a `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` antes de abrirse (para ver ejemplos consulte la documentación sobre hospedaje y los ejemplos).  
  
### <a name="user-experience"></a>Experiencia del usuario  

 En el servidor:  
  
- La implementación del servidor `ICalculator` no tiene que cambiarse.  
  
- App.config para el servicio debe utilizar un enlace POX personalizado que defina el atributo `messageVersion` del elemento `textMessageEncoding` en `None`.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- App.config para el servicio también debe especificar el `EnableHttpGetRequestsBehavior` personalizado agregándolo a la sección de extensiones de comportamiento y utilizándolo.  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
- Agregue los formateadores de operación antes de llamar a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.  
  
 En el cliente:  
  
- La implementación del cliente no tiene que cambiar.  
  
- App.config para el cliente debe utilizar un enlace POX personalizado que define el atributo `messageVersion` del elemento `textMessageEncoding` en `None`. Una diferencia del servicio es que el cliente debe habilitar el direccionamiento manual para que se pueda modificar la dirección A saliente.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- App.config para el cliente debe especificar el mismo `EnableHttpGetRequestsBehavior` personalizado que el servidor.  
  
- Agregue los formateadores de operación antes de llamar a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Las cuatro operaciones (sumar, restar, multiplicar y dividir) deberán realizarse correctamente.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QueryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
