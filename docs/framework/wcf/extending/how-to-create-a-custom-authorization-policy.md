---
title: Procedimiento para crear una directiva de autorización personalizada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
ms.openlocfilehash: 05130e809356369ee2b43d9af86acf69fe527e9a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295424"
---
# <a name="how-to-create-a-custom-authorization-policy"></a>Procedimiento para crear una directiva de autorización personalizada
La infraestructura del modelo de identidad en Windows Communication Foundation (WCF) admite un modelo de autorización basado en notificaciones. Las notificaciones se extraen de los tokens, procesados opcionalmente por la directiva de autorización personalizada. Después se colocan en un <xref:System.IdentityModel.Policy.AuthorizationContext> que se puede examinar a continuación para tomar las decisiones de autorización. Se puede utilizar una directiva personalizada para transformar las notificaciones de tokens entrantes en notificaciones esperadas por la aplicación. De este modo, se puede aislar la capa de aplicación de los detalles en las distintas notificaciones servidas por los distintos tipos de token que WCF admite. En este tema se muestra cómo implementar una directiva de autorización personalizada y cómo agregarla a la colección de directivas utilizada por un servicio.  
  
### <a name="to-implement-a-custom-authorization-policy"></a>Para implementar una directiva de autorización personalizada  
  
1. Defina una nueva clase derivada de <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.  
  
2. Implemente la propiedad <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> de solo lectura generando una cadena única en el constructor para la clase y devolviendo esa cadena cada vez que se tenga acceso a la propiedad.  
  
3. Implemente la propiedad <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> de solo lectura devolviendo un <xref:System.IdentityModel.Claims.ClaimSet> que representa el emisor de la directiva. Éste podría ser `ClaimSet`, que representa la aplicación o un `ClaimSet` integrado (por ejemplo, el `ClaimSet` devuelto por la propiedad <xref:System.IdentityModel.Claims.ClaimSet.System%2A> estática.  
  
4. Implemente el método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> tal y como se ha descrito en el procedimiento siguiente.  
  
### <a name="to-implement-the-evaluate-method"></a>Para implementar el método de evaluación  
  
1. Dos parámetros se pasan a este método: una instancia de la clase <xref:System.IdentityModel.Policy.EvaluationContext> y una referencia de objeto.  
  
2. Si la directiva de autorización personalizada agrega <xref:System.IdentityModel.Claims.ClaimSet> instancias sin tener en cuenta el contenido actual de la <xref:System.IdentityModel.Policy.EvaluationContext>, a continuación, agregue cada `ClaimSet` mediante una llamada a la <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> método y devolver `true` desde el <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> método. Devolver `true` indica a la infraestructura de la autorización que la directiva de autorización ha realizado su trabajo y no necesita ser llamada de nuevo.  
  
3. Si la directiva de autorización personalizada agrega conjuntos de notificaciones solo si algunas notificaciones están presentes en `EvaluationContext`, después búsquelas examinando las instancias `ClaimSet` devueltas por la propiedad <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A>. Si las notificaciones están presentes, añada los nuevos conjuntos de notificaciones llamando al método <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> y, si no se van a agregar más conjuntos de notificaciones, devuelva `true`, indicando a la infraestructura de autorización que la directiva de autorización ha completado su trabajo. Si las notificaciones no están presentes, devuelva `false`, indicando que se debería llamar a la directiva de autorización de nuevo si otras directivas de autorización agregan más conjuntos de notificaciones a `EvaluationContext`.  
  
4. En escenarios de procesamiento más complejos, el segundo parámetro del método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> se utiliza para almacenar una variable de estado que la infraestructura de autorización devolverá durante cada llamada posterior realizada al método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> para una evaluación determinada.  
  
### <a name="to-specify-a-custom-authorization-policy-through-configuration"></a>Para especificar una directiva de autorización personalizada mediante la configuración  
  
1. Especifique el tipo de la directiva de autorización personalizada en el atributo `policyType` en el elemento `add` correspondiente al elemento `authorizationPolicies` del elemento `serviceAuthorization`.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
        <serviceAuthorization serviceAuthorizationManagerType=  
                  "Samples.MyServiceAuthorizationManager" >  
          <authorizationPolicies>  
            <add policyType="Samples.MyAuthorizationPolicy" />  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-specify-a-custom-authorization-policy-through-code"></a>Para especificar una directiva de autorización personalizada mediante código  
  
1. Cree un <xref:System.Collections.Generic.List%601> de <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.  
  
2. Cree una instancia de la directiva de autorización personalizada.  
  
3. Agregue la instancia de la directiva de autorización a la lista.  
  
4. Repita los pasos 2 y 3 para cada directiva de autorización personalizada.  
  
5. Asigne una versión de solo lectura de la lista a la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>.  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra una implementación de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> completa.  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Cómo: Comparar las notificaciones](../../../../docs/framework/wcf/extending/how-to-compare-claims.md)
- [Cómo: Crear un administrador de autorización personalizado para un servicio](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [Directiva de autorización](../../../../docs/framework/wcf/samples/authorization-policy.md)
