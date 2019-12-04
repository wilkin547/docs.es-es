---
title: Proveedor de token emitido duradero
ms.date: 03/30/2017
ms.assetid: 76fb27f5-8787-4b6a-bf4c-99b4be1d2e8b
ms.openlocfilehash: 62e4cca50e9a2fbbf319d66fbe85cec6cdb73b23
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716458"
---
# <a name="durable-issued-token-provider"></a>Proveedor de token emitido duradero
Este ejemplo muestra cómo implementar un proveedor personalizado de tokens emitidos por el cliente.  
  
## <a name="discussion"></a>Discusión  
 Un proveedor de tokens en Windows Communication Foundation (WCF) se usa para proporcionar credenciales a la infraestructura de seguridad. En general, el proveedor de tokens examina el destino y emite las credenciales adecuadas de manera que la infraestructura de seguridad pueda proteger el mensaje. WCF se suministra con un proveedor de tokens de CardSpace. Los proveedores de tokens personalizados son útiles en los casos siguientes:  
  
- Si tiene un almacén de credenciales con el que el proveedor de tokens integrado no puede funcionar.  
  
- Si desea proporcionar su propio mecanismo personalizado para transformar las credenciales desde el punto en el que el usuario proporciona detalles cuando el cliente de WCF usa las credenciales.  
  
- Si está creando un token personalizado.  
  
 Este ejemplo muestra cómo crear un proveedor de tokens personalizado que almacena en memoria caché los tokens emitidos por un servicio de token de seguridad (STS).  
  
 En resumen, este ejemplo muestra lo siguiente:  
  
- Cómo se puede configurar un cliente con un proveedor de tokens personalizado.  
  
- Cómo se pueden almacenar en caché y proporcionar los tokens emitidos al cliente WCF.  
  
- Cómo el cliente autentica el servidor usando el certificado X.509 del servidor.  
  
 Este ejemplo está compuesto de un programa de consola de cliente (Client.exe), un programa de consola de servicio de token de seguridad (Securitytokenservice.exe) y un programa de consola de servicio (Service.exe). El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta. La interfaz `ICalculator`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato. El cliente obtiene un token de seguridad del servicio de token de seguridad (STS) y realiza las solicitudes sincrónicas al servicio para una operación matemática determinada y el servicio responde con el resultado. La actividad del cliente es visible en la ventana de la consola.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo expone el contrato de ICalculator mediante el [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). La configuración de este enlace en el cliente se muestra en el código siguiente.  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey" 
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuer address="http://localhost:8000/sts/windows" 
                  binding="wsHttpBinding" />
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 En el elemento `security` de `wsFederationHttpBinding`, el valor `mode` configura qué modo de seguridad debería utilizarse. En este ejemplo, se utiliza la seguridad de los mensajes, que es por lo que se especifica el elemento `message` de `wsFederationHttpBinding` dentro del elemento `security` de `wsFederationHttpBinding`. El elemento `issuer` de `wsFederationHttpBinding` que se encuentra dentro del elemento `message` de `wsFederationHttpBinding` especifica la dirección y el enlace para el Servicio de token de seguridad que emite un token de seguridad para el cliente, de manera que el cliente pueda autenticarlo con el servicio de calculadora.  
  
 La configuración de este enlace en el servicio se muestra en el código siguiente.  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey" 
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuerMetadata address="http://localhost:8000/sts/mex">
            <identity>
              <certificateReference storeLocation="CurrentUser" 
                                    storeName="TrustedPeople" 
                                    x509FindType="FindBySubjectDistinguishedName" 
                                    findValue="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 En el elemento `security` de `wsFederationHttpBinding`, el valor `mode` configura qué modo de seguridad debería utilizarse. En este ejemplo, se utiliza la seguridad de los mensajes, que es por lo que se especifica el elemento `message` de `wsFederationHttpBinding` dentro del elemento `security` de `wsFederationHttpBinding`. El elemento `issuerMetadata` de `wsFederationHttpBinding` dentro del elemento `message` de `wsFederationHttpBinding` especifica la dirección e identidad de un punto de conexión que se puede utilizar para recuperar los metadatos para el Servicio de token de seguridad.  
  
 El comportamiento para el servicio se muestra en el código siguiente.  
  
