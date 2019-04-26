---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 8694f83a731363f83cb09de43214eb4b211ef5ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704289"
---
# <a name="comcontract"></a><span data-ttu-id="03504-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="03504-101">\<comContract></span></span>
<span data-ttu-id="03504-102">Especifica un contrato de servicio de integración de COM+.</span><span class="sxs-lookup"><span data-stu-id="03504-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="03504-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="03504-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="03504-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="03504-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03504-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03504-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03504-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03504-106">Attributes and Elements</span></span>  
 <span data-ttu-id="03504-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03504-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03504-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="03504-108">Attributes</span></span>  
  
|<span data-ttu-id="03504-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="03504-109">Attribute</span></span>|<span data-ttu-id="03504-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="03504-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03504-111">contrato</span><span class="sxs-lookup"><span data-stu-id="03504-111">contract</span></span>|<span data-ttu-id="03504-112">Una cadena que contiene el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="03504-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="03504-113">name</span><span class="sxs-lookup"><span data-stu-id="03504-113">name</span></span>|<span data-ttu-id="03504-114">Una cadena que contiene el nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="03504-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="03504-115">namespace</span><span class="sxs-lookup"><span data-stu-id="03504-115">namespace</span></span>|<span data-ttu-id="03504-116">Una cadena que contiene el espacio de nombres del contrato.</span><span class="sxs-lookup"><span data-stu-id="03504-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="03504-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="03504-117">requiresSession</span></span>|<span data-ttu-id="03504-118">Un valor booleano que especifica si el contrato sólo se puede utilizar en enlaces con canal.</span><span class="sxs-lookup"><span data-stu-id="03504-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="03504-119">Cuando se inicializa el servicio, el tiempo de ejecución de integración garantiza que este valor es coherente con el tipo de enlace que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="03504-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="03504-120">Se genera una excepción si uno o más de los enlaces para el contrato están en conflicto.</span><span class="sxs-lookup"><span data-stu-id="03504-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="03504-121">Si esta propiedad es `false`, y un canal unidireccional está en uso y hay parámetros [fuera], también se genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="03504-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03504-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03504-122">Child Elements</span></span>  
  
|<span data-ttu-id="03504-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="03504-123">Element</span></span>|<span data-ttu-id="03504-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="03504-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03504-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="03504-125">persistableTypes</span></span>|<span data-ttu-id="03504-126">Todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="03504-126">All the persistable types.</span></span>|  
|<span data-ttu-id="03504-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="03504-127">userDefinedTypes</span></span>|<span data-ttu-id="03504-128">Una colección de tipos definidos por el usuario (UDT) que se va a incluir en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="03504-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="03504-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="03504-129">exposedMethods</span></span>|<span data-ttu-id="03504-130">Una colección de métodos COM+ que se exponen cuando la interfaz en un componente de COM+ se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="03504-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03504-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03504-131">Parent Elements</span></span>  
  
|<span data-ttu-id="03504-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="03504-132">Element</span></span>|<span data-ttu-id="03504-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="03504-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03504-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="03504-134">comContracts</span></span>|<span data-ttu-id="03504-135">Contiene una colección de elementos `comContract`.</span><span class="sxs-lookup"><span data-stu-id="03504-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03504-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03504-136">Remarks</span></span>  
 <span data-ttu-id="03504-137">Contratos de servicio de integración de COM + están restringidos actualmente a la `http://tempuri.org` espacio de nombres y nombre de contrato se deriva de la interfaz COM de apoyo.</span><span class="sxs-lookup"><span data-stu-id="03504-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="03504-138">Puede, sin embargo, especificar las alternativas utilizando la sección `comContracts`, así como el elemento `comContract` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="03504-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="03504-139">Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres, el nombre del contrato y los tipos definidos por el usuario que se van incluir, así como otros valores para un contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="03504-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="03504-140">Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.</span><span class="sxs-lookup"><span data-stu-id="03504-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03504-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="03504-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="03504-142">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="03504-142">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="03504-143">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="03504-143">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="03504-144">Cómo: Configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="03504-144">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
