---
title: "Cómo: Especificar el tipo de credencial de cliente"
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
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 35c3b5ee429f7c9337fa3c3e3eb0d0476e3f56d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="f8b24-102">Cómo: Especificar el tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="f8b24-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="f8b24-103">Después de establecer un modo de seguridad (ya sea transporte o mensaje), tiene la opción de establecer el tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="f8b24-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="f8b24-104">Esta propiedad especifica qué tipo de credencial debe proporcionar el cliente al servicio para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f8b24-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="f8b24-105">configuración del modo de seguridad (un paso necesario antes de establecer tipo de credencial de cliente), consulte [Cómo: establecer el modo de seguridad](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="f8b24-105"> setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="f8b24-106">Para establecer el tipo de credencial de cliente en el código</span><span class="sxs-lookup"><span data-stu-id="f8b24-106">To set the client credential type in code</span></span>  
  
1.  <span data-ttu-id="f8b24-107">Cree una instancia del enlace que el servicio va a usar.</span><span class="sxs-lookup"><span data-stu-id="f8b24-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="f8b24-108">En el ejemplo siguiente se utiliza el enlace <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f8b24-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2.  <span data-ttu-id="f8b24-109">Establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="f8b24-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="f8b24-110">Este ejemplo utiliza el modo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f8b24-110">This example uses the Message mode.</span></span>  
  
3.  <span data-ttu-id="f8b24-111">Establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="f8b24-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="f8b24-112">Este ejemplo establece el uso de la autenticación de Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="f8b24-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="f8b24-113">Para establecer el tipo de credencial en la configuración</span><span class="sxs-lookup"><span data-stu-id="f8b24-113">To set the client credential type in configuration</span></span>  
  
1.  <span data-ttu-id="f8b24-114">Agregar un [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f8b24-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2.  <span data-ttu-id="f8b24-115">Como un elemento secundario, agregue un [ \<enlaces >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f8b24-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3.  <span data-ttu-id="f8b24-116">Agregue un enlace adecuado.</span><span class="sxs-lookup"><span data-stu-id="f8b24-116">Add an appropriate binding.</span></span> <span data-ttu-id="f8b24-117">Este ejemplo se utiliza la [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f8b24-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4.  <span data-ttu-id="f8b24-118">Agregar un [ \<enlace >](../../../docs/framework/misc/binding.md) y establezca el `name` de atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f8b24-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="f8b24-119">Este ejemplo utiliza el nombre "SecureBinding".</span><span class="sxs-lookup"><span data-stu-id="f8b24-119">This example uses the name "SecureBinding".</span></span>  
  
5.  <span data-ttu-id="f8b24-120">Agregue un enlace `<security>`.</span><span class="sxs-lookup"><span data-stu-id="f8b24-120">Add a `<security>` binding.</span></span> <span data-ttu-id="f8b24-121">Establezca el atributo `mode` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f8b24-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="f8b24-122">Este ejemplo lo define en `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="f8b24-122">This example sets it to `"Message"`.</span></span>  
  
6.  <span data-ttu-id="f8b24-123">Agregue un elemento `<message>` o `<transport>`, tal y como se haya determinado en el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f8b24-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="f8b24-124">Establezca el atributo `clientCredentialType` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f8b24-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="f8b24-125">Este ejemplo usa `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="f8b24-125">This example uses `"Windows"`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8b24-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8b24-126">See Also</span></span>  
 [<span data-ttu-id="f8b24-127">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="f8b24-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="f8b24-128">Cómo establecer el modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="f8b24-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
