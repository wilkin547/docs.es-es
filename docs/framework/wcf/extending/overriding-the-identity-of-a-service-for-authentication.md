---
title: Invalidación de la identidad de un servicio para la autenticación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: 8c0807a7b811cf2cb3a13576018373d135e3e5cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554470"
---
# <a name="overriding-the-identity-of-a-service-for-authentication"></a>Invalidación de la identidad de un servicio para la autenticación
Normalmente, no tiene que establecer la identidad en un servicio porque la selección de un tipo de credencial de cliente dicta el tipo de identidad expuesto en los metadatos del servicio. Por ejemplo, el código de configuración siguiente utiliza el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento y establece el `clientCredentialType` atribuir a Windows.  
  
  
  
 El fragmento siguiente de Lenguaje de descripción de servicios Web (WSDL) muestra la identidad para el punto de conexión previamente definido. En este ejemplo, el servicio se ejecuta como un servicio autohospedado en una cuenta de usuario en particular (username@contoso.com) y, por tanto, la identidad del usuario (UPN) del nombre principal contiene el nombre de cuenta. El UPN también se conoce como el nombre de inicio de sesión de usuario en un dominio de Windows.  
  
  
  
 Para una aplicación de ejemplo que muestre la configuración de identidad, vea [ejemplo de identidad de servicio](../../../../docs/framework/wcf/samples/service-identity-sample.md). Para obtener más información acerca de la identidad de servicio, consulte [autenticación e identidad de servicio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Autenticación e identidad de Kerberos  
 De forma predeterminada, cuando un servicio está configurado para usar una credencial de Windows, un [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elemento que contiene un [ \<userPrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/userprincipalname.md) o [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) elemento se genera en el WSDL. Si el servicio se ejecuta bajo la `LocalSystem`, `LocalService`, o `NetworkService` cuenta, un servicio (SPN) de nombre principal se genera de forma predeterminada en el formulario de `host/` \< *hostname*> porque esas cuentas tienen acceso a los datos SPN del equipo. Si el servicio se está ejecutando bajo una cuenta diferente, Windows Communication Foundation (WCF) genera un UPN en forma de \< *username*>@<*domainName* `>` . Esto ocurre porque la autenticación Kerberos requiere que se proporcione un UPN o SPN al cliente para autenticar el servicio.  
  
 También puede utilizar la herramienta Setspn.exe para registrar un SPN adicional con la cuenta de un servicio en un dominio. Puede utilizar a continuación el SPN como la identidad del servicio. Para descargar la herramienta, consulte [Windows 2000 Resource Kit Tool: Setspn.exe](https://go.microsoft.com/fwlink/?LinkId=91752). Para obtener más información acerca de la herramienta, consulte [información general sobre Setspn](https://go.microsoft.com/fwlink/?LinkId=61374).  
  
> [!NOTE]
>  Para usar el tipo de credencial de Windows sin negociación, la cuenta de usuario del servicio debe tener acceso al nombre de entidad de seguridad de servicio (SPN) registrado en el dominio de Active Directory. Puede hacer esto de las siguientes maneras:  
  
-   Use la cuenta NetworkService o LocalSystem para ejecutar el servicio. Porque esas cuentas tienen acceso al SPN del equipo que se establece cuando el equipo une al dominio de Active Directory, WCF genera automáticamente el elemento SPN apropiado dentro del extremo del servicio en los metadatos del servicio (WSDL).  
  
-   Utilice una cuenta de dominio arbitraria de Active Directory para ejecutar el servicio. En este caso, establezca un SPN para esa cuenta de dominio, lo cual puede llevar a cabo utilizando la herramienta de utilidad Setspn.exe. Una vez creado el SPN para la cuenta del servicio, configure WCF para publicar ese SPN a los clientes del servicio a través de sus metadatos (WSDL). Para ello, hay que establecer la identidad del punto de conexión para el punto de conexión expuesto, ya sea mediante un archivo de configuración de la aplicación o el código.  
  
 Para obtener más información acerca de los SPN, el protocolo Kerberos y Active Directory, consulte [suplemento técnico de Kerberos para Windows](https://go.microsoft.com/fwlink/?LinkId=88330).  
  
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
 El servicio no tiene que especificar explícitamente una identidad, porque WCF determina automáticamente. Sin embargo, WCF permite especificar una identidad en un punto de conexión, si es necesario. El código siguiente agrega un nuevo punto de conexión de servicio con una identidad de DNS concreta.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Vea también
- [Cómo: Crear un comprobador de identidad de cliente personalizada](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)
- [Identidad del servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
