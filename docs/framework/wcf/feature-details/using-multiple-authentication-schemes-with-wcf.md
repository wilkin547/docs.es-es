---
title: Usar múltiples esquemas de autenticación con WCF
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: 9f2c9944b424ba527fb20562706d5ad7fc3f8359
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465500"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a>Usar múltiples esquemas de autenticación con WCF
WCF permite ahora especificar varios esquemas de autenticación en un único extremo. Además los servicios hospedados en web pueden heredar sus valores de autenticación directamente de IIS. Los servicios autohospedados pueden especificar los esquemas de autenticación que se pueden usar. Para obtener más información acerca de cómo establecer la configuración de autenticación en IIS, consulte [autenticación IIS](https://go.microsoft.com/fwlink/?LinkId=232458)  
  
## <a name="iis-hosted-services"></a>Servicios hospedados en IIS  
 Para los servicios hospedados en IIS, establezca los esquemas de autenticación que desea usa en IIS. A continuación, en el archivo web.config de su servicio, en la configuración de enlace especifique tipo clientCredential como "InheritedFromHost" como se muestra en el siguiente fragmento XML:  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 Puede especificar que desea que solo un subconjunto de esquemas de autenticación que se usará con el servicio mediante el ServiceAuthenticationBehavior o el \<serviceAuthenticationManager > elemento. Al configurar esto en el código, use ServiceAuthenticationBehavior como se muestra en el fragmento de código siguiente.  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 Al configurar esto en un archivo de configuración, use el \<serviceAuthenticationManager > elemento tal como se muestra en el siguiente fragmento XML.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 Esto garantizará que solo se considere un subconjunto de los esquemas de autenticación enumerados aquí para aplicar en el punto de conexión de servicio, según cuál se haya seleccionado en IIS. Esto significa que un desarrollador puede excluir la autenticación básica de la lista omitiéndola de la lista de serviceAuthenticationManager e incluso si está habilitada en IIS, no se aplicará en el punto de conexión de servicio.  
  
## <a name="self-hosted-services"></a>Servicios WCF autohospedados  
 Los servicios autohospedados se configuran de manera ligeramente diferente puesto que no hay configuración de IIS para heredar. Aquí se usa el \<serviceAuthenticationManager > elemento o ServiceAuthenticationBehavior para especificar la configuración de autenticación que se heredarán. En el código tiene el siguiente aspecto:  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 En la configuración, tiene el siguiente aspecto:  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 A continuación puede especificar InheritFromHost en la configuración de enlace como se muestra en el fragmento XML siguiente.  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 Opcionalmente, puede especificar los esquemas de autenticación en un enlace personalizado, estableciendo los esquemas de autenticación en el elemento de enlace de transporte HTTP, como se muestra en el siguiente fragmento de código de configuración.  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a>Vea también
- [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [Puntos de conexión: Las direcciones, enlaces y contratos](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Configuración de enlaces proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Funcionalidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)
- [Enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md)
