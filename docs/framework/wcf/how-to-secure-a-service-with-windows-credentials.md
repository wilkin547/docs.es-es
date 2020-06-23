---
title: Procedimiento para proteger un servicio con credenciales de Windows
description: Obtenga información acerca de cómo habilitar la seguridad de transporte en un servicio WCF que resida en un dominio de Windows y al que llaman los clientes del mismo dominio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
ms.openlocfilehash: 8ef164e1475bfd5f047a99426a2bed43a7aa7353
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244639"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a>Procedimiento para proteger un servicio con credenciales de Windows

En este tema se muestra cómo habilitar la seguridad de transporte en un servicio de Windows Communication Foundation (WCF) que reside en un dominio de Windows y al que llaman los clientes del mismo dominio. Para obtener más información acerca de este escenario, vea [seguridad de transporte con autenticación de Windows](./feature-details/transport-security-with-windows-authentication.md). Para obtener una aplicación de ejemplo, vea el ejemplo [wsHttpBinding](./samples/wshttpbinding.md) .

En este tema se parte del supuesto de que ya tiene definidas una interfaz e implementación de contrato. También puede modificar un servicio y cliente existentes.

Puede proteger completamente un servicio con credenciales de Windows en el código. Alternativamente, puede omitir una parte del código mediante un archivo de configuración. En este tema se explican ambos métodos. Asegúrese de que sigue solamente uno de ellos.

Los tres primeros procedimientos muestran cómo proteger el servicio en el código. En el cuarto y quinto procedimientos se muestra cómo hacerlo con un archivo de configuración.

## <a name="using-code"></a>Mediante código

El código completo para el servicio y el cliente se encuentra en la sección Ejemplo al final de este tema.

El primer procedimiento le guía en la creación y configuración de una clase <xref:System.ServiceModel.WSHttpBinding> en el código. El enlace usa el transporte HTTP. El mismo enlace se usa en el cliente.

#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a>Para crear un WSHttpBinding que utiliza credenciales de Windows y seguridad de mensaje

1. El código de este procedimiento se encuentra insertado al principio del método `Run` de la clase `Test` en el código del servicio, en la sección Ejemplo.

2. Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding>.

3. Establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> de la clase <xref:System.ServiceModel.WSHttpSecurity> en <xref:System.ServiceModel.SecurityMode.Message>.

4. Establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> de la clase <xref:System.ServiceModel.MessageSecurityOverHttp> en <xref:System.ServiceModel.MessageCredentialType.Windows>.

