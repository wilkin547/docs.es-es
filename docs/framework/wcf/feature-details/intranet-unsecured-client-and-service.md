---
title: Cliente y servicio de intranet no protegidos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: 591f7db0f6b4e928a991961d3bc7c404f41028bf
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579285"
---
# <a name="intranet-unsecured-client-and-service"></a>Cliente y servicio de intranet no protegidos
En la ilustración siguiente se muestra un servicio de Windows Communication Foundation simple (WCF) desarrollado para proporcionar información sobre una red privada segura a una aplicación WCF. No es necesaria la seguridad porque los datos son de poca importancia, se espera que la red sea intrínsecamente segura, o bien la seguridad la proporciona una capa por debajo de la infraestructura de WCF.  
  
 ![Escenario de servicio y cliente no seguro de la intranet.](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Modo de seguridad|None|  
|Transporte|TCP|  
|Enlace|<xref:System.ServiceModel.NetTcpBinding>|  
|Interoperabilidad|Solo WCF|  
|Authentication|None|  
|Integridad|None|  
|Confidencialidad|None|  
  
## <a name="service"></a>web de Office  
 El código y la configuración siguientes están diseñados para ejecutarse de forma independiente. Lleve a cabo una de las siguientes acciones:  
  
- Cree un servicio independiente mediante el código sin configuración.  
  
- Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.  
  
### <a name="code"></a>Código  
 El siguiente código muestra cómo crear un extremo sin seguridad:  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a>Configuración  
 El código siguiente establece el mismo extremo utilizando la configuración.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Cliente  
 El código y la configuración siguientes están diseñados para ejecutarse de forma independiente. Lleve a cabo una de las siguientes acciones:  
  
- Cree un cliente independiente mediante el código (y el código de cliente).  
  
- Cree un cliente que no defina direcciones de punto de conexión. En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento. Por ejemplo:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>Código  
 En el código siguiente se muestra un cliente de WCF básico que tiene acceso a un punto de conexión no seguro mediante el protocolo TCP.  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a>Configuración  
 El código de configuración siguiente se aplica al cliente:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.NetTcpBinding>
- [Información general sobre seguridad](security-overview.md)
- [Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
