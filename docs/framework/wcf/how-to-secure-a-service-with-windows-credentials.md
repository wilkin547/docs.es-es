---
title: "C&#243;mo: Proteger un servicio con credenciales de Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, seguridad"
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
caps.latest.revision: 26
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 26
---
# C&#243;mo: Proteger un servicio con credenciales de Windows
En este tema se muestra cómo habilitar la seguridad de transferencia en un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] que reside en un dominio de Windows y al que llaman los clientes del mismo dominio. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Este escenario, consulte [seguridad de transporte con autenticación de Windows](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md). Para una aplicación de ejemplo, consulte el [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) ejemplo.  
  
 En este tema se parte del supuesto de que ya tiene definidas una interfaz e implementación de contrato. También puede modificar un servicio y cliente existentes.  
  
 Puede proteger completamente un servicio con credenciales de Windows en el código. Alternativamente, puede omitir una parte del código mediante un archivo de configuración. En este tema se explican ambos métodos. Asegúrese de que sigue solamente uno de ellos.  
  
 Los tres primeros procedimientos muestran cómo proteger el servicio en el código. En el cuarto y quinto procedimientos se muestra cómo hacerlo con un archivo de configuración.  
  
## <a name="using-code"></a>Mediante código  
 El código completo para el servicio y el cliente se encuentra en la sección Ejemplo al final de este tema.  
  
 El primer procedimiento le guía a través de la creación y configuración de un <xref:System.ServiceModel.WSHttpBinding> clase en el código. El enlace usa el transporte HTTP. El mismo enlace se usa en el cliente.  
  
#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a>Para crear un WSHttpBinding que utiliza credenciales de Windows y seguridad de mensaje  
  
1.  El código de este procedimiento se encuentra insertado al principio del método `Run` de la clase `Test` en el código del servicio, en la sección Ejemplo.  
  
2.  Cree una instancia de la <xref:System.ServiceModel.WSHttpBinding> clase.  
  
3.  Establecer el <xref:System.ServiceModel.WsHttpSecurity.Mode%2A> propiedad de la <xref:System.ServiceModel.WsHttpSecurity> clase <xref:System.ServiceModel.SecurityMode>.  
  
4.  Establecer el <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> propiedad de la <xref:System.ServiceModel.MessageSecurityOverHttp> clase <xref:System.ServiceModel.MessageCredentialType>.  
  
