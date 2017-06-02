---
title: "Elemento &lt;transport&gt; de &lt;basicHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Elemento &lt;transport&gt; de &lt;basicHttpBinding&gt;
Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.  
  
## Sintaxis  
  
```  
<basicHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</basicHttpBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|clientCredentialType|-   Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente mediante la autenticación de HTTP.  De manera predeterminada, es `None`.  Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|-   Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente desde un dominio utilizando un proxy sobre HTTP.  Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.  Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.  El valor predeterminado es una cadena vacía.|  
|policyEnforcement|Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtectionPolicy>.<br /><br /> 1.  Never: la directiva nunca se aplica \(la protección extendida está deshabilitada\).<br />2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.<br />3.  Always: la directiva siempre se aplica.  Los clientes que no admitan la protección extendida no podrán autenticarse.|  
|protectionScenario|Esta enumeración especifica el escenario de protección que exige la directiva.|  
  
## Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|Los mensajes no se protegen durante la transferencia.|  
|Básico|Especifica la autenticación básica.|  
|Implícita|Especifica la autenticación implícita.|  
|Ntlm|Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.|  
|Windows|Especifica la autenticación de Windows integrada.|  
  
## Atributo proxyCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|-   Los mensajes no se protegen durante la transferencia.|  
|Básico|Especifica la autenticación básica como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita.|  
|Implícita|Especifica la autenticación implícita como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita|  
|Ntlm|Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.|  
|Windows|Especifica la autenticación de Windows integrada.|  
|Certificado|Realiza la autenticación del cliente mediante un certificado.  Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Define las funciones de seguridad para [\<basicHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).|  
  
## Ejemplo  
 El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.  De forma predeterminada, el enlace básico soporta la comunicación HTTP.  
  
```  
<system.serviceModel>  
   <services>  
      <service   
          type="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
         <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
   </services>  
    <bindings>  
        <basicHttpBinding>  
        <!-- Configure basicHttpBinding with Transport security -- >  
        <!-- mode and clientCredentialType set to None.-->  
           <binding name="Binding1">  
               <security mode="Transport">  
                   <transport clientCredentialType="None"  
                              proxyCredentialType="None">  
                       <extendedProtectionPolicy  
                          policyEnforcement="WhenSupported"  
                          protectionScenario="TransportSelected">  
                    <customServiceNames></customServiceNames>  
                       </extendedProtectionPolicy>  
               </security>  
           </binding>  
        </basicHttpBinding>  
    </bindings>  
</system.serviceModel>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>   
 <xref:System.ServiceModel.HttpTransportSecurity>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)