```xml  
<behavior name="ServiceBehavior">
  <serviceDebug includeExceptionDetailInFaults="true" />
  <serviceMetadata httpGetEnabled="true" />
  <serviceCredentials>
    <issuedTokenAuthentication>
      <knownCertificates>
        <add storeLocation="LocalMachine" 
              storeName="TrustedPeople" 
              x509FindType="FindBySubjectDistinguishedName" 
              findValue="CN=STS" />
      </knownCertificates>
    </issuedTokenAuthentication>
    <serviceCertificate storeLocation="LocalMachine" 
                        storeName="My" 
                        x509FindType="FindBySubjectDistinguishedName" 
                        findValue="CN=localhost" />
  </serviceCredentials>
</behavior>  
```  
  
 El elemento `issuedTokenAuthentication` dentro del elemento `serviceCredentials` permite al servicio especificar las restricciones en los tokens y permite a los clientes presentarse durante la autenticación. Esta configuración especifica que el servicio acepta los tokens firmados por un certificado cuyo nombre de asunto sea CN=STS.  
  
 El Servicio de token de seguridad expone un solo punto de conexión con el wsHttpBinding estándar. El Servicio de token de seguridad responde a las solicitudes de tokens de los clientes y, siempre que el cliente se autentique utilizando una cuenta de Windows, emite un token que contiene el nombre de usuario del cliente como una notificación en el token emitido. Como parte de la creación del token, el servicio de token de seguridad firma el token usando la clave privada asociada con el certificado de CN=STS. Además, crea una clave simétrica y la cifra utilizando la clave pública asociada con el certificado de CN=localhost. Para devolver el token al cliente, el servicio de token de seguridad devuelve también la clave simétrica. El cliente presenta el token emitido al servicio de la calculadora y demuestra que conoce la clave simétrica firmando el mensaje con esa clave.  
  
## <a name="custom-client-credentials-and-token-provider"></a>Credenciales de cliente personalizadas y proveedor de tokens  
 En los pasos siguientes se muestra cómo desarrollar un proveedor de tokens personalizado que almacena en memoria caché los tokens emitidos y los integra con WCF: Security.  
  
### <a name="to-develop-a-custom-token-provider"></a>Para desarrollar un proveedor de tokens personalizado  
  
1. Escriba un proveedor de tokens personalizado.  
  
     El ejemplo implementa un proveedor de tokens personalizado que devuelve un token de seguridad recuperado de la memoria caché.  
  
     Para realizar esta tarea, el proveedor de tokens personalizado deriva la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider> e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>. Este método intenta recibir un token de la memoria caché o si un token no se puede encontrar en la caché, se recupera un token del proveedor subyacente y, a continuación, lo almacena en la caché. En ambos casos, el método devuelve un `SecurityToken`.  
  
    ```csharp  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
      GenericXmlSecurityToken token;  
      if (!this.cache.TryGetToken(target, issuer, out token))  
      {  
        token = (GenericXmlSecurityToken) this.innerTokenProvider.GetToken(timeout);  
        this.cache.AddToken(token, target, issuer);  
      }  
      return token;  
    }  
    ```  
  
2. Escribir el administrador de tokens de seguridad personalizado.  
  
     El <xref:System.IdentityModel.Selectors.SecurityTokenManager> se utiliza para crear un <xref:System.IdentityModel.Selectors.SecurityTokenProvider> para el <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> concreto que se pasa en el método `CreateSecurityTokenProvider`. Un administrador de tokens de seguridad también se utiliza para crear autenticadores y serializadores de tokens, aunque en este ejemplo no se explica. En este ejemplo, el administrador de tokens de seguridad personalizado hereda de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> e invalida el método `CreateSecurityTokenProvider` para devolver el proveedor de tokens personalizado cuando los requisitos de tokens pasados indican que se solicita un token emitido.  
  
    ```csharp
    class DurableIssuedTokenClientCredentialsTokenManager :  
     ClientCredentialsSecurityTokenManager  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentialsTokenManager ( DurableIssuedTokenClientCredentials creds ): base(creds)  
      {  
        this.cache = creds.IssuedTokenCache;  
      }  
  
      public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )  
      {  
        if (IsIssuedSecurityTokenRequirement(tokenRequirement))  
        {  
          return new DurableIssuedSecurityTokenProvider ((IssuedSecurityTokenProvider)base.CreateSecurityTokenProvider( tokenRequirement), this.cache);  
        }  
        else
        {  
          return base.CreateSecurityTokenProvider(tokenRequirement);  
        }  
      }  
    }  
    ```  
  
