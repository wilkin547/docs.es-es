---
title: Procedimiento para crear un enlace personalizado de sesión confiable con HTTPS
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 7f22eeaae39b4d9a83c77c7f3e9db1d7d3f04e8e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895201"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Procedimiento para crear un enlace personalizado de sesión confiable con HTTPS

En este tema se muestra el uso de la seguridad de transporte de capa de sockets seguros (SSL) con sesiones confiables. Para utilizar una sesión confiable sobre HTTPS, debe crear un enlace personalizado que utilice una sesión confiable y el transporte de HTTPS. Puede habilitar la sesión confiable de manera imperativa mediante el uso de código o mediante declaración en el archivo de configuración. Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión confiable y el elemento [ **\<> de httpsTransport**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) .

La parte clave de este procedimiento es que el  **\<punto de conexión >** elemento de `bindingConfiguration` configuración contiene un atributo que hace referencia a `reliableSessionOverHttps`una configuración de enlace personalizada denominada. El elemento de configuración de [ **\<enlace >** ](../../../../docs/framework/misc/binding.md) hace referencia a este nombre para especificar que se usan una sesión confiable y el transporte https incluyendo  **\<reliableSession >** y **\<httpsTransport >** elementos.

Para la copia de origen de este ejemplo, consulte el [enlace personalizado de la sesión confiable sobre https](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Configurar el servicio con un CustomBinding para utilizar una sesión confiable con HTTPS

1. Defina un contrato de servicios para el tipo de servicio.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Implemente el contrato de servicios en una clase de servicio. Tenga en cuenta que la información de dirección o enlace no se especifica dentro de la implementación del servicio. No es necesario escribir código para recuperar la dirección o la información de enlace del archivo de configuración.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Cree un archivo *Web. config* para configurar un extremo para el `CalculatorService` con un enlace personalizado denominado `reliableSessionOverHttps` que use una sesión confiable y el transporte https.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Cree un archivo *Service. SVC* que contenga la línea:

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. Coloque el archivo *Service. SVC* en el directorio virtual de Internet Information Services (IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Configurar el cliente con un CustomBinding para utilizar una sesión confiable con HTTPS

1. Use la [herramienta de utilidad de metadatos de ServiceModel (*SvcUtil. exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. El cliente que se genera contiene la `ICalculator` interfaz que define el contrato de servicio que la implementación del cliente debe cumplir.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. La aplicación de cliente generada también contiene la implementación de `ClientCalculator`. Tenga en cuenta que la información de dirección y enlace no se especifica dentro de la implementación del servicio. No es necesario escribir código para recuperar la dirección y la información de enlace del archivo de configuración.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Configure un enlace personalizado `reliableSessionOverHttps` denominado para usar el transporte https y las sesiones de confianza.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Compile y ejecute el cliente.  

## <a name="net-framework-security"></a>seguridad en .NET Framework

Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con *Makecert. exe*, aparecerá una alerta de seguridad al intentar obtener acceso a una dirección https `https://localhost/servicemodelsamples/service.svc`, como, desde el explorador.

## <a name="see-also"></a>Vea también

- [Sesiones de confianza](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
