---
title: Protección de clientes
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], security considerations
ms.assetid: 44c8578c-9a5b-4acd-8168-1c30a027c4c5
ms.openlocfilehash: bfb980e629ffb8f8543937a1850430c9bf6e9199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183130"
---
# <a name="securing-clients"></a>Protección de clientes
En Windows Communication Foundation (WCF), el servicio dicta los requisitos de seguridad para los clientes. Es decir, el servicio especifica qué modo de seguridad utilizar, y si el cliente debe proporcionar una credencial o no. El proceso de protección de un cliente, por consiguiente, es simple: utilice los metadatos obtenidos del servicio (si se publica) y cree un cliente. Los metadatos especifican cómo configurar el cliente. Si el servicio requiere que el cliente suministre una credencial, debe obtener una credencial que se ajuste al requisito. Este tema explica el proceso con más detalle. Para obtener más información acerca de cómo crear un servicio seguro, vea [Proteger servicios](securing-services.md).  
  
## <a name="the-service-specifies-security"></a>El servicio especifica la seguridad  
 De forma predeterminada, los enlaces WCF tienen habilitadas las características de seguridad. (La excepción <xref:System.ServiceModel.BasicHttpBinding>es el .) Por lo tanto, si el servicio se creó mediante WCF, hay una mayor probabilidad de que implemente la seguridad para garantizar la autenticación, confidencialidad e integridad. En ese caso, los metadatos que proporciona el servicio indicarán lo que se requiere para establecer un canal de comunicación seguro. Si los metadatos del servicio no incluyen ningún requisito de seguridad, no hay ninguna manera de imponer un esquema de seguridad, como Secure Sockets Layer (SSL) sobre HTTP, en un servicio. Si, sin embargo, el servicio requiere que el cliente proporcione una credencial, el desarrollador, implementador o administrador del cliente, debe proporcionar la credencial real que el cliente utilizará para autenticarse en el servicio.  
  
## <a name="obtaining-metadata"></a>Obtención de los metadatos  
 Al crear un cliente, el primer paso es obtener los metadatos para el servicio con el que el cliente se comunicará. Esto se puede llevar a cabo de dos maneras. En primer lugar, si el servicio publica un extremo de intercambio de metadatos (MEX) o hace que sus metadatos estén disponibles a través de HTTP o HTTPS, puede descargar los metadatos mediante la herramienta de utilidad de metadatos de [ServiceModel (Svcutil.exe),](servicemodel-metadata-utility-tool-svcutil-exe.md)que genera tanto archivos de código para un cliente como un archivo de configuración. (Para obtener más información sobre el uso de la herramienta, vea acceso a servicios [mediante un cliente WCF](accessing-services-using-a-wcf-client.md).) Si el servicio no publica un punto de conexión MEX y tampoco hace que sus metadatos estén disponibles a través de HTTP o HTTPS, debe ponerse en contacto con el creador del servicio para obtener documentación que describa los requisitos de seguridad y los metadatos.  
  
> [!IMPORTANT]
> Se recomienda que los metadatos procedan de una fuente de confianza y que no se manipulen. Los metadatos recuperados utilizando el protocolo HTTP se envían en texto no cifrado y se pueden manipular. Si el servicio utiliza <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> y las propiedades <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>, utilice la dirección URL que el creador del servicio proporcionó para descargar los datos mediante el protocolo HTTPS.  
  
## <a name="validating-security"></a>Validación de la seguridad  
 Las fuentes de metadatos pueden dividirse en dos amplias categorías: fuentes de confianza y fuentes que no son de confianza. Si confía en una fuente y se ha descargado el código de cliente y otros metadatos desde ese extremo MEX seguro de la fuente, puede crear el cliente, proporcionarle las credenciales correctas y ejecutarlo sin más preocupaciones.  
  
 Sin embargo, si elige descargar un cliente y metadatos desde un origen del que sabe poco, asegúrese de validar la las medidas de seguridad que utiliza el código. Por ejemplo, no debe crear simplemente un cliente que envíe su información personal o financiera a un servicio a menos que el servicio exija confidencialidad e integridad (como mínimo). Usted debe confiar en el propietario del servicio en la medida en que esté dispuesto a divulgar dicha información, ya que dicha información será visible para ellos.  
  
 Como regla, por consiguiente, al utilizar código y metadatos desde una fuente que no sea de confianza, compruebe el código y los metadatos para asegurarse de que cumple el nivel de seguridad que requiere.  
  