5. El código de este procedimiento es el siguiente:

    [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
    [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]

### <a name="using-the-binding-in-a-service"></a>Utilizar el enlace en un servicio

Este es el segundo procedimiento, que muestra cómo usar el enlace en un servicio autohospedado. Para obtener más información acerca de los servicios de hospedaje, vea [servicios de hospedaje](hosting-services.md).

##### <a name="to-use-a-binding-in-a-service"></a>Utilizar un enlace en un servicio

1. Inserte el código de este procedimiento después del código del procedimiento anterior.

2. Cree una variable <xref:System.Type>`contractType` con nombre y asígnele el tipo de la interfaz (`ICalculator`). Al usar Visual Basic, use el `GetType` operador; al usar C#, use la `typeof` palabra clave.

3. Cree una segunda variable <xref:System.Type>`serviceType` con nombre y asígnele el tipo del contrato implementado (`Calculator`).

4. Cree una instancia de la clase <xref:System.Uri> denominada `baseAddress` con la dirección base del servicio. La dirección base debe tener un esquema que coincida con el transporte. En este caso, el esquema de transporte es HTTP y la dirección incluye el identificador uniforme de recursos (URI) especial "localhost" y un número de puerto (8036), así como una dirección de punto de conexión base ("serviceModelSamples/): `http://localhost:8036/serviceModelSamples/` .

5. Cree una instancia de la clase<xref:System.ServiceModel.ServiceHost> con `serviceType` y variables `baseAddress`.

6. Agregue un punto de conexión al servicio incluyendo `contractType`, el enlace y el nombre del punto de conexión ("secureCalculator"). Un cliente debe concatenar la dirección base y el nombre de punto de conexión al iniciar una llamada al servicio.

7. Llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> para iniciar el servicio. El código de este procedimiento se muestra aquí:

    [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
    [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]

### <a name="using-the-binding-in-a-client"></a>Utilizar el enlace en un cliente

Este procedimiento muestra cómo generar un proxy que se comunica con el servicio. El proxy se genera con la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe),](servicemodel-metadata-utility-tool-svcutil-exe.md) que usa los metadatos del servicio para crear el proxy.

En este procedimiento también se crea una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> para comunicarse con el servicio y, a continuación, se llama al servicio.

Este ejemplo solo utiliza código para crear el cliente. Como alternativa, puede utilizar un archivo de configuración, que se muestra en la sección que sigue a este procedimiento.

#### <a name="to-use-a-binding-in-a-client-with-code"></a>Para usar un enlace en un cliente con el código

1. Use la herramienta SvcUtil.exe para generar el código del proxy a partir de los metadatos del servicio. Para obtener más información, consulte [Cómo: crear un cliente](how-to-create-a-wcf-client.md). El código proxy generado hereda de la <xref:System.ServiceModel.ClientBase%601> clase, lo que garantiza que cada cliente tenga los constructores, métodos y propiedades necesarios para comunicarse con un servicio WCF. En este ejemplo, el código generado incluye la clase `CalculatorClient`, que implementa la interfaz `ICalculator`, habilitando la compatibilidad con el código del servicio.

2. El código de este procedimiento se encuentra insertado al principio del método `Main` del programa cliente.

3. Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en `Message` y su tipo de credencial de cliente en `Windows`. El ejemplo denomina el `clientBinding`variable.

4. Cree una instancia de la clase <xref:System.ServiceModel.EndpointAddress> denominada `serviceAddress`. Inicialice la instancia con la dirección base concatenada con el nombre de punto de conexión.

5. Cree una instancia de la clase de cliente generada con `serviceAddress` y las variables `clientBinding`.

6. Llame al método <xref:System.ServiceModel.ClientBase%601.Open%2A>, como se muestra en el siguiente código.

7. Llame al servicio y muestre los resultados.

    [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
    [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]

## <a name="using-the-configuration-file"></a>Usar el archivo de configuración

En lugar de crear el enlace con código de procedimiento, puede usar el código siguiente, que se muestra para la sección de enlaces del archivo de configuración.

Si aún no tiene un servicio definido, vea [diseñar e implementar servicios](designing-and-implementing-services.md)y [configurar servicios](configuring-services.md).

> [!NOTE]
> Este código de configuración se utiliza en los archivos de configuración de servicio y de cliente.

#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a>Habilitar la seguridad de la transferencia en un servicio en un dominio de Windows utilizando la configuración

1. Agregue un [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento a la [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) sección de elemento del archivo de configuración.

2. Agregue un `binding` elemento <> al elemento <`WSHttpBinding`> y establezca el `configurationName` atributo en un valor adecuado para su aplicación.

3. Agregue un `security` elemento <> y establezca el `mode` atributo en Message.

4. Agregue un `message` elemento <> y establezca el `clientCredentialType` atributo en Windows.

5. En el archivo de configuración del servicio, reemplace la sección `<bindings>` con el código siguiente. Si aún no tiene un archivo de configuración de servicio, consulte [uso de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md).

    ```xml
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

#### <a name="to-use-a-binding-in-a-client-with-configuration"></a>Para usar un enlace en un cliente mediante configuración

1. Use la herramienta SvcUtil.exe para generar el código proxy y el archivo de configuración a partir de los metadatos del servicio. Para obtener más información, consulte [Cómo: crear un cliente](how-to-create-a-wcf-client.md).

2. Reemplace la [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) sección del archivo de configuración generado por el código de configuración de la sección anterior.

3. El código de procedimiento se encuentra insertado al principio del método `Main` del programa cliente.

4. Cree una instancia de la clase de cliente generada, pasando el nombre del enlace en el archivo de configuración como parámetro de entrada.

5. Llame al método <xref:System.ServiceModel.ClientBase%601.Open%2A>, como se muestra en el siguiente código.

6. Llame al servicio y muestre los resultados.

    [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]

## <a name="example"></a>Ejemplo

[!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]

[!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)]
[!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.WSHttpBinding>
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Cómo crear un cliente](how-to-create-a-wcf-client.md)
- [Seguridad de servicios](securing-services.md)
- [Información general sobre seguridad](./feature-details/security-overview.md)
