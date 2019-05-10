---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 5d6bfb1e4aa1651cd8c3a869f681d71cfb15725c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751872"
---
# <a name="comcontract"></a><span data-ttu-id="0adbc-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="0adbc-101">\<comContract></span></span>
<span data-ttu-id="0adbc-102">Especifica un contrato de servicio de integración de COM+.</span><span class="sxs-lookup"><span data-stu-id="0adbc-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="0adbc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0adbc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0adbc-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="0adbc-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0adbc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0adbc-105">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0adbc-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0adbc-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0adbc-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0adbc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0adbc-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0adbc-108">Attributes</span></span>  
  
|<span data-ttu-id="0adbc-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0adbc-109">Attribute</span></span>|<span data-ttu-id="0adbc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0adbc-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0adbc-111">contrato</span><span class="sxs-lookup"><span data-stu-id="0adbc-111">contract</span></span>|<span data-ttu-id="0adbc-112">Una cadena que contiene el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="0adbc-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="0adbc-113">name</span><span class="sxs-lookup"><span data-stu-id="0adbc-113">name</span></span>|<span data-ttu-id="0adbc-114">Una cadena que contiene el nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="0adbc-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="0adbc-115">namespace</span><span class="sxs-lookup"><span data-stu-id="0adbc-115">namespace</span></span>|<span data-ttu-id="0adbc-116">Una cadena que contiene el espacio de nombres del contrato.</span><span class="sxs-lookup"><span data-stu-id="0adbc-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="0adbc-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="0adbc-117">requiresSession</span></span>|<span data-ttu-id="0adbc-118">Un valor booleano que especifica si el contrato sólo se puede utilizar en enlaces con canal.</span><span class="sxs-lookup"><span data-stu-id="0adbc-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="0adbc-119">Cuando se inicializa el servicio, el tiempo de ejecución de integración garantiza que este valor es coherente con el tipo de enlace que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="0adbc-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="0adbc-120">Se genera una excepción si uno o más de los enlaces para el contrato están en conflicto.</span><span class="sxs-lookup"><span data-stu-id="0adbc-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="0adbc-121">Si esta propiedad es `false`, y un canal unidireccional está en uso y hay parámetros [fuera], también se genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="0adbc-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0adbc-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0adbc-122">Child Elements</span></span>  
  
|<span data-ttu-id="0adbc-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="0adbc-123">Element</span></span>|<span data-ttu-id="0adbc-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="0adbc-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0adbc-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="0adbc-125">persistableTypes</span></span>|<span data-ttu-id="0adbc-126">Todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="0adbc-126">All the persistable types.</span></span>|  
|<span data-ttu-id="0adbc-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="0adbc-127">userDefinedTypes</span></span>|<span data-ttu-id="0adbc-128">Una colección de tipos definidos por el usuario (UDT) que se va a incluir en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="0adbc-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="0adbc-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="0adbc-129">exposedMethods</span></span>|<span data-ttu-id="0adbc-130">Una colección de métodos COM+ que se exponen cuando la interfaz en un componente de COM+ se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="0adbc-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0adbc-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0adbc-131">Parent Elements</span></span>  
  
|<span data-ttu-id="0adbc-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="0adbc-132">Element</span></span>|<span data-ttu-id="0adbc-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="0adbc-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0adbc-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="0adbc-134">comContracts</span></span>|<span data-ttu-id="0adbc-135">Contiene una colección de elementos `comContract`.</span><span class="sxs-lookup"><span data-stu-id="0adbc-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0adbc-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0adbc-136">Remarks</span></span>  
 <span data-ttu-id="0adbc-137">Contratos de servicio de integración de COM + están restringidos actualmente a la `http://tempuri.org` espacio de nombres y nombre de contrato se deriva de la interfaz COM de apoyo.</span><span class="sxs-lookup"><span data-stu-id="0adbc-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="0adbc-138">Puede, sin embargo, especificar las alternativas utilizando la sección `comContracts`, así como el elemento `comContract` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0adbc-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="0adbc-139">Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres, el nombre del contrato y los tipos definidos por el usuario que se van incluir, así como otros valores para un contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="0adbc-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
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
  
 <span data-ttu-id="0adbc-140">Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.</span><span class="sxs-lookup"><span data-stu-id="0adbc-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0adbc-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="0adbc-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="0adbc-142">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="0adbc-142">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="0adbc-143">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="0adbc-143">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="0adbc-144">Cómo: Configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="0adbc-144">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