## <a name="setting-a-client-credential"></a>Establecimiento de una credencial de cliente  
 El establecimiento de una credencial de cliente en un cliente consta de dos pasos:  
  
1. Determine el tipo de credencial de *cliente que* requiere el servicio. Esto se logra mediante uno de los dos métodos de siguientes. Primero, si tiene documentación del creador del servicio, debería especificar el tipo de credencial de cliente (si hubiese) que el servicio requiere. Segundo, si solo tiene un archivo de configuración generado por la herramienta Svcutil.exe, puede examinar los enlaces individuales para determinar qué tipo de credencial se requiere.  
  
2. Especifique una credencial de cliente real. La credencial de cliente real se denomina valor de credencial de *cliente* para distinguirla del tipo. Por ejemplo, si el tipo de credencial de cliente especifica un certificado, debe proporcionar un certificado X.509 que emita una entidad de certificación en la que el servicio confíe.  
  
### <a name="determining-the-client-credential-type"></a>Determinación del tipo de credencial de cliente  
 Si tiene generado el archivo de configuración de la herramienta Svcutil.exe, examine los [ \<enlaces>](../configure-apps/file-schema/wcf/bindings.md) sección para determinar qué tipo de credencial de cliente es necesario. Dentro de la sección hay elementos de enlace que especifican los requisitos de seguridad. En concreto, \<examine la seguridad> elemento de cada enlace. Ese elemento incluye el atributo `mode`, que puede establecer en uno de tres valores posibles (`Message`, `Transport`o `TransportWithMessageCredential`). El valor del atributo determina el modo y el modo determina cuál de los elementos secundarios es significativo.  
  
 El `<security>` elemento puede `<transport>` contener `<message>` un elemento o o ambos. El elemento significativo es el que coincide con el modo de seguridad. Por ejemplo, el siguiente código especifica que el modo de seguridad es `"Message"`, y que el tipo de credencial de cliente para el elemento `<message>`. En este caso se puede ignorar el elemento `<transport>`. Sin embargo, el elemento `<message>` especifica que se debe proporcionar un certificado X.509.  

```xml  
<wsHttpBinding>  
    <binding name="WSHttpBinding_ICalculator">  
       <security mode="Message">  
           <transport clientCredentialType="Windows"
                      realm="" />  
           <message clientCredentialType="Certificate"
                    negotiateServiceCredential="true"  
                    algorithmSuite="Default"
                    establishSecurityContext="true" />  
       </security>  
    </binding>  
</wsHttpBinding>  
```  

 Tenga en cuenta que si el atributo `clientCredentialType` está establecido en `"Windows"`, tal y como se muestra en el ejemplo siguiente, no es necesario proporcionar un valor de credencial real. Esto se debe a que la seguridad integrada de Windows proporciona la credencial real (un token de Kerberos) de la persona que está ejecutando el cliente.  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows "
        realm="" />  
