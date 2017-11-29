---
title: '&lt;comContracts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 168bd57652aca5f3c1b61c90abea5288bd1a6719
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcomcontractsgt"></a><span data-ttu-id="f86f2-102">&lt;comContracts&gt;</span><span class="sxs-lookup"><span data-stu-id="f86f2-102">&lt;comContracts&gt;</span></span>
<span data-ttu-id="f86f2-103">La sección de configuración `comContracts` contiene elementos que le permiten especificar varias propiedades de un contrato de servicios de la integración de COM+.</span><span class="sxs-lookup"><span data-stu-id="f86f2-103">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="f86f2-104">Especificar espacio de nombres y contrato</span><span class="sxs-lookup"><span data-stu-id="f86f2-104">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="f86f2-105">Contratos de servicio de integración de COM + están restringidos actualmente al espacio de nombres "http://tempuri.org" y el nombre del contrato se deriva de la interfaz COM de apoyo.</span><span class="sxs-lookup"><span data-stu-id="f86f2-105">COM+ integration service contracts are currently restricted to the "http://tempuri.org" namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="f86f2-106">Puede, sin embargo, especificar alternativas mediante la sección `comContracts` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f86f2-106">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="f86f2-107">Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres y nombre del contrato del contrato de servicios, así como una opción para exigir el uso en enlaces con sesión.</span><span class="sxs-lookup"><span data-stu-id="f86f2-107">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="f86f2-108">Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.</span><span class="sxs-lookup"><span data-stu-id="f86f2-108">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="f86f2-109">Cuando esta sección está vacía, la inicialización del servicio aplica un espacio de nombres y un nombre de contrato predeterminados tomados del identificador de la interfaz COM de apoyo.</span><span class="sxs-lookup"><span data-stu-id="f86f2-109">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="f86f2-110">Además, puede usar el [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elemento para especificar los métodos COM + que se exponen cuando la interfaz en un componente COM + se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="f86f2-110">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="f86f2-111">También puede usar el [ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) para especificar los tipos con persistencia utilizados en la integración.</span><span class="sxs-lookup"><span data-stu-id="f86f2-111">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="f86f2-112">Por último, puede usar el [ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) elemento para incluir definido tipos usuario (UDT) que deben incluirse en el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="f86f2-112">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86f2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f86f2-113">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="f86f2-114">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="f86f2-114">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)  
 [<span data-ttu-id="f86f2-115">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="f86f2-115">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)  
 [<span data-ttu-id="f86f2-116">\<userDefinedType ></span><span class="sxs-lookup"><span data-stu-id="f86f2-116">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)  
 [<span data-ttu-id="f86f2-117">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="f86f2-117">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)  
 [<span data-ttu-id="f86f2-118">Integración con aplicaciones COM +</span><span class="sxs-lookup"><span data-stu-id="f86f2-118">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="f86f2-119">Cómo: configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="f86f2-119">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