5.  El código de este procedimiento es el siguiente:  
  
     [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
     [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]  
  
### <a name="using-the-binding-in-a-service"></a>Utilizar el enlace en un servicio  
 Este es el segundo procedimiento, que muestra cómo usar el enlace en un servicio autohospedado. [!INCLUDE[crabout](../../../includes/crabout-md.md)]hospedaje de servicios, consulte [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).  
  
##### <a name="to-use-a-binding-in-a-service"></a>Utilizar un enlace en un servicio  
  
1.  Inserte el código de este procedimiento después del código del procedimiento anterior.  
  
2.  Crear un <xref:System.Type> variable denominada `contractType` y asignar el tipo de la interfaz (`ICalculator`). Cuando utilice [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], utilice al operador `GetType`; cuando utilice C#, utilice la palabra clave `typeof`.  
  
3.  Cree una segunda variable `Type``serviceType` con nombre y asígnele el tipo del contrato implementado (`Calculator`).  
  
4.  Cree una instancia de la <xref:System.Uri> clase denominada `baseAddress` con la dirección base del servicio. La dirección base debe tener un esquema que coincida con el transporte. En este caso, el esquema de transporte es HTTP y la dirección incluye el identificador uniforme de recursos (URI) especial "localhost" y un número de puerto (8036) así como una dirección de punto de conexión base ("serviceModelSamples/): http://localhost:8036/serviceModelSamples/.  
  
5.  Cree una instancia de la <xref:System.ServiceModel.ServiceHost> clase con la `serviceType` y `baseAddress` las variables.  
  
6.  Agregue un extremo al servicio incluyendo `contractType`, el enlace y el nombre del extremo ("secureCalculator"). Un cliente debe concatenar la dirección base y el nombre de punto de conexión al iniciar una llamada al servicio.  
  
7.  Llame a la <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> método para iniciar el servicio. El código de este procedimiento se muestra aquí:  
  
     [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
     [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]  
  
### <a name="using-the-binding-in-a-client"></a>Utilizar el enlace en un cliente  
 Este procedimiento muestra cómo generar un proxy que se comunica con el servicio. El proxy se genera con el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) que utiliza los metadatos del servicio para crear el proxy.  
  
 Este procedimiento también crea una instancia de la <xref:System.ServiceModel.WSHttpBinding> clase para comunicarse con el servicio y, a continuación, llama al servicio.  
  
 Este ejemplo solo utiliza código para crear el cliente. Como alternativa, puede utilizar un archivo de configuración, que se muestra en la sección que sigue a este procedimiento.  
  
##### <a name="to-use-a-binding-in-a-client-with-code"></a>Para usar un enlace en un cliente con el código  
  
1.  Use la herramienta SvcUtil.exe para generar el código del proxy a partir de los metadatos del servicio. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Cómo: crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). El código proxy generado hereda de la <xref:System.ServiceModel.ClientBase%601> (clase), lo que garantiza que cada cliente tenga el necesarios constructores, métodos y propiedades para comunicarse con un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio. En este ejemplo, el código generado incluye la clase `CalculatorClient`, que implementa la interfaz `ICalculator`, habilitando la compatibilidad con el código del servicio.  
  
2.  El código de este procedimiento se encuentra insertado al principio del método `Main` del programa cliente.  
  
3.  Cree una instancia de la <xref:System.ServiceModel.WSHttpBinding> de clase y establezca su modo de seguridad en `Message` y su tipo de credencial de cliente `Windows`. El ejemplo denomina el `clientBinding`variable.  
  
4.  Cree una instancia de la <xref:System.ServiceModel.EndpointAddress> clase denominada `serviceAddress`. Inicialice la instancia con la dirección base concatenada con el nombre de punto de conexión.  
  
5.  Cree una instancia de la clase de cliente generada con `serviceAddress` y las variables `clientBinding`.  
  
6.  Llame a la <xref:System.ServiceModel.ClientBase%601.Open%2A> método, tal como se muestra en el código siguiente.  
  
7.  Llame al servicio y muestre los resultados.  
  
     [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
     [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]  
  
## <a name="using-the-configuration-file"></a>Usar el archivo de configuración  
 En lugar de crear el enlace con código de procedimiento, puede usar el código siguiente, que se muestra para la sección de enlaces del archivo de configuración.  
  
 Si no dispone de un servicio definido, consulte [diseño e implementación de servicios](../../../docs/framework/wcf/designing-and-implementing-services.md), y [configurar Services](../../../docs/framework/wcf/configuring-services.md).  
  
 **Nota** este código de configuración se utiliza en el servicio y el cliente de los archivos de configuración.  
  
#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a>Habilitar la seguridad de la transferencia en un servicio en un dominio de Windows utilizando la configuración  
  
1.  Agregar un [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento a la [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sección del elemento del archivo de configuración.  
  
2.  Agregue un elemento <`binding`> al elemento <`WSHttpBinding`> y establezca el atributo `configurationName` a un valor apropiado para su aplicación.  
  
3.  Agregue un elemento <`security`> y establezca el atributo `mode` en Message.  
  
4.  Agregue un elemento <`message`> y establezca el atributo `clientCredentialType` en Windows.  
  
5.  En el archivo de configuración del servicio, reemplace la sección `<bindings>` con el código siguiente. Si no dispone de un archivo de configuración de servicio, consulte [uso de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
    ```  
    <bindings>  
      <wsHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
### <a name="using-the-binding-in-a-client"></a>Utilizar el enlace en un cliente  
 En este procedimiento se muestra cómo generar dos archivos: un proxy que se comunica con el servicio y un archivo de configuración. También se describen los cambios en el programa cliente, que es el tercer archivo utilizado en el cliente.  
  
##### <a name="to-use-a-binding-in-a-client-with-configuration"></a>Para usar un enlace en un cliente mediante configuración  
  
1.  Use la herramienta SvcUtil.exe para generar el código proxy y el archivo de configuración a partir de los metadatos del servicio. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Cómo: crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Reemplace el [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sección del archivo de configuración generado con el código de configuración de la sección anterior.  
  
3.  El código de procedimiento se encuentra insertado al principio del método `Main` del programa cliente.  
  
4.  Cree una instancia de la clase de cliente generada, pasando el nombre del enlace en el archivo de configuración como parámetro de entrada.  
  
5.  Llame a la <xref:System.ServiceModel.ClientBase%601.Open%2A> método, tal como se muestra en el código siguiente.  
  
6.  Llame al servicio y muestre los resultados.  
  
     [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]  
  
 [!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)]
 <!-- TODO: review snippet reference [!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]  -->  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.WSHttpBinding>   
 [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Cómo: crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Protección de servicios](../../../docs/framework/wcf/securing-services.md)   
 [Información general sobre seguridad](../../../docs/framework/wcf/feature-details/security-overview.md)