3. Escribir una credencial de cliente personalizada.  
  
     Se usa una clase de credenciales de cliente para representar las credenciales que se configuran para el proxy de cliente y crea el administrador de tokens de seguridad que se utiliza para obtener autenticadores, proveedores y serializadores de tokens.  
  
    ```csharp
    public class DurableIssuedTokenClientCredentials : ClientCredentials  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentials() : base()  
      {  
      }  
  
      DurableIssuedTokenClientCredentials ( DurableIssuedTokenClientCredentials other) : base(other)  
      {  
        this.cache = other.cache;  
      }  
  
      public IssuedTokenCache IssuedTokenCache  
      {  
        get  
        {  
          return this.cache;  
        }  
        set  
        {  
          this.cache = value;  
        }  
      }  
  
      protected override ClientCredentials CloneCore()  
      {  
        return new DurableIssuedTokenClientCredentials(this);  
      }  
  
      public override SecurityTokenManager CreateSecurityTokenManager()  
      {  
        return new DurableIssuedTokenClientCredentialsTokenManager ((DurableIssuedTokenClientCredentials)this.Clone());  
      }  
    }  
    ```  
  
4. Implementar la caché del token. La implementación del ejemplo utiliza una clase base abstracta a través de la cual los consumidores de una caché de token determinada interactúan con la caché.  
  
    ```csharp
    public abstract class IssuedTokenCache  
    {  
      public abstract void AddToken ( GenericXmlSecurityToken token, EndpointAddress target, EndpointAddress issuer);  
      public abstract bool TryGetToken(EndpointAddress target, EndpointAddress issuer, out GenericXmlSecurityToken cachedToken);  
    }  
    // Configure the client to use the custom client credential.  
    ```  
  
     Para que el cliente utilice la credencial de cliente personalizada, el ejemplo elimina la clase de credencial de cliente predeterminada y proporciona la nueva.  
  
    ```csharp
    clientFactory.Endpoint.Behaviors.Remove<ClientCredentials>();  
    DurableIssuedTokenClientCredentials durableCreds = new DurableIssuedTokenClientCredentials();  
    durableCreds.IssuedTokenCache = cache;  
    durableCreds.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
    clientFactory.Endpoint.Behaviors.Add(durableCreds);  
    ```  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 Consulte las instrucciones siguientes para ejecutar el ejemplo. Al ejecutar el ejemplo, la solicitud para el token de seguridad se muestra en la ventana de la consola del servicio de token de seguridad. Las solicitudes y respuestas de la operación se muestran en las ventanas de la consola del cliente y el servicio. Presione ENTRAR en cualquiera de las ventanas de la consola para cerrar la aplicación.  
  
## <a name="the-setupcmd-batch-file"></a>Archivo por lotes Setup.cmd  
 El archivo por lotes de Setup.cmd incluido con este ejemplo le permite configurar el servidor y servicio de token de seguridad con certificados pertinentes para ejecutar una aplicación autohospedada. El archivo por lotes crea dos certificados en el almacén de certificados CurrentUser/TrustedPeople. El primer certificado tiene un nombre de asunto CN=STS que utiliza el servicio de token de seguridad para firmar los tokens de seguridad que emite el cliente. El segundo certificado tiene un nombre de asunto de CN=localhost que usa el servicio de token de seguridad para cifrar un secreto para que el servicio lo pueda descifrar.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Ejecute el archivo Setup.cmd para crear los certificados necesarios.  
  
2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md). Asegúrese de que todos los proyectos en la solución están compilados (compartido, RSTRSTR, servicio, SecurityTokenService y cliente).  
  
3. Asegúrese de que tanto el archivo Service.exe como el archivo SecurityTokenService.exe se ejecutan con privilegios de administrador.  
  
4. Ejecute Client.exe.  
  
### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
1. Ejecute Cleanup.cmd en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\DurableIssuedTokenProvider`  
