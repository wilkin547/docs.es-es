---
title: "C&#243;mo crear un administrador de autorizaci&#243;n personalizado para un servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Clase OperationRequirement"
  - "Windows Communication Foundation, extender"
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# C&#243;mo crear un administrador de autorizaci&#243;n personalizado para un servicio
La infraestructura del Modelo de identidad en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admite un modelo de la autorización basado en demandas extensible.Las demandas se extraen de los tokens y opcionalmente son procesadas por directivas de autorización personalizadas y, a continuación, colocadas en <xref:System.IdentityModel.Policy.AuthorizationContext>.Un administrador de autorización examina las demandas en <xref:System.IdentityModel.Policy.AuthorizationContext> para tomar las decisiones de autorización.  
  
 La clase <xref:System.ServiceModel.ServiceAuthorizationManager> toma de forma predeterminada, las decisiones de la autorización; sin embargo estas decisiones se pueden invalidar creando un administrador de autorización personalizado.Para crear un administrador de autorización personalizado, cree una clase que derive de <xref:System.ServiceModel.ServiceAuthorizationManager> e implemente el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.Las decisiones de la autorización se toman en el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>, que devuelve `true` cuando se permite el acceso y `false` cuando se niega el acceso.  
  
 Si la decisión de autorización depende del contenido del cuerpo del mensaje, utilice el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.  
  
 Debido a los problemas de rendimiento, en la medida de lo posible debe rediseñar su aplicación para que la decisión de autorización no requiera el acceso al cuerpo del mensaje.  
  
 El registro del administrador de autorización personalizado para un servicio se puede hacer en código o configuración.  
  
### Para crear un administrador de autorización personalizado  
  
1.  Derive una clase de la clase <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  Invalide el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>.  
  
     Utilice el <xref:System.ServiceModel.OperationContext> que se pasa al método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> para tomar las decisiones de autorización.  
  
     El siguiente ejemplo de código utiliza el método <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> para buscar el `http://www.contoso.com/claims/allowedoperation` de la notificación personalizada y tomar una decisión de autorización.  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### Para registrar a un administrador de autorización personalizado mediante código  
  
1.  Cree una instancia del administrador de autorización personalizado y asígnelo a la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.  
  
     Se puede tener acceso a <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.  
  
     El ejemplo de código siguiente registra el administrador de autorización personalizado `MyServiceAuthorizationManager`.  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### Para registrar a un administrador de autorización personalizado mediante configuración  
  
1.  Abra el archivo de configuración para el servicio.  
  
2.  Agregue [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) a [\<comportamientos\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
     Para el [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), agregue un atributo `serviceAuthorizationManagerType` y establezca su valor en el tipo que represente al administrador de autorización personalizado.  
  
3.  Agregue un enlace que proteja la comunicación entre el cliente y el servicio.  
  
     El enlace que se elige para esta comunicación determina las demandas que se agregan al <xref:System.IdentityModel.Policy.AuthorizationContext>, que el administrador de autorización personalizado utiliza para tomar las decisiones de autorización.Para obtener más detalles sobre los enlaces proporcionados por el sistema, vea [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
4.  Asocie el comportamiento a un extremo de servicio, agregando un elemento [\<servicio\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)`behaviorConfiguration y establezca el valor del atributo` [\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md).  
  
     Para obtener más información sobre la configuración de un extremo de servicio, vea [Cómo crear un extremo de servicio en configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
     El ejemplo de código siguiente registra el administrador de autorización personalizado `Samples.MyServiceAuthorizationManager`.  
  
    ```  
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
    >  Tenga en cuenta que cuando se especifica el serviceAuthorizationManagerType, la cadena debe contener el nombre de tipo completo.una coma, y el nombre del ensamblado en el que el tipo está definido.Si deja fuera el nombre del ensamblado, WCF intentará cargar el tipo desde System.ServiceModel.dll.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra una implementación básica de una clase <xref:System.ServiceModel.ServiceAuthorizationManager> que incluye la invalidación del método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.El código de ejemplo examina <xref:System.IdentityModel.Policy.AuthorizationContext> para una demanda personalizada y devuelve `true` cuando el recurso para esa demanda de la costumbre coincide con el valor de la acción de <xref:System.ServiceModel.OperationContext>.Para una implementación más completa de una clase <xref:System.ServiceModel.ServiceAuthorizationManager>, vea [Directiva de autorización](../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## Vea también  
 <xref:System.ServiceModel.ServiceAuthorizationManager>   
 [Directiva de autorización](../../../../docs/framework/wcf/samples/authorization-policy.md)   
 [Directiva de autorización](../../../../docs/framework/wcf/samples/authorization-policy.md)