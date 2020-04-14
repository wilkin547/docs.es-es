---
title: Invalidación de la identidad de un servicio para la autenticación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: 5649ef4cc05c9c16b1f8f626ba5e2e584b0e52eb
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278917"
---
# <a name="override-the-identity-of-a-service-for-authentication"></a>Reemplazar la identidad de un servicio para la autenticación

Normalmente, no tiene que establecer la identidad en un servicio porque la selección de un tipo de credencial de cliente dicta el tipo de identidad expuesto en los metadatos del servicio. Por ejemplo, el siguiente código de configuración utiliza el `clientCredentialType` [ \<elemento de>wsHttpBinding](../../configure-apps/file-schema/wcf/wshttpbinding.md) y establece el atributo en Windows.  

 El fragmento siguiente de Lenguaje de descripción de servicios Web (WSDL) muestra la identidad para el punto de conexión previamente definido. En este ejemplo, el servicio se ejecuta como un serviciousername@contoso.comautohospedado bajo una cuenta de usuario determinada ( ) y, por lo tanto, la identidad del nombre principal de usuario (UPN) contiene el nombre de cuenta. El UPN también se conoce como el nombre de inicio de sesión del usuario en un dominio de Windows.  

 Para obtener una aplicación de ejemplo que muestra la configuración de identidad, vea Ejemplo de [identidad](../samples/service-identity-sample.md)de servicio . Para obtener más información acerca de la identidad del servicio, vea [Identidad de servicio y autenticación](../feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Autenticación e identidad de Kerberos  
 De forma predeterminada, cuando un servicio está [ \<](../../configure-apps/file-schema/wcf/identity.md) configurado para usar una credencial de Windows, se genera una identidad>elemento que contiene un [ \<elemento userPrincipalName>](../../configure-apps/file-schema/wcf/userprincipalname.md) o [ \<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) en el WSDL. Si el servicio se `LocalSystem` `LocalService`ejecuta `NetworkService` bajo la cuenta o , , se genera un nombre `host/` \<de entidad de seguridad de servicio (SPN) de forma predeterminada en forma de nombre de *host*> porque esas cuentas tienen acceso a los datos de SPN del equipo. Si el servicio se ejecuta en una cuenta diferente, Windows Communication Foundation \<(WCF) genera un UPN en forma de nombre de *usuario*>@<*nombredeusuarionombre*`>`. Esto ocurre porque la autenticación Kerberos requiere que se proporcione un UPN o SPN al cliente para autenticar el servicio.  
  
 También puede utilizar la herramienta [Setspn](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731241(v=ws.10)?redirectedfrom=MSDN) para registrar un SPN adicional con la cuenta de un servicio en un dominio. Puede utilizar a continuación el SPN como la identidad del servicio. Para obtener más información acerca de la herramienta, consulte [Setspn Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).  
  
> [!NOTE]
> Para usar el tipo de credencial de Windows sin negociación, la cuenta de usuario del servicio debe tener acceso al nombre de entidad de seguridad de servicio (SPN) registrado en el dominio de Active Directory. Puede hacer esto de las siguientes maneras:  
  
- Use la cuenta NetworkService o LocalSystem para ejecutar el servicio. Dado que esas cuentas tienen acceso al SPN de máquina que se establece cuando la máquina se une al dominio de Active Directory, WCF genera automáticamente el elemento SPN adecuado dentro del extremo del servicio en los metadatos del servicio (WSDL).  
  
- Utilice una cuenta de dominio arbitraria de Active Directory para ejecutar el servicio. En este caso, establezca un SPN para esa cuenta de dominio, lo cual puede llevar a cabo utilizando la herramienta de utilidad Setspn.exe. Una vez que cree el SPN para la cuenta del servicio, configure WCF para publicar ese SPN en los clientes del servicio a través de sus metadatos (WSDL). Para ello, hay que establecer la identidad del extremo para el extremo expuesto, ya sea mediante un archivo de configuración de la aplicación o el código.  
  
 Para obtener más información acerca de los SPN, el protocolo Kerberos y Active Directory, consulte [Suplemento técnico de Kerberos para Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)).  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>Cuando SPN o UPN es igual a la cadena vacía  
 Si establece el SPN o el UPN igual a una cadena vacía, pueden ocurrir varias cosas diferentes, según el nivel de seguridad y modo de autenticación que se use:  
  
- Si está usando la seguridad de nivel de transporte, se elige la autenticación NT LanMan (NTLM).  
  
- Si usa la seguridad de nivel de mensaje, se puede producir un error en la autenticación, en función del modo de autenticación:  
  
- Si está `spnego` utilizando `AllowNtlm` el modo `false`y el atributo se establece en , se produce un error de autenticación.  
  
- Si está `spnego` utilizando `AllowNtlm` el modo `true`y el atributo se establece en , se produce un error de autenticación si el UPN está vacío, pero se realiza correctamente si el SPN está vacío.  
  
- Si usa Kerberos directo (también conocido como "de una vez"), se produce un error de autenticación.  
  
### <a name="use-the-identity-element-in-configuration"></a>Utilice \<el elemento> de identidad en la configuración  
 Si cambia el tipo de credencial de `Certificate`cliente en el enlace mostrado anteriormente , el WSDL generado contiene un certificado X.509 serializado de Base64 para el valor de identidad como se muestra en el código siguiente. Éste es el valor predeterminado para todos los tipos de credencial de cliente excepto Windows.  

 Puede cambiar el valor de la identidad de servicio predeterminada o `identity` cambiar el tipo de la identidad mediante el <> elemento en la configuración o estableciendo la identidad en el código. El código de configuración siguiente establece una identidad del sistema de nombres de dominio (DNS) con el valor `contoso.com`.  

### <a name="set-identity-programmatically"></a>Establecer identidad mediante programación  
 El servicio no tiene que especificar explícitamente una identidad, porque WCF la determina automáticamente. Sin embargo, WCF permite especificar una identidad en un extremo, si es necesario. El código siguiente agrega un nuevo punto de conexión de servicio con una identidad de DNS concreta.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Consulte también

- [Procedimiento para crear un comprobador de identidad de cliente personalizado](how-to-create-a-custom-client-identity-verifier.md)
- [Identidad del servicio y autenticación](../feature-details/service-identity-and-authentication.md)
