---
title: "C&#243;mo utilizar seguridad de transporte y credenciales de mensajes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TransportWithMessageCredentials"
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
caps.latest.revision: 11
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 11
---
# C&#243;mo utilizar seguridad de transporte y credenciales de mensajes
Proteger un servicio con credenciales de mensajes y transporte emplea lo mejor de los modos de seguridad de mensajes y transporte en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].En suma, la seguridad de la capa de transporte proporciona integridad y confidencialidad, mientras que la seguridad de la capa de mensaje proporciona una variedad de credenciales que no son posibles con mecanismos de seguridad de transporte estrictos.En este tema se muestran los pasos básicos para implementar transporte con credenciales de mensaje usando los enlaces <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.NetTcpBinding>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo establecer el modo de seguridad, vea [Cómo: Establecer el modo de seguridad](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
 Al establecer el modo de seguridad como `TransportWithMessageCredential`, el transporte determina el mecanismo real que proporciona la seguridad de nivel de transporte.Para HTTP, el mecanismo es Secure Sockets Layer \(SSL\) sobre HTTP \(HTTPS\); para TCP, es SSL sobre TCP o Windows.  
  
 Si el transporte es HTTP \(utilizando <xref:System.ServiceModel.WSHttpBinding>\), SSL sobre HTTP proporciona la seguridad de nivel de transporte.En ese caso, debe configurar el equipo que aloja el servicio con un certificado SSL enlazado a un puerto, tal y como se muestra más adelante en este tema.  
  
 Si el transporte es TCP \(utilizando <xref:System.ServiceModel.NetTcpBinding>\), la seguridad de nivel de transporte proporcionada es, de forma predeterminada, seguridad de Windows, o SSL sobre TCP.Al utilizar SSL sobre TCP, debe especificar el certificado mediante el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>, tal y como se muestra más adelante en este tema.  
  
### Para utilizar WSHttpBinding con un certificado para la seguridad de transporte \(en código\)  
  
1.  Utilice la herramienta HttpCfg.exe para enlazar un certificado SSL a un puerto en el equipo.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: Configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
2.  Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> como <xref:System.ServiceModel.SecurityMode>.  
  
3.  Establezca la propiedad <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> con un valor apropiado.\([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Selección de tipos de credenciales](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).\) El siguiente código usa el valor <xref:System.ServiceModel.MessageCredentialType>.  
  
4.  Cree una instancia de la clase <xref:System.Uri> con una dirección base apropiada.Observe que la dirección debe utilizar el esquema "HTTPS" y contener el nombre real del equipo y el número de puerto al que se enlaza el certificado SSL.\(De manera alternativa, puede establecer la dirección base mediante configuración.\)  
  
5.  Agregue un extremo de servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
6.  Cree la instancia del <xref:System.ServiceModel.ServiceHost> y llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>, tal y como se muestra en el código siguiente.  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### Para usar el NetTcpBinding con un certificado para la seguridad de transporte \(en código\)  
  
1.  Cree una instancia de la clase <xref:System.ServiceModel.NetTcpBinding> y establezca la propiedad <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> como <xref:System.ServiceModel.SecurityMode>.  
  
2.  Establezca un valor adecuado para la propiedad <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A>.El siguiente código usa el valor <xref:System.ServiceModel.MessageCredentialType>.  
  
3.  Cree una instancia de la clase <xref:System.Uri> con una dirección base apropiada.Observe que la dirección debe utilizar el esquema "net.tcp."\(De manera alternativa, puede establecer la dirección base mediante configuración.\)  
  
4.  Cree la instancia de la clase <xref:System.ServiceModel.ServiceHost>.  
  
5.  Utilice el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> para establecer explícitamente el certificado X.509 para el servicio.  
  
6.  Agregue un extremo de servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
7.  Llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>, tal y como se indica en el siguiente código.  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### Para utilizar NetTcpBinding con Windows para la seguridad de transporte \(en código\)  
  
1.  Cree una instancia de la clase <xref:System.ServiceModel.NetTcpBinding> y establezca la propiedad <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> en <xref:System.ServiceModel.SecurityMode>.  
  
2.  Establezca la seguridad de transporte para que utilice Windows estableciendo el <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> como <xref:System.ServiceModel.TcpClientCredentialType>.\(Observe que se trata del valor predeterminado\).  
  
3.  Establezca un valor adecuado para la propiedad <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A>.El siguiente código usa el valor <xref:System.ServiceModel.MessageCredentialType>.  
  
4.  Cree una instancia de la clase <xref:System.Uri> con una dirección base apropiada.Observe que la dirección debe utilizar el esquema "net.tcp."\(De manera alternativa, puede establecer la dirección base mediante configuración.\)  
  
5.  Cree la instancia de la clase <xref:System.ServiceModel.ServiceHost>.  
  
6.  Utilice el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> para establecer explícitamente el certificado X.509 para el servicio.  
  
7.  Agregue un extremo de servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
8.  Llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>, como se muestra en el siguiente código.  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## Uso de la configuración  
  
#### Para usar el WSHttpBinding  
  
1.  Configure el equipo con un certificado SSL enlazado a un puerto.\([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: Configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)\).No necesita establecer un valor de elemento \<`transport`\> con esta configuración.  
  
2.  Especifique el tipo de credencial de cliente para la seguridad del nivel de mensaje.El siguiente ejemplo establece el atributo `clientCredentialType` del elemento \<`message`\> como `UserName`.  
  
    ```  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### Para usar el NetTcpBinding con un certificado para la seguridad de transporte  
  
1.  Para SSL sobre TCP, debe especificar explícitamente el certificado en el elemento `<behaviors>`.El siguiente ejemplo especifica un certificado por su emisor en la ubicación de almacén predeterminada \(equipo local y almacenes personales\).  
  
    ```  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2.  Agregue un [\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) a la sección de enlaces  
  
3.  Agregue un elemento de enlace y establezca un valor apropiado para el atributo `name`.  
  
4.  Agregue un elemento \<`security`\> y establezca el atributo `mode` como `TransportWithMessageCredential`.  
  
5.  Agregue un elemento \<`message>` `y establezca el atributo clientCredentialType` con un valor adecuado.  
  
    ```  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### Para utilizar NetTcpBinding con Windows para la seguridad de transporte  
  
1.  Agregue un [\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) a la sección de enlaces,  
  
2.  Agregue un elemento \<`binding`\> y establezca el atributo `name` con un valor adecuado.  
  
3.  Agregue un elemento \<`security`\> y establezca el atributo `mode` como `TransportWithMessageCredential`.  
  
4.  Agregue un elemento \<`transport`\> y establezca el atributo `clientCredentialType` como `Windows`.  
  
5.  Agregue un elemento \<`message`\> y establezca el atributo `clientCredentialType` con un valor adecuado.El siguiente código establece el valor para un certificado.  
  
    ```  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
  
    ```  
  
## Vea también  
 [Cómo: Establecer el modo de seguridad](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)   
 [Seguridad de servicios](../../../../docs/framework/wcf/securing-services.md)   
 [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)