---
description: 'Más información acerca de cómo: crear una directiva de autorización personalizada'
title: Procedimiento para crear una directiva de autorización personalizada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
ms.openlocfilehash: 41158944aec9b0a5b8cb28c51922b8a1b103317c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743712"
---
# <a name="how-to-create-a-custom-authorization-policy"></a><span data-ttu-id="269e4-103">Procedimiento para crear una directiva de autorización personalizada</span><span class="sxs-lookup"><span data-stu-id="269e4-103">How to: Create a Custom Authorization Policy</span></span>

<span data-ttu-id="269e4-104">La infraestructura del modelo de identidad de Windows Communication Foundation (WCF) admite un modelo de autorización basado en notificaciones.</span><span class="sxs-lookup"><span data-stu-id="269e4-104">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports a claim-based authorization model.</span></span> <span data-ttu-id="269e4-105">Las notificaciones se extraen de los tokens, procesados opcionalmente por la directiva de autorización personalizada. Después se colocan en un <xref:System.IdentityModel.Policy.AuthorizationContext> que se puede examinar a continuación para tomar las decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="269e4-105">Claims are extracted from tokens, optionally processed by custom authorization policy, and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext> that can then be examined to make authorization decisions.</span></span> <span data-ttu-id="269e4-106">Se puede utilizar una directiva personalizada para transformar las notificaciones de tokens entrantes en notificaciones esperadas por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="269e4-106">A custom policy can be used to transform claims from incoming tokens into claims expected by the application.</span></span> <span data-ttu-id="269e4-107">De esta manera, el nivel de aplicación se puede aislar de los detalles de las distintas notificaciones servidas por los diferentes tipos de token que admite WCF.</span><span class="sxs-lookup"><span data-stu-id="269e4-107">In this way, the application layer can be insulated from the details on the differing claims served up by the different token types that WCF supports.</span></span> <span data-ttu-id="269e4-108">En este tema se muestra cómo implementar una directiva de autorización personalizada y cómo agregarla a la colección de directivas utilizada por un servicio.</span><span class="sxs-lookup"><span data-stu-id="269e4-108">This topic shows how to implement a custom authorization policy and how to add that policy to the collection of policies used by a service.</span></span>  
  
### <a name="to-implement-a-custom-authorization-policy"></a><span data-ttu-id="269e4-109">Para implementar una directiva de autorización personalizada</span><span class="sxs-lookup"><span data-stu-id="269e4-109">To implement a custom authorization policy</span></span>  
  
1. <span data-ttu-id="269e4-110">Defina una nueva clase derivada de <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="269e4-110">Define a new class that derives from <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2. <span data-ttu-id="269e4-111">Implemente la propiedad <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> de solo lectura generando una cadena única en el constructor para la clase y devolviendo esa cadena cada vez que se tenga acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="269e4-111">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> property by generating a unique string in the constructor for the class and returning that string whenever the property is accessed.</span></span>  
  
