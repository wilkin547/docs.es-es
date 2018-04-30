---
title: Invalidación de la identidad de un servicio para la autenticación
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f5383a1d241134318ce48c8c0c9f39f831396730
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="overriding-the-identity-of-a-service-for-authentication"></a>Invalidación de la identidad de un servicio para la autenticación
Normalmente, no tiene que establecer la identidad en un servicio porque la selección de un tipo de credencial de cliente dicta el tipo de identidad expuesto en los metadatos del servicio. Por ejemplo, el siguiente código de configuración usa la [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento y establece el `clientCredentialType` atribuir a Windows.  
  
  
  
 El fragmento siguiente de Lenguaje de descripción de servicios Web (WSDL) muestra la identidad para el punto de conexión previamente definido. En este ejemplo, el servicio se ejecuta como un servicio hospedado por sí mismo bajo una cuenta de usuario determinada (username@contoso.com) y, por tanto, la identidad de nombre principal (UPN) del usuario contiene el nombre de cuenta. El UPN también se conoce como el nombre de inicio de sesión de usuario en un dominio de Windows.  
  
  
  
 Para una aplicación de ejemplo que muestra el valor de identidad, vea [ejemplo de identidad de servicio](../../../../docs/framework/wcf/samples/service-identity-sample.md). Para obtener más información acerca de la identidad de servicio, consulte [autenticación e identidad de servicio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Autenticación e identidad de Kerberos  
 De forma predeterminada, cuando un servicio está configurado para usar una credencial de Windows, un [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elemento que contiene un [ \<userPrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/userprincipalname.md) o [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) se genera el elemento en el archivo WSDL. Si el servicio se ejecuta bajo la `LocalSystem`, `LocalService`, o `NetworkService` cuenta, un servicio de nombre de entidad de seguridad (SPN) se genera de forma predeterminada en el formulario de `host/` \< *hostname*> porque esas cuentas tienen acceso a los datos SPN del equipo. Si el servicio se está ejecutando bajo una cuenta diferente, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] genera un UPN con el formato de \< *nombre de usuario*>@<*domainName*`>`. Esto ocurre porque la autenticación Kerberos requiere que se proporcione un UPN o SPN al cliente para autenticar el servicio.  
  
 También puede utilizar la herramienta Setspn.exe para registrar un SPN adicional con la cuenta de un servicio en un dominio. Puede utilizar a continuación el SPN como la identidad del servicio. Para descargar la herramienta, consulte [herramienta del Kit de recursos de Windows 2000: Setspn.exe](http://go.microsoft.com/fwlink/?LinkId=91752). Para obtener más información acerca de la herramienta, consulte [información general sobre Setspn](http://go.microsoft.com/fwlink/?LinkId=61374).  
  
> [!NOTE]
>  Para usar el tipo de credencial de Windows sin negociación, la cuenta de usuario del servicio debe tener acceso al nombre de entidad de seguridad de servicio (SPN) registrado en el dominio de Active Directory. Puede hacer esto de las siguientes maneras:  
  
-   Use la cuenta NetworkService o LocalSystem para ejecutar el servicio. Dado que esas cuentas tienen acceso al SPN del equipo que se establece cuando el equipo se une al dominio de Active Directory, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera automáticamente el elemento SPN apropiado dentro del extremo del servicio en los metadatos del servicio (WSDL).  
  
-   Utilice una cuenta de dominio arbitraria de Active Directory para ejecutar el servicio. En este caso, establezca un SPN para esa cuenta de dominio, lo cual puede llevar a cabo utilizando la herramienta de utilidad Setspn.exe. Una vez creado el SPN para la cuenta del servicio, configure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para publicar ese SPN a los clientes del servicio a través de sus metadatos (WSDL). Para ello, hay que establecer la identidad del punto de conexión para el punto de conexión expuesto, ya sea mediante un archivo de configuración de la aplicación o el código.  
  
 Para obtener más información acerca de los SPN, el protocolo Kerberos y Active Directory, vea [complemento técnico de Kerberos para Windows](http://go.microsoft.com/fwlink/?LinkId=88330).  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>Cuando SPN o UPN es igual a la cadena vacía  
 Si establece el SPN o el UPN igual a una cadena vacía, pueden ocurrir varias cosas diferentes, según el nivel de seguridad y modo de autenticación que se use:  
  
-   Si está usando la seguridad de nivel de transporte, se elige la autenticación NT LanMan (NTLM).  
  
-   Si usa la seguridad de nivel de mensaje, se puede producir un error en la autenticación, en función del modo de autenticación:  
  
-   Si usa el modo `spnego` y el atributo `AllowNtlm` está establecido en `false`, se produce un error de autenticación.  
  
-   Si usa el modo `spnego` y el atributo `AllowNtlm` está establecido en `true`, se produce un error de autenticación si el UPN está vacío, pero se realiza correctamente si el SPN está vacío.  
  
-   Si usa Kerberos directo (también conocido como "de una vez"), se produce un error de autenticación.  
  
### <a name="using-the-identity-element-in-configuration"></a>Mediante el \<identidad > elemento de configuración  
 Si se cambia el tipo de credencial de cliente del enlace mostrado anteriormente a Certificate`,` el WSDL generado contiene un certificado X.509 serializado en Base64 para el valor de identidad, como se muestra en el código siguiente. Éste es el valor predeterminado para todos los tipos de credencial de cliente excepto Windows.  
  
  
  
 Puede cambiar el valor de la identidad del servicio predeterminada o el tipo de la identidad con el elemento <`identity`> en la configuración o estableciendo la identidad en código. El código de configuración siguiente establece una identidad del sistema de nombres de dominio (DNS) con el valor `contoso.com`.  
  
  
  
### <a name="setting-identity-programmatically"></a>Establecimiento mediante programación de la identidad  
 Su servicio no tiene que especificar explícitamente una identidad, porque [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lo determina automáticamente. Sin embargo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le permite especificar una identidad en un extremo, si se requiere. El código siguiente agrega un nuevo punto de conexión de servicio con una identidad de DNS concreta.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Vea también  
 [Creación de un comprobador de identidad de cliente personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 [Identidad del servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
