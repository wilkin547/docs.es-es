---
title: Filtrar para especificar el tipo de credencial de cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: 1138f0fe955782c71076d5c15c236d1d4ebbec01
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185060"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="84961-102">Filtrar para especificar el tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="84961-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="84961-103">Después de establecer un modo de seguridad (ya sea transporte o mensaje), tiene la opción de establecer el tipo de credencial de cliente.</span><span class="sxs-lookup"><span data-stu-id="84961-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="84961-104">Esta propiedad especifica qué tipo de credencial debe proporcionar el cliente al servicio para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="84961-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="84961-105">Para obtener más información acerca de cómo establecer el modo de seguridad (un paso necesario antes de establecer tipo de credencial de cliente), consulte [Cómo: Establecer el modo de seguridad](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="84961-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="84961-106">Para establecer el tipo de credencial de cliente en el código</span><span class="sxs-lookup"><span data-stu-id="84961-106">To set the client credential type in code</span></span>  
  
1.  <span data-ttu-id="84961-107">Cree una instancia del enlace que el servicio va a usar.</span><span class="sxs-lookup"><span data-stu-id="84961-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="84961-108">En el ejemplo siguiente se utiliza el enlace <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="84961-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2.  <span data-ttu-id="84961-109">Establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="84961-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="84961-110">Este ejemplo utiliza el modo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="84961-110">This example uses the Message mode.</span></span>  
  
3.  <span data-ttu-id="84961-111">Establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="84961-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="84961-112">Este ejemplo establece el uso de la autenticación de Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="84961-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="84961-113">Para establecer el tipo de credencial en la configuración</span><span class="sxs-lookup"><span data-stu-id="84961-113">To set the client credential type in configuration</span></span>  
  
1.  <span data-ttu-id="84961-114">Agregar un [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="84961-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2.  <span data-ttu-id="84961-115">Como un elemento secundario, agregue un [ \<enlaces >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="84961-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3.  <span data-ttu-id="84961-116">Agregue un enlace adecuado.</span><span class="sxs-lookup"><span data-stu-id="84961-116">Add an appropriate binding.</span></span> <span data-ttu-id="84961-117">Este ejemplo se usa el [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="84961-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4.  <span data-ttu-id="84961-118">Agregar un [ \<enlace >](../../../docs/framework/misc/binding.md) y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="84961-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="84961-119">Este ejemplo utiliza el nombre "SecureBinding".</span><span class="sxs-lookup"><span data-stu-id="84961-119">This example uses the name "SecureBinding".</span></span>  
  
5.  <span data-ttu-id="84961-120">Agregue un enlace `<security>`.</span><span class="sxs-lookup"><span data-stu-id="84961-120">Add a `<security>` binding.</span></span> <span data-ttu-id="84961-121">Establezca el atributo `mode` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="84961-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="84961-122">Este ejemplo lo define en `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="84961-122">This example sets it to `"Message"`.</span></span>  
  
6.  <span data-ttu-id="84961-123">Agregue un `<message>` o `<transport>` elemento, según lo determinado por el modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="84961-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="84961-124">Establezca el atributo `clientCredentialType` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="84961-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="84961-125">Este ejemplo usa `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="84961-125">This example uses `"Windows"`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="84961-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="84961-126">See also</span></span>

- [<span data-ttu-id="84961-127">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="84961-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="84961-128">Filtrar para establecer el modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="84961-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
