---
description: Más información acerca de cómo configurar un servicio de Windows Communication Foundation para usar el uso compartido de puertos
title: 'Cómo: Configurar un servicio de Windows Communication Foundation para utilizar puertos compartidos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
ms.openlocfilehash: 53fe3449ece5a5e545d7add5c4e6c7feebe5a8ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780107"
---
# <a name="how-to-configure-a-windows-communication-foundation-service-to-use-port-sharing"></a>Cómo: Configurar un servicio de Windows Communication Foundation para utilizar puertos compartidos

La manera más sencilla de utilizar el uso compartido de puertos net. TCP://en la aplicación Windows Communication Foundation (WCF) es exponer un servicio mediante <xref:System.ServiceModel.NetTcpBinding> .  
  
 Este enlace proporciona una propiedad <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> que controla si la compartición de puertos de net.tcp:// está habilitada para el servicio que se está configurando con este enlace.  
  
 El siguiente procedimiento muestra cómo utilizar la clase <xref:System.ServiceModel.NetTcpBinding> para abrir un punto de conexión en el URI net.tcp://localhost/MyService, primero mediante código y, a continuación, mediante los elementos de configuración.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-code"></a>Para habilitar la compartición de puertos de net.tcp:// en un NetTcpBinding mediante código  
  
1. Cree un servicio para implementar un contrato llamado `IMyService` y llámelo `MyService` .  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2. Cree una instancia de la clase <xref:System.ServiceModel.NetTcpBinding> y establezca la propiedad <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> en `true`.  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3. Cree un <xref:System.ServiceModel.ServiceHost> y agregue el punto de conexión de servicio a él para `MyService` que utiliza el <xref:System.ServiceModel.NetTcpBinding> con uso compartido de puerto habilitado y que realiza escuchas en el URI de la dirección del punto de conexión "net.tcp://localhost/MyService".  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    > Este ejemplo utiliza el puerto TCP predeterminado 808, porque el URI de dirección de punto de conexión no especifica un número de puerto diferente. Dado que el uso compartido del puerto está habilitado explícitamente en el enlace de transporte, este servicio puede compartir el puerto 808 con otros servicios en otros procesos. Si no se permitiera el uso compartido del puerto y otra aplicación ya estuviese utilizando el puerto 808, este servicio produciría una <xref:System.ServiceModel.AddressAlreadyInUseException> al abrirse.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-configuration"></a>Para habilitar el uso compartido de puerto de  net.tcp:// en un NetTcpBinding mediante configuración  
  
1. El ejemplo siguiente muestra cómo habilitar el uso compartido de puerto y agregar el punto de conexión de servicio mediante elementos de configuración.  
  
```xml  
<system.serviceModel>  
  <bindings>  
    <netTcpBinding name="portSharingBinding"
                   portSharingEnabled="true" />  
  </bindings>  
  <services>  
    <service name="MyService">  
        <endpoint address="net.tcp://localhost/MyService"  
                  binding="netTcpBinding"  
                  contract="IMyService"  
                  bindingConfiguration="portSharingBinding" />  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Vea también

- [Uso compartido de puertos Net.TCP](net-tcp-port-sharing.md)
- [Procedimiento para habilitar el servicio de uso compartido de puertos Net.TCP](how-to-enable-the-net-tcp-port-sharing-service.md)
