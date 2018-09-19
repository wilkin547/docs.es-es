---
title: Configuración de un cliente básico de Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 3f267edf87711de8a5969e3e0b577648008c5a75
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46323644"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Configuración de un cliente básico de Windows Communication Foundation

Esta es la quinta de las seis tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).

Este tema describe el archivo de configuración de cliente que se ha generado mediante la **Add Service Reference** funcionalidad de Visual Studio o el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). La configuración del cliente consiste en especificar el punto de conexión que utiliza el cliente para obtener acceso al servicio. Un punto de conexión tiene una dirección, un enlace y un contrato, y cada uno de ellos debe especificarse en el proceso de configuración del cliente.

## <a name="configure-a-windows-communication-foundation-client"></a>Configurar a un cliente de Windows Communication Foundation

Abra el archivo de configuración generado (App.config) del proyecto GettingStartedClient. El siguiente ejemplo es una vista del archivo de configuración generado. En el [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sección, busque la [ \<punto de conexión >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
          <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

Este ejemplo configura el punto de conexión que el cliente utiliza para tener acceso al servicio que se encuentra en la siguiente dirección: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.

El elemento de extremo especifica que el contrato de servicio de `ServiceReference1.ICalculator` se usa para la comunicación entre el cliente y el servicio de WCF. El canal de WCF se configura con el <xref:System.ServiceModel.WSHttpBinding> proporcionado por el sistema. Este contrato se generó mediante el uso de **Add Service Reference** en Visual Studio. Es básicamente una copia del contrato que se definió en el proyecto GettingStartedLib. El enlace <xref:System.ServiceModel.WSHttpBinding> especifica HTTP como el transporte, la seguridad interoperable y otros detalles de configuración.

Para obtener más información sobre cómo usar el cliente generado con esta configuración, consulte [Cómo: usar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Cómo: usar un cliente de WCF](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

## <a name="see-also"></a>Vea también

- [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)