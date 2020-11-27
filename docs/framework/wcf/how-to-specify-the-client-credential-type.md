---
title: Procedimiento para especificar el tipo de credencial de cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: b45d7b58d8a1fe79f9d7a8cff6e328b46633985c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293681"
---
# <a name="how-to-specify-the-client-credential-type"></a>Procedimiento para especificar el tipo de credencial de cliente

Después de establecer un modo de seguridad (ya sea transporte o mensaje), tiene la opción de establecer el tipo de credencial de cliente. Esta propiedad especifica qué tipo de credencial debe proporcionar el cliente al servicio para la autenticación. Para obtener más información acerca de cómo establecer el modo de seguridad (un paso necesario antes de establecer el tipo de credencial de cliente), consulte [Cómo: establecer el modo de seguridad](how-to-set-the-security-mode.md).  
  
### <a name="to-set-the-client-credential-type-in-code"></a>Para establecer el tipo de credencial de cliente en el código  
  
1. Cree una instancia del enlace que el servicio va a usar. En el ejemplo siguiente se utiliza el enlace <xref:System.ServiceModel.WSHttpBinding>.  
  
2. Establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> en un valor apropiado. Este ejemplo utiliza el modo de mensaje.  
  
3. Establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en un valor apropiado. Este ejemplo establece el uso de la autenticación de Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>Para establecer el tipo de credencial en la configuración  
  
1. Agregue un [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) elemento al archivo de configuración.  
  
2. Como elemento secundario, agregue un [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) elemento.  
  
3. Agregue un enlace adecuado. En este ejemplo se usa el [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.  
  
4. Agregue un [\<binding>](../configure-apps/file-schema/wcf/bindings.md) elemento y establezca el `name` atributo en un valor adecuado. Este ejemplo utiliza el nombre "SecureBinding".  
  
5. Agregue un enlace `<security>`. Establezca el atributo `mode` en un valor adecuado. Este ejemplo lo define en `"Message"`.  
  
6. Agregue un elemento `<message>`, tal y como se haya determinado en el modo de seguridad. Establezca el atributo `clientCredentialType` en un valor adecuado. En este ejemplo se usa `"Windows"`.  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>Vea también

- [Seguridad de servicios](securing-services.md)
- [Procedimiento para establecer el modo de seguridad](how-to-set-the-security-mode.md)
