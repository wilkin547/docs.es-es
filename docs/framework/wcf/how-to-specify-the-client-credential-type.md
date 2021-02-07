---
description: 'Más información acerca de cómo: especificar el tipo de credencial de cliente'
title: Procedimiento para especificar el tipo de credencial de cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: f6536778e8814a1b5a4c03e22c0fe4108f89b6eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752540"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="27645-103">Procedimiento para especificar el tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="27645-103">How to: Specify the Client Credential Type</span></span>

<span data-ttu-id="27645-104">Después de establecer un modo de seguridad (ya sea transporte o mensaje), tiene la opción de establecer el tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="27645-104">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="27645-105">Esta propiedad especifica qué tipo de credencial debe proporcionar el cliente al servicio para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="27645-105">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="27645-106">Para obtener más información acerca de cómo establecer el modo de seguridad (un paso necesario antes de establecer el tipo de credencial de cliente), consulte [Cómo: establecer el modo de seguridad](how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="27645-106">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="27645-107">Para establecer el tipo de credencial de cliente en el código</span><span class="sxs-lookup"><span data-stu-id="27645-107">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="27645-108">Cree una instancia del enlace que el servicio va a usar.</span><span class="sxs-lookup"><span data-stu-id="27645-108">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="27645-109">En el ejemplo siguiente se utiliza el enlace <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="27645-109">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="27645-110">Establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="27645-110">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="27645-111">Este ejemplo utiliza el modo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="27645-111">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="27645-112">Establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="27645-112">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="27645-113">Este ejemplo establece el uso de la autenticación de Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="27645-113">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="27645-114">Para establecer el tipo de credencial en la configuración</span><span class="sxs-lookup"><span data-stu-id="27645-114">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="27645-115">Agregue un [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) elemento al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="27645-115">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="27645-116">Como elemento secundario, agregue un [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="27645-116">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="27645-117">Agregue un enlace adecuado.</span><span class="sxs-lookup"><span data-stu-id="27645-117">Add an appropriate binding.</span></span> <span data-ttu-id="27645-118">En este ejemplo se usa el [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="27645-118">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="27645-119">Agregue un [\<binding>](../configure-apps/file-schema/wcf/bindings.md) elemento y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="27645-119">Add a [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="27645-120">Este ejemplo utiliza el nombre "SecureBinding".</span><span class="sxs-lookup"><span data-stu-id="27645-120">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="27645-121">Agregue un enlace `<security>`.</span><span class="sxs-lookup"><span data-stu-id="27645-121">Add a `<security>` binding.</span></span> <span data-ttu-id="27645-122">Establezca el atributo `mode` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="27645-122">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="27645-123">Este ejemplo lo define en `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="27645-123">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="27645-124">Agregue un elemento `<message>`, tal y como se haya determinado en el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="27645-124">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="27645-125">Establezca el atributo `clientCredentialType` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="27645-125">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="27645-126">En este ejemplo se usa `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="27645-126">This example uses `"Windows"`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27645-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="27645-127">See also</span></span>

- [<span data-ttu-id="27645-128">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="27645-128">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="27645-129">Procedimiento para establecer el modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="27645-129">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
