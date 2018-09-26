---
title: '&lt;comContract&gt;'
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: e2addbada7f55076ae919d93c897991a7ec0fcd8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208029"
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="ff072-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="ff072-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="ff072-103">Especifica un contrato de servicio de integración de COM+.</span><span class="sxs-lookup"><span data-stu-id="ff072-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="ff072-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ff072-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ff072-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="ff072-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff072-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff072-106">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff072-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ff072-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ff072-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ff072-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff072-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff072-109">Attributes</span></span>  
  
|<span data-ttu-id="ff072-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="ff072-110">Attribute</span></span>|<span data-ttu-id="ff072-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff072-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff072-112">contrato</span><span class="sxs-lookup"><span data-stu-id="ff072-112">contract</span></span>|<span data-ttu-id="ff072-113">Una cadena que contiene el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="ff072-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="ff072-114">name</span><span class="sxs-lookup"><span data-stu-id="ff072-114">name</span></span>|<span data-ttu-id="ff072-115">Una cadena que contiene el nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="ff072-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="ff072-116">namespace</span><span class="sxs-lookup"><span data-stu-id="ff072-116">namespace</span></span>|<span data-ttu-id="ff072-117">Una cadena que contiene el espacio de nombres del contrato.</span><span class="sxs-lookup"><span data-stu-id="ff072-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="ff072-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="ff072-118">requiresSession</span></span>|<span data-ttu-id="ff072-119">Un valor booleano que especifica si el contrato sólo se puede utilizar en enlaces con canal.</span><span class="sxs-lookup"><span data-stu-id="ff072-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="ff072-120">Cuando se inicializa el servicio, el tiempo de ejecución de integración garantiza que este valor es coherente con el tipo de enlace que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ff072-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="ff072-121">Se genera una excepción si uno o más de los enlaces para el contrato están en conflicto.</span><span class="sxs-lookup"><span data-stu-id="ff072-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="ff072-122">Si esta propiedad es `false`, y un canal unidireccional está en uso y hay parámetros [fuera], también se genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="ff072-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff072-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ff072-123">Child Elements</span></span>  
  
|<span data-ttu-id="ff072-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff072-124">Element</span></span>|<span data-ttu-id="ff072-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff072-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff072-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="ff072-126">persistableTypes</span></span>|<span data-ttu-id="ff072-127">Todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="ff072-127">All the persistable types.</span></span>|  
|<span data-ttu-id="ff072-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="ff072-128">userDefinedTypes</span></span>|<span data-ttu-id="ff072-129">Una colección de tipos definidos por el usuario (UDT) que se va a incluir en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="ff072-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="ff072-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="ff072-130">exposedMethods</span></span>|<span data-ttu-id="ff072-131">Una colección de métodos COM+ que se exponen cuando la interfaz en un componente de COM+ se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="ff072-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff072-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ff072-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ff072-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff072-133">Element</span></span>|<span data-ttu-id="ff072-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff072-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff072-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="ff072-135">comContracts</span></span>|<span data-ttu-id="ff072-136">Contiene una colección de elementos `comContract`.</span><span class="sxs-lookup"><span data-stu-id="ff072-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff072-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff072-137">Remarks</span></span>  
 <span data-ttu-id="ff072-138">Contratos de servicio de integración de COM + están restringidos actualmente a la `http://tempuri.org` espacio de nombres y nombre de contrato se deriva de la interfaz COM de apoyo.</span><span class="sxs-lookup"><span data-stu-id="ff072-138">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="ff072-139">Puede, sin embargo, especificar las alternativas utilizando la sección `comContracts`, así como el elemento `comContract` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ff072-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="ff072-140">Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres, el nombre del contrato y los tipos definidos por el usuario que se van incluir, así como otros valores para un contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="ff072-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="ff072-141">Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.</span><span class="sxs-lookup"><span data-stu-id="ff072-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff072-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff072-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="ff072-143">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="ff072-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="ff072-144">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="ff072-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="ff072-145">Configuración de los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="ff072-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