</security>  
```  
  
### <a name="setting-the-client-credential-value"></a>Establecimiento del valor de credencial de cliente  
 Si se determina que el cliente debe proporcionar una credencial, utilice el método adecuado para configurar el cliente. Por ejemplo, para establecer un certificado de cliente, utilice el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>.  
  
 Un formulario común de credencial es el certificado X.509. Puede proporcionar la credencial de dos maneras:  
  
- Programándolo en su código de cliente (mediante el método `SetCertificate` ).  
  
 Agregando [ \<](../configure-apps/file-schema/wcf/behaviors.md) un comportamiento>sección del archivo de `clientCredentials` configuración para el cliente y usando el elemento (que se muestra a continuación).  
  
#### <a name="setting-a-clientcredentials-value-in-code"></a>Establecer \<un valor de> clientCredentials en el código  
 Para establecer un <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> <xref:System.ServiceModel.ClientBase%601> [ \<valor de>clientCredentials](../configure-apps/file-schema/wcf/clientcredentials.md) en el código, debe tener acceso a la propiedad de la clase. La propiedad devuelve un objeto <xref:System.ServiceModel.Description.ClientCredentials> que permite el acceso a varios tipos de credenciales, tal y como se muestra en la tabla siguiente.  
  
|Propiedad ClientCredential|Descripción|Notas|  
|-------------------------------|-----------------|-----------|  
|<xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>|Devuelve una <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.|Representa un certificado X.509 proporcionado por el cliente para autenticarse en el servicio.|  
|<xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>|Devuelve una <xref:System.ServiceModel.Security.HttpDigestClientCredential>.|Representa una credencial de sintaxis de HTTP. La credencial es un hash del nombre de usuario y contraseña.|  
|<xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>|Devuelve una <xref:System.ServiceModel.Security.IssuedTokenClientCredential>.|Representa un token de seguridad personalizado emitido por un servicio de tokens de seguridad, utilizado normalmente en escenarios de federación.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>|Devuelve una <xref:System.ServiceModel.Security.PeerCredential>|Representa una credencial del mismo nivel para la participación en una malla del mismo nivel en un dominio de Windows.|  
|<xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>|Devuelve una <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>.|Representa un certificado X.509 proporcionado por el servicio en una negociación fuera de banda.|  
|<xref:System.ServiceModel.Description.ClientCredentials.UserName%2A>|Devuelve una <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>|Representa un par de nombre de usuario y contraseña.|  
|<xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>|Devuelve una <xref:System.ServiceModel.Security.WindowsClientCredential>|Representa una credencial de cliente de Windows (una credencial de Kerberos). Las propiedades de la clase son de solo lectura.|  
  
#### <a name="setting-a-clientcredentials-value-in-configuration"></a>Establecer \<un valor de> clientCredentials en la configuración  
 Los valores de credenciales se especifican mediante un comportamiento de punto de conexión como elementos secundarios del [ \<elemento clientCredentials>.](../configure-apps/file-schema/wcf/clientcredentials.md) El elemento utilizado depende del tipo de credencial de cliente. Por ejemplo, en el ejemplo siguiente se muestra la configuración para establecer un certificado X.509 mediante la <[ \<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>
        <behavior name="myEndpointBehavior">  
          <clientCredentials>  
            <clientCertificate findvalue="myMachineName"
            storeLocation="Current" X509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>
      </endpointBehaviors>
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
 Para establecer la credencial de cliente en la configuración, agregue un [ \<elemento de>endpointBehaviors](../configure-apps/file-schema/wcf/endpointbehaviors.md) al archivo de configuración. Además, el elemento de comportamiento agregado debe estar `behaviorConfiguration` vinculado al punto de conexión del servicio mediante el atributo del [ \<punto \<](../configure-apps/file-schema/wcf/endpoint-of-client.md) de conexión> del elemento de>de cliente, como se muestra en el ejemplo siguiente. El valor del atributo `behaviorConfiguration` debe coincidir con el valor del atributo `name` del comportamiento.  

```xml
<configuration>
  <system.serviceModel>
    <client>
      <endpoint address="http://localhost/servicemodelsamples/service.svc"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                behaviorConfiguration="myEndpointBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```
  
> [!NOTE]
> Algunos de los valores de credenciales de cliente no se pueden establecer utilizando los archivos de configuración de la aplicación, por ejemplo, el nombre de usuario y la contraseña, o los valores de usuario y contraseña de Windows. Tales valores de credenciales solo se pueden especificarse mediante código.  
  
 Para obtener más información acerca de cómo establecer la credencial de cliente, vea [Cómo: Especificar valores](how-to-specify-client-credential-values.md)de credenciales de cliente .  
  
> [!NOTE]
> Se omite `ClientCredentialType` cuando `SecurityMode` está establecido en `"TransportWithMessageCredential",` tal y como se muestra en la configuración del ejemplo siguiente.  
  
```xml  
<wsHttpBinding>  
    <binding name="PingBinding">  
        <security mode="TransportWithMessageCredential"  >  
           <message  clientCredentialType="UserName"
               establishSecurityContext="false"
               negotiateServiceCredential="false" />  
           <transport clientCredentialType="Certificate"  />  
         </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [\<encuadernaciones>](../configure-apps/file-schema/wcf/bindings.md)
- [Herramienta del editor de configuración (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)
- [Seguridad de servicios](securing-services.md)
- [Acceso a los servicios mediante un cliente WCF](accessing-services-using-a-wcf-client.md)
- [Cómo especificar los valores de credenciales de cliente](how-to-specify-client-credential-values.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Cómo especificar el tipo de credencial de cliente](how-to-specify-the-client-credential-type.md)