3. <span data-ttu-id="269e4-112">Implemente la propiedad <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> de solo lectura devolviendo un <xref:System.IdentityModel.Claims.ClaimSet> que representa el emisor de la directiva.</span><span class="sxs-lookup"><span data-stu-id="269e4-112">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> property by returning a <xref:System.IdentityModel.Claims.ClaimSet> that represents the policy issuer.</span></span> <span data-ttu-id="269e4-113">Éste podría ser `ClaimSet`, que representa la aplicación o un `ClaimSet` integrado (por ejemplo, el `ClaimSet` devuelto por la propiedad <xref:System.IdentityModel.Claims.ClaimSet.System%2A> estática.</span><span class="sxs-lookup"><span data-stu-id="269e4-113">This could be a `ClaimSet` that represents the application or a built-in `ClaimSet` (for example, the `ClaimSet` returned by the static <xref:System.IdentityModel.Claims.ClaimSet.System%2A> property.</span></span>  
  
4. <span data-ttu-id="269e4-114">Implemente el método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> tal y como se ha descrito en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="269e4-114">Implement the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method as described in the following procedure.</span></span>  
  
### <a name="to-implement-the-evaluate-method"></a><span data-ttu-id="269e4-115">Para implementar el método de evaluación</span><span class="sxs-lookup"><span data-stu-id="269e4-115">To implement the Evaluate method</span></span>  
  
1. <span data-ttu-id="269e4-116">Dos parámetros se pasan a este método: una instancia de la clase <xref:System.IdentityModel.Policy.EvaluationContext> y una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="269e4-116">Two parameters are passed to this method: an instance of the <xref:System.IdentityModel.Policy.EvaluationContext> class and an object reference.</span></span>  
  
2. <span data-ttu-id="269e4-117">Si la Directiva de autorización personalizada agrega <xref:System.IdentityModel.Claims.ClaimSet> instancias sin tener en cuenta el contenido actual de <xref:System.IdentityModel.Policy.EvaluationContext> , agregue cada `ClaimSet` una de ellas llamando al <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> método y devolviendo `true` desde el <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> método.</span><span class="sxs-lookup"><span data-stu-id="269e4-117">If the custom authorization policy adds <xref:System.IdentityModel.Claims.ClaimSet> instances without regard to the current content of the <xref:System.IdentityModel.Policy.EvaluationContext>, then add each `ClaimSet` by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and return `true` from the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> method.</span></span> <span data-ttu-id="269e4-118">Devolver `true` indica a la infraestructura de la autorización que la directiva de autorización ha realizado su trabajo y no necesita ser llamada de nuevo.</span><span class="sxs-lookup"><span data-stu-id="269e4-118">Returning `true` indicates to the authorization infrastructure that the authorization policy has performed its work and does not need to be called again.</span></span>  
  
3. <span data-ttu-id="269e4-119">Si la directiva de autorización personalizada agrega conjuntos de notificaciones solo si algunas notificaciones están presentes en `EvaluationContext`, después búsquelas examinando las instancias `ClaimSet` devueltas por la propiedad <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A>.</span><span class="sxs-lookup"><span data-stu-id="269e4-119">If the custom authorization policy adds claim sets only if certain claims are already present in the `EvaluationContext`, then look for those claims by examining the `ClaimSet` instances returned by the <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A> property.</span></span> <span data-ttu-id="269e4-120">Si las notificaciones están presentes, añada los nuevos conjuntos de notificaciones llamando al método <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> y, si no se van a agregar más conjuntos de notificaciones, devuelva `true`, indicando a la infraestructura de autorización que la directiva de autorización ha completado su trabajo.</span><span class="sxs-lookup"><span data-stu-id="269e4-120">If the claims are present, then add the new claim sets by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and, if no more claim sets are to be added, return `true`, indicating to the authorization infrastructure that the authorization policy has completed its work.</span></span> <span data-ttu-id="269e4-121">Si las notificaciones no están presentes, devuelva `false`, indicando que se debería llamar a la directiva de autorización de nuevo si otras directivas de autorización agregan más conjuntos de notificaciones a `EvaluationContext`.</span><span class="sxs-lookup"><span data-stu-id="269e4-121">If the claims are not present, return `false`, indicating that the authorization policy should be called again if other authorization policies add more claim sets to the `EvaluationContext`.</span></span>  
  
4. <span data-ttu-id="269e4-122">En escenarios de procesamiento más complejos, el segundo parámetro del método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> se utiliza para almacenar una variable de estado que la infraestructura de autorización devolverá durante cada llamada posterior realizada al método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> para una evaluación determinada.</span><span class="sxs-lookup"><span data-stu-id="269e4-122">In more complex processing scenarios, the second parameter of the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method is used to store a state variable that the authorization infrastructure will pass back during each subsequent call to the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method for a particular evaluation.</span></span>  
  
### <a name="to-specify-a-custom-authorization-policy-through-configuration"></a><span data-ttu-id="269e4-123">Para especificar una directiva de autorización personalizada mediante la configuración</span><span class="sxs-lookup"><span data-stu-id="269e4-123">To specify a custom authorization policy through configuration</span></span>  
  
1. <span data-ttu-id="269e4-124">Especifique el tipo de la directiva de autorización personalizada en el atributo `policyType` en el elemento `add` correspondiente al elemento `authorizationPolicies` del elemento `serviceAuthorization`.</span><span class="sxs-lookup"><span data-stu-id="269e4-124">Specify the type of the custom authorization policy in the `policyType` attribute in the `add` element in the `authorizationPolicies` element in the `serviceAuthorization` element.</span></span>  
  
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
  
### <a name="to-specify-a-custom-authorization-policy-through-code"></a><span data-ttu-id="269e4-125">Para especificar una directiva de autorización personalizada mediante código</span><span class="sxs-lookup"><span data-stu-id="269e4-125">To specify a custom authorization policy through code</span></span>  
  
1. <span data-ttu-id="269e4-126">Cree un <xref:System.Collections.Generic.List%601> de <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="269e4-126">Create a <xref:System.Collections.Generic.List%601> of <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2. <span data-ttu-id="269e4-127">Cree una instancia de la directiva de autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="269e4-127">Create an instance of the custom authorization policy.</span></span>  
  
3. <span data-ttu-id="269e4-128">Agregue la instancia de la directiva de autorización a la lista.</span><span class="sxs-lookup"><span data-stu-id="269e4-128">Add the authorization policy instance to the list.</span></span>  
  
4. <span data-ttu-id="269e4-129">Repita los pasos 2 y 3 para cada directiva de autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="269e4-129">Repeat steps 2 and 3 for each custom authorization policy.</span></span>  
  
5. <span data-ttu-id="269e4-130">Asigne una versión de solo lectura de la lista a la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>.</span><span class="sxs-lookup"><span data-stu-id="269e4-130">Assign a read-only version of the list to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A> property.</span></span>  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="269e4-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="269e4-131">Example</span></span>  

 <span data-ttu-id="269e4-132">En el siguiente ejemplo se muestra una implementación de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> completa.</span><span class="sxs-lookup"><span data-stu-id="269e4-132">The following example shows a complete <xref:System.IdentityModel.Policy.IAuthorizationPolicy> implementation.</span></span>  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="269e4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="269e4-133">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="269e4-134">Procedimiento para comparar notificaciones</span><span class="sxs-lookup"><span data-stu-id="269e4-134">How to: Compare Claims</span></span>](how-to-compare-claims.md)
- [<span data-ttu-id="269e4-135">Procedimiento para crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="269e4-135">How to: Create a Custom Authorization Manager for a Service</span></span>](how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="269e4-136">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="269e4-136">Authorization Policy</span></span>](../samples/authorization-policy.md)
