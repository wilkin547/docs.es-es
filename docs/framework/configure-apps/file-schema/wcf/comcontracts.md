---
description: 'Más información acerca de: <comContracts>'
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 263210b4499274fe009a6b1b1e46c1f09dd007ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638657"
---
# \<comContracts>

<span data-ttu-id="1d2c1-102">La sección de configuración `comContracts` contiene elementos que le permiten especificar varias propiedades de un contrato de servicios de la integración de COM+.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="1d2c1-103">Especificar espacio de nombres y contrato</span><span class="sxs-lookup"><span data-stu-id="1d2c1-103">Specifying Namespace and Contract</span></span>  

 <span data-ttu-id="1d2c1-104">Los contratos de servicio de integración de COM+ están restringidos actualmente al `http://tempuri.org` espacio de nombres y el nombre del contrato se deriva de la interfaz com compatible.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="1d2c1-105">Puede, sin embargo, especificar alternativas mediante la sección `comContracts` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="1d2c1-106">Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres y nombre del contrato del contrato de servicios, así como una opción para exigir el uso en enlaces con sesión.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="1d2c1-107">Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="1d2c1-108">Cuando esta sección está vacía, la inicialización del servicio aplica un espacio de nombres y un nombre de contrato predeterminados tomados del identificador de la interfaz COM de apoyo.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="1d2c1-109">Además, puede utilizar el [\<exposedMethod>](exposedmethod.md) elemento para especificar los métodos com+ que se exponen cuando la interfaz en un componente com+ se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-109">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="1d2c1-110">También puede usar [\<persistableTypes>](persistabletypes.md) para especificar los tipos con persistencia que se usan en la integración de.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-110">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="1d2c1-111">Por último, puede usar el [\<userDefinedType>](userdefinedtype.md) elemento para incluir tipos definidos por el usuario (UDT) que se van a incluir en el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="1d2c1-111">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2c1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d2c1-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [<span data-ttu-id="1d2c1-113">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="1d2c1-113">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="1d2c1-114">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="1d2c1-114">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
