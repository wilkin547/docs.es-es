---
title: Creación de un enlace personalizado de sesión confiable con HTTPS
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: b3699593f783fff1227ec51194956e0cc8577dd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492767"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Creación de un enlace personalizado de sesión confiable con HTTPS

En este tema se muestra el uso de la seguridad de transporte de capa de sockets seguros (SSL) con sesiones confiables. Para utilizar una sesión confiable sobre HTTPS, debe crear un enlace personalizado que utilice una sesión confiable y el transporte de HTTPS. Habilitar la sesión confiable de manera imperativa mediante código o mediante declaración en el archivo de configuración. Este procedimiento utiliza los archivos de configuración de cliente y servicio para habilitar la sesión confiable y [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) elemento.

La parte clave de este procedimiento es que la  **\<extremo >** elemento de configuración contienen un `bindingConfiguration` atributo que hace referencia a una configuración de enlace personalizado denominada `reliableSessionOverHttps`. El [  **\<enlace >** ](../../../../docs/framework/misc/binding.md) elemento de configuración hace referencia a este nombre para especificar que se utilizan una sesión confiable y el transporte HTTPS mediante la inclusión de  **\< reliableSession >** y  **\<httpsTransport >** elementos.

Para la copia de origen de este ejemplo, vea [personalizado de enlace sesión confiable sobre HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Configurar el servicio con un CustomBinding para utilizar una sesión confiable con HTTPS

1. Defina un contrato de servicios para el tipo de servicio.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Implemente el contrato de servicios en una clase de servicio. Tenga en cuenta que no se especifica la información de dirección o enlace dentro de la implementación del servicio. No es necesario escribir código para recuperar la información de dirección o enlace desde el archivo de configuración.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Crear un *Web.config* archivo para configurar un extremo para la `CalculatorService` con un enlace personalizado denominado `reliableSessionOverHttps` que utiliza una sesión confiable y el transporte HTTPS.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Crear un *Service.svc* archivo que contiene la línea:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Lugar la *Service.svc* archivo en el directorio virtual de Internet Information Services (IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Configurar al cliente con un CustomBinding para utilizar una sesión confiable con HTTPS

1. Use la [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de metadatos del servicio.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. El cliente que se genera contiene la `ICalculator` interfaz que define el contrato de servicio que debe satisfacer la implementación del cliente.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. La aplicación de cliente generada también contiene la implementación de `ClientCalculator`. Tenga en cuenta que no se especifica la información de enlace y dirección de la implementación del servicio. No es necesario escribir código para recuperar la información de enlace y la dirección del archivo de configuración.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Configurar un enlace personalizado denominado `reliableSessionOverHttps` para usar el transporte HTTPS y sesiones confiables.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Compile y ejecute el cliente.  

## <a name="net-framework-security"></a>seguridad en .NET Framework

Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con *Makecert.exe*, aparecerá una alerta de seguridad cuando intenta tener acceso a una dirección HTTPS, como `https://localhost/servicemodelsamples/service.svc`, desde el explorador.

## <a name="see-also"></a>Vea también

[Sesiones de confianza](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
