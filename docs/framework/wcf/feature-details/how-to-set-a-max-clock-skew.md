---
title: "Cómo: Establecer un sesgo de reloj máximo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 16dc6c7dfc474a04e6f3b27db0efd8fb2ca78b82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-max-clock-skew"></a><span data-ttu-id="6bfc3-102">Cómo: Establecer un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="6bfc3-102">How to: Set a Max Clock Skew</span></span>
<span data-ttu-id="6bfc3-103">Las funciones críticas en el tiempo se pueden desbaratar si los ajustes del reloj en dos equipos son diferentes.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-103">Time-critical functions can be derailed if the clock settings on two computers are different.</span></span> <span data-ttu-id="6bfc3-104">Para mitigar esta posibilidad, puede establecer la propiedad `MaxClockSkew` en <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-104">To mitigate this possibility, you can set the `MaxClockSkew` property to a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="6bfc3-105">Esta propiedad está disponible en dos clases:</span><span class="sxs-lookup"><span data-stu-id="6bfc3-105">This property is available on two classes:</span></span>  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6bfc3-106">Importante para una conversación segura, cambia a la `MaxClockSkew` propiedad se debe realizar cuando se arranca el servicio o cliente.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-106">Important   For a secure conversation, changes to the `MaxClockSkew` property  must be made when the service or client is bootstrapped.</span></span> <span data-ttu-id="6bfc3-107">Para ello, debe establecer la propiedad en el <xref:System.ServiceModel.Channels.SecurityBindingElement> devuelto por la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-107">To do this, you must set the property on the <xref:System.ServiceModel.Channels.SecurityBindingElement> returned by the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.</span></span>  
  
 <span data-ttu-id="6bfc3-108">Para cambiar la propiedad en uno de los enlaces proporcionados por el sistema, debe encontrar el elemento de enlace de seguridad en la colección de enlaces y establecer la propiedad `MaxClockSkew` en un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-108">To change the property on one of the system-provided bindings, you must find the security binding element in the collection of bindings and set the `MaxClockSkew` property to a new value.</span></span> <span data-ttu-id="6bfc3-109">Dos clases derivan de <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-109">Two classes derive from the <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="6bfc3-110">Al recuperar el enlace de seguridad de la colección, debe convertir a uno de estos tipos para establecer correctamente la propiedad `MaxClockSkew`.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-110">When retrieving the security binding from the collection, you must cast to one of these types in order to correctly set the `MaxClockSkew` property.</span></span> <span data-ttu-id="6bfc3-111">El siguiente ejemplo usa un <xref:System.ServiceModel.WSHttpBinding>, que utiliza el <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-111">The following example uses a <xref:System.ServiceModel.WSHttpBinding>, which uses the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="6bfc3-112">Para obtener una lista que especifica qué tipo de enlace de seguridad que se va a utilizar en cada enlace proporcionado por el sistema, consulte [enlaces proporcionados](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="6bfc3-112">For a list that specifies which type of security binding to use in each system-provided binding, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
### <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a><span data-ttu-id="6bfc3-113">Para crear un enlace personalizado con un nuevo valor de sesgo de reloj en código</span><span class="sxs-lookup"><span data-stu-id="6bfc3-113">To create a custom binding with a new clock skew value in code</span></span>  
  
1.  > [!WARNING]
    >  <span data-ttu-id="6bfc3-114">Nota: agregue referencias a los espacios de nombres siguientes en el código: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, y <xref:System.ServiceModel.Security.Tokens>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-114">Note   Add references to the following namespaces in your code: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, and <xref:System.ServiceModel.Security.Tokens>.</span></span>  
  
     <span data-ttu-id="6bfc3-115">Cree una instancia de una clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en <xref:System.ServiceModel.SecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-115">Create an instance of a <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
2.  <span data-ttu-id="6bfc3-116">Cree una nueva instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> llamando al método <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-116">Create a new instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class by calling the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3.  <span data-ttu-id="6bfc3-117">Utilice el método <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> para encontrar el elemento del enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-117">Use the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method of the <xref:System.ServiceModel.Channels.BindingElementCollection> class to find the security binding element.</span></span>  
  
4.  <span data-ttu-id="6bfc3-118">Al utilizar el método <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>, convierta al tipo real.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-118">When using the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method, cast to the actual type.</span></span> <span data-ttu-id="6bfc3-119">El ejemplo siguiente convierte al tipo <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-119">The example below casts to the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> type.</span></span>  
  
5.  <span data-ttu-id="6bfc3-120">Establezca la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> en el elemento del enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-120">Set the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the security binding element.</span></span>  
  
6.  <span data-ttu-id="6bfc3-121">Cree un <xref:System.ServiceModel.ServiceHost> con un tipo de servicio y dirección base adecuados.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-121">Create a <xref:System.ServiceModel.ServiceHost> with an appropriate service type and base address.</span></span>  
  
7.  <span data-ttu-id="6bfc3-122">Utilice el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> para agregar un extremo e incluir el <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-122">Use the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method to add an endpoint and include the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### <a name="to-set-the-maxclockskew-in-configuration"></a><span data-ttu-id="6bfc3-123">Para establecer MaxClockSkew en la configuración</span><span class="sxs-lookup"><span data-stu-id="6bfc3-123">To set the MaxClockSkew in configuration</span></span>  
  
1.  <span data-ttu-id="6bfc3-124">Crear un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) en el [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sección del elemento.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-124">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) in the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section.</span></span>  
  
2.  <span data-ttu-id="6bfc3-125">Crear un [ \<enlace >](../../../../docs/framework/misc/binding.md) y establezca el `name` de atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-125">Create a [\<binding>](../../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="6bfc3-126">El siguiente ejemplo lo define en `MaxClockSkewBinding`.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-126">The following example sets it to `MaxClockSkewBinding`.</span></span>  
  
3.  <span data-ttu-id="6bfc3-127">Agregue un elemento de codificación.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-127">Add an encoding element.</span></span> <span data-ttu-id="6bfc3-128">El siguiente ejemplo agrega un [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span><span class="sxs-lookup"><span data-stu-id="6bfc3-128">The example below adds a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
4.  <span data-ttu-id="6bfc3-129">Agregar un [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) y establezca el `authenticationMode` de atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-129">Add a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element and set the `authenticationMode` attribute to an appropriate setting.</span></span> <span data-ttu-id="6bfc3-130">El siguiente ejemplo establece el atributo en `Kerberos` para especificar que el servicio usa autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-130">The following example set the attribute to `Kerberos` to specify that the service use Windows authentication.</span></span>  
  
5.  <span data-ttu-id="6bfc3-131">Agregar un [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) y establezca el `maxClockSkew` de atributo en un valor en forma de `"##:##:##"`.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-131">Add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to a value in the form of `"##:##:##"`.</span></span> <span data-ttu-id="6bfc3-132">El siguiente ejemplo lo establece en 7 minutos.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-132">The following example sets it to 7 minutes.</span></span> <span data-ttu-id="6bfc3-133">Opcionalmente, agregue un [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) y establezca el `maxClockSkew` de atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-133">Optionally, add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to an appropriate setting.</span></span>  
  
6.  <span data-ttu-id="6bfc3-134">Agregue un elemento de transporte.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-134">Add a transport element.</span></span> <span data-ttu-id="6bfc3-135">En el ejemplo siguiente se usa un [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span><span class="sxs-lookup"><span data-stu-id="6bfc3-135">The following example uses an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
7.  <span data-ttu-id="6bfc3-136">Para una conversación segura, debe producirse la configuración de seguridad en el servicio de arranque en el [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6bfc3-136">For a secure conversation, the security settings must occur at the bootstrap in the [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6bfc3-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bfc3-137">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="6bfc3-138">Cómo: crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6bfc3-138">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
