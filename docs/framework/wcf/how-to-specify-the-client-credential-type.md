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
ms.openlocfilehash: df18f89ee18bfa33ecc0aced617d168c805e3515
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138578"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="02d80-102">Procedimiento para especificar el tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="02d80-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="02d80-103">Después de establecer un modo de seguridad (ya sea transporte o mensaje), tiene la opción de establecer el tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="02d80-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="02d80-104">Esta propiedad especifica qué tipo de credencial debe proporcionar el cliente al servicio para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="02d80-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="02d80-105">Para obtener más información acerca de cómo establecer el modo de seguridad (un paso necesario antes de establecer el tipo de credencial de cliente), consulte [How para: Establezca el modo de seguridad ](how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="02d80-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="02d80-106">Para establecer el tipo de credencial de cliente en el código</span><span class="sxs-lookup"><span data-stu-id="02d80-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="02d80-107">Cree una instancia del enlace que el servicio va a usar.</span><span class="sxs-lookup"><span data-stu-id="02d80-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="02d80-108">En el ejemplo siguiente se utiliza el enlace <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="02d80-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="02d80-109">Establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="02d80-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="02d80-110">Este ejemplo utiliza el modo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="02d80-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="02d80-111">Establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="02d80-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="02d80-112">Este ejemplo establece el uso de la autenticación de Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="02d80-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="02d80-113">Para establecer el tipo de credencial en la configuración</span><span class="sxs-lookup"><span data-stu-id="02d80-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="02d80-114">Agregue un elemento [\<system. serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="02d80-114">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="02d80-115">Como elemento secundario, agregue un elemento [\<bindings >](../configure-apps/file-schema/wcf/bindings.md) .</span><span class="sxs-lookup"><span data-stu-id="02d80-115">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="02d80-116">Agregue un enlace adecuado.</span><span class="sxs-lookup"><span data-stu-id="02d80-116">Add an appropriate binding.</span></span> <span data-ttu-id="02d80-117">En este ejemplo se usa el elemento [\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="02d80-117">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="02d80-118">Agregue un elemento [\<binding >](../configure-apps/file-schema/wcf/bindings.md) y establezca el atributo `name` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="02d80-118">Add a [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="02d80-119">Este ejemplo utiliza el nombre "SecureBinding".</span><span class="sxs-lookup"><span data-stu-id="02d80-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="02d80-120">Agregue un enlace `<security>`.</span><span class="sxs-lookup"><span data-stu-id="02d80-120">Add a `<security>` binding.</span></span> <span data-ttu-id="02d80-121">Establezca el atributo `mode` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="02d80-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="02d80-122">Este ejemplo lo define en `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="02d80-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="02d80-123">Agregue un `<message>` o `<transport>` elemento, según lo determinado por el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="02d80-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="02d80-124">Establezca el atributo `clientCredentialType` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="02d80-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="02d80-125">Este ejemplo usa `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="02d80-125">This example uses `"Windows"`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02d80-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d80-126">See also</span></span>

- [<span data-ttu-id="02d80-127">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="02d80-127">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="02d80-128">Cómo: Establecer el modo de seguridad </span><span class="sxs-lookup"><span data-stu-id="02d80-128">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
