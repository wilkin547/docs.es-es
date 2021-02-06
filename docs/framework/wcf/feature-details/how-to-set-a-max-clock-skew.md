---
description: 'Más información acerca de cómo: establecer un sesgo de reloj máximo'
title: Procedimiento para establecer un sesgo de reloj máximo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: 688be1bb42dd7b30fce577082992741b76819e3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643207"
---
# <a name="how-to-set-a-max-clock-skew"></a><span data-ttu-id="f1497-103">Procedimiento para establecer un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="f1497-103">How to: Set a Max Clock Skew</span></span>

<span data-ttu-id="f1497-104">Las funciones críticas en el tiempo se pueden desbaratar si los ajustes del reloj en dos equipos son diferentes.</span><span class="sxs-lookup"><span data-stu-id="f1497-104">Time-critical functions can be derailed if the clock settings on two computers are different.</span></span> <span data-ttu-id="f1497-105">Para mitigar esta posibilidad, puede establecer la propiedad `MaxClockSkew` en <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="f1497-105">To mitigate this possibility, you can set the `MaxClockSkew` property to a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="f1497-106">Esta propiedad está disponible en dos clases:</span><span class="sxs-lookup"><span data-stu-id="f1497-106">This property is available on two classes:</span></span>  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
> <span data-ttu-id="f1497-107">En el caso de una conversación segura, `MaxClockSkew` se deben realizar cambios en la propiedad cuando se arranque el servicio o el cliente.</span><span class="sxs-lookup"><span data-stu-id="f1497-107">For a secure conversation, changes to the `MaxClockSkew` property  must be made when the service or client is bootstrapped.</span></span> <span data-ttu-id="f1497-108">Para ello, debe establecer la propiedad en la <xref:System.ServiceModel.Channels.SecurityBindingElement> devuelta por la <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f1497-108">To do this, you must set the property on the <xref:System.ServiceModel.Channels.SecurityBindingElement> returned by the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="f1497-109">Para cambiar la propiedad en uno de los enlaces proporcionados por el sistema, debe encontrar el elemento de enlace de seguridad en la colección de enlaces y establecer la propiedad `MaxClockSkew` en un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="f1497-109">To change the property on one of the system-provided bindings, you must find the security binding element in the collection of bindings and set the `MaxClockSkew` property to a new value.</span></span> <span data-ttu-id="f1497-110">Dos clases derivan de <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="f1497-110">Two classes derive from the <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="f1497-111">Al recuperar el enlace de seguridad de la colección, debe convertir a uno de estos tipos para establecer correctamente la propiedad `MaxClockSkew`.</span><span class="sxs-lookup"><span data-stu-id="f1497-111">When retrieving the security binding from the collection, you must cast to one of these types in order to correctly set the `MaxClockSkew` property.</span></span> <span data-ttu-id="f1497-112">El siguiente ejemplo usa un <xref:System.ServiceModel.WSHttpBinding>, que utiliza el <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="f1497-112">The following example uses a <xref:System.ServiceModel.WSHttpBinding>, which uses the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="f1497-113">Para obtener una lista que especifica qué tipo de enlace de seguridad utilizar en cada enlace proporcionado por el sistema, consulte [enlaces proporcionados](../system-provided-bindings.md)por el sistema.</span><span class="sxs-lookup"><span data-stu-id="f1497-113">For a list that specifies which type of security binding to use in each system-provided binding, see [System-Provided Bindings](../system-provided-bindings.md).</span></span>  
  
## <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a><span data-ttu-id="f1497-114">Para crear un enlace personalizado con un nuevo valor de sesgo de reloj en código</span><span class="sxs-lookup"><span data-stu-id="f1497-114">To create a custom binding with a new clock skew value in code</span></span>  
  
> [!WARNING]
> <span data-ttu-id="f1497-115">Agregue referencias a los siguientes espacios de nombres en el código: <xref:System.ServiceModel.Channels> ,, <xref:System.ServiceModel.Description> <xref:System.Security.Permissions> y <xref:System.ServiceModel.Security.Tokens> .</span><span class="sxs-lookup"><span data-stu-id="f1497-115">Add references to the following namespaces in your code: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, and <xref:System.ServiceModel.Security.Tokens>.</span></span>  
  
