---
description: Más información acerca de cómo crear un administrador de autorización personalizado para un servicio
title: Procedimiento para crear un administrador de autorización personalizado para un servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
ms.openlocfilehash: e5b5655bb8cd087e2c5140f45e80f8b079cf06c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743725"
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a>Procedimiento para crear un administrador de autorización personalizado para un servicio

La infraestructura del modelo de identidad de Windows Communication Foundation (WCF) admite un modelo de autorización basado en notificaciones extensible. Las demandas se extraen de los tokens y opcionalmente son procesadas por directivas de autorización personalizadas y, a continuación, colocadas en <xref:System.IdentityModel.Policy.AuthorizationContext>. Un administrador de autorización examina las demandas en <xref:System.IdentityModel.Policy.AuthorizationContext> para tomar las decisiones de autorización.

La clase <xref:System.ServiceModel.ServiceAuthorizationManager> toma de forma predeterminada, las decisiones de la autorización; sin embargo estas decisiones se pueden invalidar creando un administrador de autorización personalizado. Para crear un administrador de autorización personalizado, cree una clase que derive de <xref:System.ServiceModel.ServiceAuthorizationManager> e implemente el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Las decisiones de la autorización se toman en el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>, que devuelve `true` cuando se permite el acceso y `false` cuando se niega el acceso.

Si la decisión de autorización depende del contenido del cuerpo del mensaje, utilice el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.

Debido a los problemas de rendimiento, en la medida de lo posible debe rediseñar su aplicación para que la decisión de autorización no requiera el acceso al cuerpo del mensaje.

El registro del administrador de autorización personalizado para un servicio se puede hacer en código o configuración.

### <a name="to-create-a-custom-authorization-manager"></a>Para crear un administrador de autorización personalizado

1. Derive una clase de la clase <xref:System.ServiceModel.ServiceAuthorizationManager>.

    [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
    [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]

2. Invalide el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> .

    Utilice el <xref:System.ServiceModel.OperationContext> que se pasa al método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> para tomar las decisiones de autorización.

    El siguiente ejemplo de código utiliza el método <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> para buscar el `http://www.contoso.com/claims/allowedoperation` de la notificación personalizada y tomar una decisión de autorización.

    [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
    [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]

### <a name="to-register-a-custom-authorization-manager-using-code"></a>Para registrar a un administrador de autorización personalizado mediante código

1. Cree una instancia del administrador de autorización personalizado y asígnelo a la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.

    Se puede tener acceso a <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.

    El ejemplo de código siguiente registra el administrador de autorización personalizado `MyServiceAuthorizationManager`.

    [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
    [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]

### <a name="to-register-a-custom-authorization-manager-using-configuration"></a>Para registrar a un administrador de autorización personalizado mediante configuración

1. Abra el archivo de configuración para el servicio.

2. Agregue [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) .

    Para [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) , agregue un `serviceAuthorizationManagerType` atributo y establezca su valor en el tipo que representa el administrador de autorización personalizado.

3. Agregue un enlace que proteja la comunicación entre el cliente y el servicio.

    El enlace que se elige para esta comunicación determina las demandas que se agregan al <xref:System.IdentityModel.Policy.AuthorizationContext>, que el administrador de autorización personalizado utiliza para tomar las decisiones de autorización. Para obtener más información acerca de los enlaces proporcionados por el sistema, consulte [enlaces proporcionados](../system-provided-bindings.md)por el sistema.

4. Asocie el comportamiento a un punto de conexión de servicio; para ello, agregue un [\<service>](../../configure-apps/file-schema/wcf/service.md) elemento y establezca el valor del `behaviorConfiguration` atributo en el valor del atributo name del [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.

    Para obtener más información acerca de cómo configurar un punto de conexión de servicio, consulte [Cómo: crear un punto de conexión de servicio en la configuración](../feature-details/how-to-create-a-service-endpoint-in-configuration.md).

    El ejemplo de código siguiente registra el administrador de autorización personalizado `Samples.MyServiceAuthorizationManager`.

    ```xml
    <configuration>
      <system.serviceModel>
        <services>
          <service
              name="Microsoft.ServiceModel.Samples.CalculatorService"
              behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <endpoint address=""
                      binding="wsHttpBinding_Calculator"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
          </service>
        </services>
        <bindings>
          <WSHttpBinding>
           <binding name = "wsHttpBinding_Calculator">
             <security mode="Message">
               <message clientCredentialType="Windows"/>
             </security>
            </binding>
          </WSHttpBinding>
        </bindings>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceAuthorization serviceAuthorizationManagerType="Samples.MyServiceAuthorizationManager,MyAssembly" />
             </behavior>
         </serviceBehaviors>
       </behaviors>
      </system.serviceModel>
    </configuration>
    ```

    > [!WARNING]
    > Tenga en cuenta que cuando se especifica el serviceAuthorizationManagerType, la cadena debe contener el nombre de tipo completo. una coma, y el nombre del ensamblado en el que el tipo está definido. Si deja fuera el nombre del ensamblado, WCF intentará cargar el tipo desde System.ServiceModel.dll.

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra una implementación básica de una clase <xref:System.ServiceModel.ServiceAuthorizationManager> que incluye la invalidación del método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. El código de ejemplo examina <xref:System.IdentityModel.Policy.AuthorizationContext> para una demanda personalizada y devuelve `true` cuando el recurso para esa demanda de la costumbre coincide con el valor de la acción de <xref:System.ServiceModel.OperationContext>. Para obtener una implementación más completa de una <xref:System.ServiceModel.ServiceAuthorizationManager> clase, vea [Directiva de autorización](../samples/authorization-policy.md).

[!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
[!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Directiva de autorización](../samples/authorization-policy.md)
