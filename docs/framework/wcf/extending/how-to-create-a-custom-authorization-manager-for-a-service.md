---
title: Procedimiento para crear un administrador de autorización personalizado para un servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
ms.openlocfilehash: 9c28cb81b78f80505cfcf5f7e4dfdba083bd0793
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797112"
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a><span data-ttu-id="5d457-102">Procedimiento para crear un administrador de autorización personalizado para un servicio</span><span class="sxs-lookup"><span data-stu-id="5d457-102">How to: Create a Custom Authorization Manager for a Service</span></span>

<span data-ttu-id="5d457-103">La infraestructura del modelo de identidad de Windows Communication Foundation (WCF) admite un modelo de autorización basado en notificaciones extensible.</span><span class="sxs-lookup"><span data-stu-id="5d457-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports an extensible claims-based authorization model.</span></span> <span data-ttu-id="5d457-104">Las demandas se extraen de los tokens y opcionalmente son procesadas por directivas de autorización personalizadas y, a continuación, colocadas en <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="5d457-104">Claims are extracted from tokens and optionally processed by custom authorization policies and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="5d457-105">Un administrador de autorización examina las demandas en <xref:System.IdentityModel.Policy.AuthorizationContext> para tomar las decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="5d457-105">An authorization manager examines the claims in the <xref:System.IdentityModel.Policy.AuthorizationContext> to make authorization decisions.</span></span>

<span data-ttu-id="5d457-106">La clase <xref:System.ServiceModel.ServiceAuthorizationManager> toma de forma predeterminada, las decisiones de la autorización; sin embargo estas decisiones se pueden invalidar creando un administrador de autorización personalizado.</span><span class="sxs-lookup"><span data-stu-id="5d457-106">By default, authorization decisions are made by the <xref:System.ServiceModel.ServiceAuthorizationManager> class; however these decisions can be overridden by creating a custom authorization manager.</span></span> <span data-ttu-id="5d457-107">Para crear un administrador de autorización personalizado, cree una clase que derive de <xref:System.ServiceModel.ServiceAuthorizationManager> e implemente el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d457-107">To create a custom authorization manager, create a class that derives from <xref:System.ServiceModel.ServiceAuthorizationManager> and implement <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="5d457-108">Las decisiones de la autorización se toman en el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>, que devuelve `true` cuando se permite el acceso y `false` cuando se niega el acceso.</span><span class="sxs-lookup"><span data-stu-id="5d457-108">Authorization decisions are made in the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method, which returns `true` when access is granted and `false` when access is denied.</span></span>

<span data-ttu-id="5d457-109">Si la decisión de autorización depende del contenido del cuerpo del mensaje, utilice el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d457-109">If the authorization decision depends on the contents of the message body, use the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method.</span></span>

<span data-ttu-id="5d457-110">Debido a los problemas de rendimiento, en la medida de lo posible debe rediseñar su aplicación para que la decisión de autorización no requiera el acceso al cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5d457-110">Because of performance issues, if possible you should redesign your application so that the authorization decision does not require access to the message body.</span></span>

<span data-ttu-id="5d457-111">El registro del administrador de autorización personalizado para un servicio se puede hacer en código o configuración.</span><span class="sxs-lookup"><span data-stu-id="5d457-111">Registration of the custom authorization manager for a service can be done in code or configuration.</span></span>

### <a name="to-create-a-custom-authorization-manager"></a><span data-ttu-id="5d457-112">Para crear un administrador de autorización personalizado</span><span class="sxs-lookup"><span data-stu-id="5d457-112">To create a custom authorization manager</span></span>

