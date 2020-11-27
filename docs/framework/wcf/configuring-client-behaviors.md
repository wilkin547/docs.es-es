---
title: Configuración de los comportamientos del cliente
description: 'Obtenga información sobre las dos formas en que WCF configura los comportamientos: en el archivo de configuración de la aplicación o mediante programación desde la aplicación que realiza la llamada.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 34cbb9e31933debb5120eb30956c3a5f0be065ed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266719"
---
# <a name="configuring-client-behaviors"></a>Configuración de los comportamientos del cliente

Windows Communication Foundation (WCF) configura los comportamientos de dos maneras: mediante la referencia a las configuraciones de comportamiento, que se definen en la `<behavior>` sección de un archivo de configuración de la aplicación cliente, o mediante programación en la aplicación que realiza la llamada. En este tema se describen ambos métodos.  
  
 Al usar un archivo de configuración, la configuración del comportamiento es una colección con nombre de valores de configuración. El nombre de cada configuración de comportamiento debe ser único. Esta cadena se usa en el atributo `behaviorConfiguration` de una configuración de punto de conexión para vincular el punto de conexión al comportamiento.  
  
## <a name="example"></a>Ejemplo  

 El código de configuración siguiente define un comportamiento llamado `myBehavior`. El punto de conexión de cliente hace referencia a este comportamiento en el atributo `behaviorConfiguration`.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a>Uso de comportamientos mediante programación  

 También puede configurar o insertar comportamientos mediante programación localizando la `Behaviors` propiedad adecuada en el objeto de cliente Windows Communication Foundation (WCF) o en el objeto de generador de canales de cliente antes de abrir el cliente.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se muestra cómo insertar un comportamiento mediante programación teniendo acceso a la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> en el <xref:System.ServiceModel.Description.ServiceEndpoint> devuelto por la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> antes de la creación del objeto del canal.  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>Vea también

- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
