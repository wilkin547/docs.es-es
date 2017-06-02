---
title: "Cliente y servicio de intranet no protegidos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
caps.latest.revision: 20
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 20
---
# Cliente y servicio de intranet no protegidos
La ilustración siguiente describe un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] simple desarrollado para proporcionar información sobre una red privada segura a una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  No se requiere seguridad porque los datos son de poca importancia, se supone que la red es intrínsecamente segura, o que la seguridad la proporciona una capa situada por debajo de la infraestructura [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 ![Escenario de cliente y servicio de intranet no protegido](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Modo de seguridad|Ninguna|  
|Transporte|TCP|  
|Enlaces|<xref:System.ServiceModel.NetTcpBinding>|  
|Interoperabilidad|Solo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]|  
|Autenticación|Ninguna|  
|Integridad|Ninguna|  
|Confidencialidad|Ninguna|  
  
## Servicio  
 El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.  Realice una de las siguientes acciones:  
  
-   Cree un servicio independiente mediante el código sin configuración.  
  
-   Cree un servicio mediante la configuración proporcionada, pero sin definir ningún extremo.  
  
### Código  
 El siguiente código muestra cómo crear un extremo sin seguridad:  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### Configuración  
 El código siguiente establece el mismo extremo utilizando la configuración.  
  
```  
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
  
## Cliente  
 El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.  Realice una de las siguientes acciones:  
  
-   Cree un cliente independiente mediante el código \(y el código de cliente\).  
  
-   Cree un cliente que no defina direcciones de extremo.  En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento.  Por ejemplo:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### Código  
 El código siguiente muestra un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] básico que puede acceder a un extremo sin protección mediante el protocolo TCP.  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### Configuración  
 El código de configuración siguiente se aplica al cliente:  
  
```  
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
  
## Vea también  
 <xref:System.ServiceModel.NetTcpBinding>   
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Seguridad y protección](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)