1. <span data-ttu-id="f1497-116">Cree una instancia de una clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f1497-116">Create an instance of a <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="f1497-117">Cree una nueva instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> llamando al método <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1497-117">Create a new instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class by calling the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="f1497-118">Utilice el método <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> para encontrar el elemento del enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1497-118">Use the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method of the <xref:System.ServiceModel.Channels.BindingElementCollection> class to find the security binding element.</span></span>  
  
4. <span data-ttu-id="f1497-119">Al utilizar el método <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>, convierta al tipo real.</span><span class="sxs-lookup"><span data-stu-id="f1497-119">When using the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method, cast to the actual type.</span></span> <span data-ttu-id="f1497-120">El ejemplo siguiente convierte al tipo <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="f1497-120">The example below casts to the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> type.</span></span>  
  
5. <span data-ttu-id="f1497-121">Establezca la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> en el elemento del enlace de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f1497-121">Set the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the security binding element.</span></span>  
  
6. <span data-ttu-id="f1497-122">Cree un <xref:System.ServiceModel.ServiceHost> con un tipo de servicio y dirección base adecuados.</span><span class="sxs-lookup"><span data-stu-id="f1497-122">Create a <xref:System.ServiceModel.ServiceHost> with an appropriate service type and base address.</span></span>  
  
7. <span data-ttu-id="f1497-123">Utilice el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> para agregar un extremo e incluir el <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="f1497-123">Use the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method to add an endpoint and include the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
## <a name="to-set-the-maxclockskew-in-configuration"></a><span data-ttu-id="f1497-124">Para establecer MaxClockSkew en la configuración</span><span class="sxs-lookup"><span data-stu-id="f1497-124">To set the MaxClockSkew in configuration</span></span>  
  
1. <span data-ttu-id="f1497-125">Cree un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) en la [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) sección del elemento.</span><span class="sxs-lookup"><span data-stu-id="f1497-125">Create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) in the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element section.</span></span>  
  
2. <span data-ttu-id="f1497-126">Cree un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f1497-126">Create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="f1497-127">El siguiente ejemplo lo define en `MaxClockSkewBinding`.</span><span class="sxs-lookup"><span data-stu-id="f1497-127">The following example sets it to `MaxClockSkewBinding`.</span></span>  
  
3. <span data-ttu-id="f1497-128">Agregue un elemento de codificación.</span><span class="sxs-lookup"><span data-stu-id="f1497-128">Add an encoding element.</span></span> <span data-ttu-id="f1497-129">En el ejemplo siguiente se agrega un [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="f1497-129">The example below adds a [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
4. <span data-ttu-id="f1497-130">Agregue un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento y establezca el `authenticationMode` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f1497-130">Add a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element and set the `authenticationMode` attribute to an appropriate setting.</span></span> <span data-ttu-id="f1497-131">El siguiente ejemplo establece el atributo en `Kerberos` para especificar que el servicio usa autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="f1497-131">The following example set the attribute to `Kerberos` to specify that the service use Windows authentication.</span></span>  
  
5. <span data-ttu-id="f1497-132">Agregue [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) y establezca el `maxClockSkew` atributo en un valor con el formato `"##:##:##"` .</span><span class="sxs-lookup"><span data-stu-id="f1497-132">Add a [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to a value in the form of `"##:##:##"`.</span></span> <span data-ttu-id="f1497-133">El siguiente ejemplo lo establece en 7 minutos.</span><span class="sxs-lookup"><span data-stu-id="f1497-133">The following example sets it to 7 minutes.</span></span> <span data-ttu-id="f1497-134">Opcionalmente, agregue [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) y establezca el `maxClockSkew` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f1497-134">Optionally, add a [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to an appropriate setting.</span></span>  
  
6. <span data-ttu-id="f1497-135">Agregue un elemento de transporte.</span><span class="sxs-lookup"><span data-stu-id="f1497-135">Add a transport element.</span></span> <span data-ttu-id="f1497-136">En el ejemplo siguiente se usa un [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="f1497-136">The following example uses an [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
7. <span data-ttu-id="f1497-137">En el caso de una conversación segura, la configuración de seguridad se debe producir en el bootstrap del [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f1497-137">For a secure conversation, the security settings must occur at the bootstrap in the [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1497-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1497-138">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f1497-139">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f1497-139">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
