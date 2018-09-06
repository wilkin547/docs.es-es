---
title: Intercambio de mensajes dentro de una sesión confiable
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 6b204749ce86b79bf46b2d5c96be1b00dca9500d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037381"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Intercambio de mensajes dentro de una sesión confiable

En este tema se describen los pasos necesarios para habilitar una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada. Habilitar una sesión confiable de manera imperativa mediante código o mediante declaración en el archivo de configuración. Este procedimiento utiliza los archivos de configuración de cliente y servicio para habilitar la sesión confiable y para estipular que los mensajes lleguen en el mismo orden en que se enviaron.

La parte clave de este procedimiento es que el elemento de configuración de punto de conexión contienen un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada `Binding1`. El [  **\<enlace >** ](../../../../docs/framework/misc/binding.md) elemento de configuración hace referencia a este nombre para habilitar sesiones confiables estableciendo el `enabled` atributo de la [  **\<reliableSession >** ](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`. Especifica las garantías de entrega ordenada de la sesión confiable estableciendo el atributo `ordered` en `true`.

Para la copia de origen de este ejemplo, vea [sesión confiable WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar el servicio con WSHttpBinding para utilizar una sesión confiable

1. Defina un contrato de servicios para el tipo de servicio.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Implemente el contrato de servicios en una clase de servicio. Tenga en cuenta que no se especifica la información de dirección o enlace dentro de la implementación del servicio. No es necesario escribir código para recuperar la información de dirección o enlace información del archivo de configuración.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Crear un *Web.config* archivo para configurar un punto de conexión para el `CalculatorService` que usa el <xref:System.ServiceModel.WSHttpBinding> con sesión confiable habilitada y entrega ordenada de mensajes necesarios.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Crear un *Service.svc* archivo que contiene la línea:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  Colocar el *Service.svc* archivo en el directorio virtual de Internet Information Services (IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar al cliente con un WSHttpBinding para utilizar una sesión confiable

1. Use la [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio:

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. El cliente generado contiene la `ICalculator` interfaz que define el contrato de servicio que debe cumplir la implementación del cliente.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. La aplicación de cliente generada también contiene la implementación de `ClientCalculator`. Tenga en cuenta que la información de dirección y el enlace no se especifica en cualquier lugar dentro de la implementación del servicio. No es necesario escribir código para recuperar la información de dirección o enlace información del archivo de configuración.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil.exe* también genera la configuración para el cliente que usa el <xref:System.ServiceModel.WSHttpBinding> clase. Nombre del archivo de configuración *App.config* cuando se usa Visual Studio.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Cree una instancia de la `ClientCalculator` en una aplicación y llamar a las operaciones de servicio.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Compile y ejecute el cliente.

## <a name="example"></a>Ejemplo

Algunos de los enlaces proporcionados por el sistema admiten de forma predeterminada las sesiones confiables. Se incluyen los siguientes:

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Para obtener un ejemplo de cómo crear un enlace personalizado que admite sesiones confiables, vea [Cómo: crear un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>Vea también

[Sesiones de confianza](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
