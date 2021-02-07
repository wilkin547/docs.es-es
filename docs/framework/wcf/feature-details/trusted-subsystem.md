---
description: 'Más información acerca de: subsistema de confianza'
title: Subsistema de confianza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f5ce46b-e259-4bc9-a0b9-89d06fc9341c
ms.openlocfilehash: 41c2943c7794206dba06ef8b5bbee762931ce0c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733052"
---
# <a name="trusted-subsystem"></a>Subsistema de confianza

Un cliente obtiene acceso a uno o varios servicios Web distribuidos a través de una red. Los servicios Web están diseñados para que el acceso a recursos adicionales (como bases de datos u otros servicios Web) se encapsule en la lógica empresarial del servicio Web. Estos recursos deben protegerse frente al acceso no autorizado. La siguiente ilustración describe un proceso de subsistema de confianza.  
  
 ![Subsistema de confianza](media/wcfc-trustedsubsystemc.gif "wcfc_TrustedSubsystemc")  
  
 Los siguientes pasos describen el proceso del subsistema de confianza tal y como se ilustra:  
  
1. El cliente envía una solicitud al subsistema de confianza, junto con las credenciales.  
  
2. El subsistema de confianza autentica y autoriza al usuario.  
  
3. El subsistema de confianza envía un mensaje de solicitud al recurso remoto. Las credenciales acompañan a esta solicitud para el subsistema de confianza (o la cuenta de servicio bajo la que se ejecuta el proceso del subsistema de confianza).  
  
4. El recurso de back-end autentica y autoriza al subsistema de confianza. A continuación, procesa la solicitud y emite una respuesta al subsistema de confianza.  
  
5. El subsistema de confianza procesa la respuesta y emite su propia respuesta al cliente.  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Modo de seguridad|Message|  
|Interoperabilidad|Solo Windows Communication Foundation (WCF).|  
|Autenticación (servicio)|El servicio de token de seguridad autentica y autoriza clientes.|  
|Autenticación (cliente)|El subsistema de confianza autentica al cliente y el recurso autentica al servicio del subsistema de confianza.|  
|Integridad|Sí|  
|Confidencialidad|Sí|  
|Transporte|HTTP entre el cliente y el servicio del subsistema de confianza.<br /><br /> NET.TCP entre el servicio del subsistema de confianza y el recurso (servicio back-end).|  
|Enlace|<xref:System.ServiceModel.WSHttpBinding> etc <xref:System.ServiceModel.NetTcpBinding>[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|  
  
## <a name="resource-back-end-service"></a>Recurso (servicio back-end)  
  
### <a name="code"></a>Código  

 El siguiente código muestra cómo crear un punto de conexión de servicio para el recurso, que utiliza seguridad de transporte a través del protocolo de transporte de TCP.  
  
 [!code-csharp[TrustedSubSystemsResource#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsresource/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsResource#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsresource/vb/source.vb#1)]  
  
### <a name="configuration"></a>Configuración  

 La siguiente configuración define el mismo punto de conexión mediante configuración.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.BackendService"  
               behaviorConfiguration="BackendServiceBehavior">  
        <endpoint address="net.tcp://localhost.com:8001/BackendService"  
                  binding="customBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <bindings>  
      <customBinding>  
        <binding name="Binding1">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="BackendServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, BackendService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="trusted-subsystem"></a>Subsistema de confianza  
  
### <a name="code"></a>Código  

 El siguiente código muestra cómo crear un extremo de servicio para el subsistema de confianza que utiliza el modo de seguridad sobre el protocolo HTTP y un nombre de usuario y contraseña para la autenticación.  
  
 [!code-csharp[TrustedSubSystems#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#1)]
 [!code-vb[TrustedSubSystems#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#1)]  
  
 El siguiente código muestra un servicio en un subsistema de confianza que se comunica con un servicio back-end utilizando seguridad de transporte a través del protocolo de transporte de TCP.  
  
 [!code-csharp[TrustedSubSystems#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystems/cs/source.cs#2)]
 [!code-vb[TrustedSubSystems#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystems/vb/source.vb#2)]  
  
### <a name="configuration"></a>Configuración  

 La siguiente configuración define el mismo punto de conexión mediante configuración. Tenga en cuenta los dos enlaces: uno protege el servicio que se hospeda en el subsistema de confianza y el otro comunica entre el subsistema de confianza y el servicio back-end.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.FacadeService"  
               behaviorConfiguration="FacadeServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/FacadeService"/>  
          </baseAddresses>  
        </host>  
        <endpoint address="http://localhost:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
      </service>  
    </services>  
    <client>  
      <endpoint name=""
                address="net.tcp://contoso.com:8001/BackendService"  
                binding="customBinding"  
                bindingConfiguration="ClientBinding"  
                contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
      <customBinding>  
        <binding name="ClientBinding">  
          <security authenticationMode="UserNameOverTransport"/>  
          <windowsStreamSecurity/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="FacadeServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                storeLocation="LocalMachine"  
                                storeName="My"  
                                x509FindType="FindBySubjectName" />  
            <userNameAuthentication userNamePasswordValidationMode="Custom"  
                                    customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator, FacadeService"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Cliente  
  
### <a name="code"></a>Código  

 El siguiente código muestra cómo crear el cliente que comunica con el subsistema de confianza utilizando la seguridad de mensaje sobre el protocolo HTTP y un nombre de usuario y contraseña para la autenticación.  
  
 [!code-csharp[TrustedSubSystemsClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/trustedsubsystemsclient/cs/source.cs#1)]
 [!code-vb[TrustedSubSystemsClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/trustedsubsystemsclient/vb/source.vb#1)]  
  
### <a name="configuration"></a>Configuración  

 El siguiente código configura el cliente para utilizar la seguridad de mensaje sobre el protocolo HTTP y un nombre de usuario y contraseña para la autenticación. El nombre de usuario y la contraseña solo se pueden especificar mediante código (no es configurable).  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <client>  
        <endpoint name=""
                  address="http://www.cohowinery.com:8000/FacadeService"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientUserNameBehavior"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator"/>  
    </client>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientUserNameBehavior">  
          <clientCredentials>  
            <serviceCertificate>  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](security-overview.md)
- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
