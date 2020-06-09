---
title: Procedimiento para proteger puntos de conexión de metadatos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
ms.openlocfilehash: c5efd921d3826ef814bf45d6895255981101d992
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592962"
---
# <a name="how-to-secure-metadata-endpoints"></a>Procedimiento para proteger puntos de conexión de metadatos

Los metadatos para un servicio pueden contener información confidencial sobre su aplicación que un usuario malintencionado puede aprovechar. Los consumidores de su servicio también pueden requerir un mecanismo seguro para obtener los metadatos sobre su servicio. Por consiguiente, a veces es necesario publicar sus metadatos utilizando un extremo seguro.

Los puntos de conexión de metadatos generalmente se protegen utilizando los mecanismos de seguridad estándar definidos en Windows Communication Foundation (WCF) para proteger los puntos de conexión de la aplicación. Para más información, consulte [Introducción a la seguridad](security-overview.md).

En este tema se describen los pasos para crear un extremo protegido por un certificado SSL (Capa de sockets seguros) o, en otras palabras, un extremo de HTTPS.

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a>Para crear un extremo seguro de metadatos HTTPS GET en código

1. Configure un puerto con un certificado X.509 adecuado. El certificado debe proceder de una autoridad de confianza y debe tener un uso previsto de "Autorización de servicio." Debe utilizar la herramienta HttpCfg.exe para asociar el certificado al puerto. Consulte [Cómo: configurar un puerto con un certificado SSL](how-to-configure-a-port-with-an-ssl-certificate.md).

    > [!IMPORTANT]
    > El asunto del certificado o su Domain Name System (DNS) debe coincidir con el nombre del equipo. Esto es esencial porque uno de los primeros pasos que el mecanismo de HTTPS realiza es comprobar que el certificado esté emitido para el mismo identificador URI (Uniform Resource Identifier) que la dirección en la que se invoca.

2. Cree una nueva instancia de la clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.

3. Establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> de la clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en `true`.

4. Establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> en una URL adecuada. Tenga en cuenta que si especifica una dirección absoluta, la dirección URL debe comenzar con el esquema `https://` . Si especifica una dirección relativa, debe proporcionar una dirección base de HTTPS para su host de servicio. Si esta propiedad no está establecida, la dirección predeterminada es "", o directamente en la dirección base de HTTPS para el servicio.

5. Agregue la instancia a la colección de comportamientos que la propiedad <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> de las clases <xref:System.ServiceModel.Description.ServiceDescription> devuelve, como se muestra en el código siguiente.

    [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
    [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a>Para crear un punto de conexión seguro de metadatos HTTPS GET en configuración

1. Agregue un [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento al [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento del archivo de configuración para el servicio.

2. Agregue un [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) elemento al [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento.

3. Agregue un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento al `<serviceBehaviors>` elemento.

4. Establezca el atributo `name` del elemento `<behavior>` en un valor adecuado. El atributo `name` es necesario. El ejemplo siguiente utiliza el valor `mySvcBehavior`.

5. Agregue un [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) al `<behavior>` elemento.

6. Establezca el atributo `httpsGetEnabled` del elemento `<serviceMetadata>` en `true`:

7. Establezca el atributo `httpsGetUrl` del elemento `<serviceMetadata>` en un valor adecuado. Tenga en cuenta que si especifica una dirección absoluta, la dirección URL debe comenzar con el esquema `https://` . Si especifica una dirección relativa, debe proporcionar una dirección base de HTTPS para su host de servicio. Si esta propiedad no está establecida, la dirección predeterminada es "", o directamente en la dirección base de HTTPS para el servicio.

8. Para utilizar el comportamiento con un servicio, establezca el `behaviorConfiguration` atributo del [\<service>](../../configure-apps/file-schema/wcf/service.md) elemento en el valor del atributo name del elemento Behavior. El código de configuración siguiente muestra un ejemplo completo.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
     <system.serviceModel>
      <behaviors>
       <serviceBehaviors>
        <behavior name="mySvcBehavior">
         <serviceMetadata httpsGetEnabled="true"
              httpsGetUrl="https://localhost:8036/calcMetadata" />
        </behavior>
       </serviceBehaviors>
      </behaviors>
     <services>
      <service behaviorConfiguration="mySvcBehavior"
            name="Microsoft.Security.Samples.Calculator">
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"
       binding="wsHttpBinding" bindingConfiguration=""
       contract="Microsoft.Security.Samples.ICalculator" />
      </service>
     </services>
    </system.serviceModel>
    </configuration>
    ```

## <a name="example"></a>Ejemplo

El ejemplo siguiente crea una instancia de una clase <xref:System.ServiceModel.ServiceHost> y agrega un extremo. El código crea a continuación una instancia de la clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> y establece las propiedades para crear un punto de intercambio seguro de metadatos.

[!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
[!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]

## <a name="compiling-the-code"></a>Compilar el código

El ejemplo de código utiliza los espacios de nombres siguientes:

- <xref:System.ServiceModel?displayProperty=nameWithType>

- <xref:System.ServiceModel.Description?displayProperty=nameWithType>

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [Procedimiento para configurar un puerto con un certificado SSL](how-to-configure-a-port-with-an-ssl-certificate.md)
- [Trabajar con certificados](working-with-certificates.md)
- [Consideraciones de seguridad con metadatos](security-considerations-with-metadata.md)
- [Protección de servicios y clientes](securing-services-and-clients.md)