1. <span data-ttu-id="5d457-113">Derive una clase de la clase <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="5d457-113">Derive a class from the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>

    [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
    [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]

2. <span data-ttu-id="5d457-114">Invalide el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> .</span><span class="sxs-lookup"><span data-stu-id="5d457-114">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method.</span></span>

    <span data-ttu-id="5d457-115">Utilice el <xref:System.ServiceModel.OperationContext> que se pasa al método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> para tomar las decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="5d457-115">Use the <xref:System.ServiceModel.OperationContext> that is passed to the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method to make authorization decisions.</span></span>

    <span data-ttu-id="5d457-116">El siguiente ejemplo de código utiliza el método <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> para buscar el `http://www.contoso.com/claims/allowedoperation` de la notificación personalizada y tomar una decisión de autorización.</span><span class="sxs-lookup"><span data-stu-id="5d457-116">The following code example uses the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> method to find the custom claim `http://www.contoso.com/claims/allowedoperation` to make an authorization decision.</span></span>

    [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
    [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]

### <a name="to-register-a-custom-authorization-manager-using-code"></a><span data-ttu-id="5d457-117">Para registrar a un administrador de autorización personalizado mediante código</span><span class="sxs-lookup"><span data-stu-id="5d457-117">To register a custom authorization manager using code</span></span>

1. <span data-ttu-id="5d457-118">Cree una instancia del administrador de autorización personalizado y asígnelo a la propiedad <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d457-118">Create an instance of the custom authorization manager and assign it to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> property.</span></span>

    <span data-ttu-id="5d457-119">Se puede tener acceso a <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d457-119">The <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> can be accessed using <xref:System.ServiceModel.ServiceHostBase.Authorization%2A> property.</span></span>

    <span data-ttu-id="5d457-120">El ejemplo de código siguiente registra el administrador de autorización personalizado `MyServiceAuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="5d457-120">The following code example registers the `MyServiceAuthorizationManager` custom authorization manager.</span></span>

    [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
    [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]

### <a name="to-register-a-custom-authorization-manager-using-configuration"></a><span data-ttu-id="5d457-121">Para registrar a un administrador de autorización personalizado mediante configuración</span><span class="sxs-lookup"><span data-stu-id="5d457-121">To register a custom authorization manager using configuration</span></span>

1. <span data-ttu-id="5d457-122">Abra el archivo de configuración para el servicio.</span><span class="sxs-lookup"><span data-stu-id="5d457-122">Open the configuration file for the service.</span></span>

2. <span data-ttu-id="5d457-123">Agregue un [ \<](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) [ >serviceAuthorizational>Behaviors.\<](../../configure-apps/file-schema/wcf/behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5d457-123">Add a [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md).</span></span>

    <span data-ttu-id="5d457-124">En el [ \<> serviceAuthorization](../../configure-apps/file-schema/wcf/serviceauthorization-element.md), agregue un `serviceAuthorizationManagerType` atributo y establezca su valor en el tipo que representa el administrador de autorización personalizado.</span><span class="sxs-lookup"><span data-stu-id="5d457-124">To the [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md), add a `serviceAuthorizationManagerType` attribute and set its value to the type that represents the custom authorization manager.</span></span>

3. <span data-ttu-id="5d457-125">Agregue un enlace que proteja la comunicación entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="5d457-125">Add a binding that secures the communication between the client and service.</span></span>

    <span data-ttu-id="5d457-126">El enlace que se elige para esta comunicación determina las demandas que se agregan al <xref:System.IdentityModel.Policy.AuthorizationContext>, que el administrador de autorización personalizado utiliza para tomar las decisiones de autorización.</span><span class="sxs-lookup"><span data-stu-id="5d457-126">The binding that is chosen for this communication determines the claims that are added to the <xref:System.IdentityModel.Policy.AuthorizationContext>, which the custom authorization manager uses to make authorization decisions.</span></span> <span data-ttu-id="5d457-127">Para obtener más información acerca de los enlaces proporcionados por el sistema, consulte [enlaces proporcionados](../system-provided-bindings.md)por el sistema.</span><span class="sxs-lookup"><span data-stu-id="5d457-127">For more details about the system-provided bindings, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>

4. <span data-ttu-id="5d457-128">Asocie el comportamiento a un punto de conexión de servicio agregando un `behaviorConfiguration` [ \<](../../configure-apps/file-schema/wcf/service.md) elemento de > de servicio y establezca el valor del atributo en el valor del atributo de nombre para el [ \<elemento de comportamiento >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="5d457-128">Associate the behavior to a service endpoint, by adding a [\<service>](../../configure-apps/file-schema/wcf/service.md) element and set the value of the `behaviorConfiguration` attribute to the value of the name attribute for the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    <span data-ttu-id="5d457-129">Para obtener más información acerca de cómo configurar un punto [de conexión de servicio, consulte Cómo: Cree un punto de conexión de](../feature-details/how-to-create-a-service-endpoint-in-configuration.md)servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="5d457-129">For more information about configuring a service endpoint, see [How to: Create a Service Endpoint in Configuration](../feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>

    <span data-ttu-id="5d457-130">El ejemplo de código siguiente registra el administrador de autorización personalizado `Samples.MyServiceAuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="5d457-130">The following code example registers the custom authorization manager `Samples.MyServiceAuthorizationManager`.</span></span>

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
    > <span data-ttu-id="5d457-131">Tenga en cuenta que cuando se especifica el serviceAuthorizationManagerType, la cadena debe contener el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="5d457-131">Note that when you specify the serviceAuthorizationManagerType, the string must contain the fully qualified type name.</span></span> <span data-ttu-id="5d457-132">una coma, y el nombre del ensamblado en el que el tipo está definido.</span><span class="sxs-lookup"><span data-stu-id="5d457-132">a comma, and the name of the assembly in which the type is defined.</span></span> <span data-ttu-id="5d457-133">Si deja fuera el nombre del ensamblado, WCF intentará cargar el tipo desde System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="5d457-133">If you leave out the assembly name, WCF will attempt to load the type from System.ServiceModel.dll.</span></span>

## <a name="example"></a><span data-ttu-id="5d457-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d457-134">Example</span></span>

<span data-ttu-id="5d457-135">El ejemplo de código siguiente muestra una implementación básica de una clase <xref:System.ServiceModel.ServiceAuthorizationManager> que incluye la invalidación del método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d457-135">The following code example demonstrates a basic implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class that includes overriding the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="5d457-136">El código de ejemplo examina <xref:System.IdentityModel.Policy.AuthorizationContext> para una demanda personalizada y devuelve `true` cuando el recurso para esa demanda de la costumbre coincide con el valor de la acción de <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="5d457-136">The example code examines the <xref:System.IdentityModel.Policy.AuthorizationContext> for a custom claim and returns `true` when the resource for that custom claim matches the action value from the <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="5d457-137">Para obtener una implementación más completa de <xref:System.ServiceModel.ServiceAuthorizationManager> una clase, vea [Directiva de autorización](../samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="5d457-137">For a more complete implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class, see [Authorization Policy](../samples/authorization-policy.md).</span></span>

[!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
[!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]

## <a name="see-also"></a><span data-ttu-id="5d457-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d457-138">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="5d457-139">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="5d457-139">Authorization Policy</span></span>](../samples/authorization-policy.md)
