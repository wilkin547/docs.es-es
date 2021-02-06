---
description: 'Más información acerca de: <comContract>'
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: fde1188a087f13da6629460bcebcea16ceefc0e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638670"
---
# \<comContract>

<span data-ttu-id="a09b1-102">Especifica un contrato de servicio de integración de COM+.</span><span class="sxs-lookup"><span data-stu-id="a09b1-102">Specifies a COM+ integration service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a><span data-ttu-id="a09b1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a09b1-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a09b1-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a09b1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a09b1-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a09b1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a09b1-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a09b1-106">Attributes</span></span>  
  
|<span data-ttu-id="a09b1-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="a09b1-107">Attribute</span></span>|<span data-ttu-id="a09b1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a09b1-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a09b1-109">contrato</span><span class="sxs-lookup"><span data-stu-id="a09b1-109">contract</span></span>|<span data-ttu-id="a09b1-110">Una cadena que contiene el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="a09b1-110">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="a09b1-111">name</span><span class="sxs-lookup"><span data-stu-id="a09b1-111">name</span></span>|<span data-ttu-id="a09b1-112">Una cadena que contiene el nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="a09b1-112">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="a09b1-113">espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a09b1-113">namespace</span></span>|<span data-ttu-id="a09b1-114">Una cadena que contiene el espacio de nombres del contrato.</span><span class="sxs-lookup"><span data-stu-id="a09b1-114">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="a09b1-115">requiresSession</span><span class="sxs-lookup"><span data-stu-id="a09b1-115">requiresSession</span></span>|<span data-ttu-id="a09b1-116">Un valor booleano que especifica si el contrato sólo se puede utilizar en enlaces con canal.</span><span class="sxs-lookup"><span data-stu-id="a09b1-116">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="a09b1-117">Cuando se inicializa el servicio, el tiempo de ejecución de integración garantiza que este valor es coherente con el tipo de enlace que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="a09b1-117">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="a09b1-118">Se genera una excepción si uno o más de los enlaces para el contrato están en conflicto.</span><span class="sxs-lookup"><span data-stu-id="a09b1-118">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="a09b1-119">Si esta propiedad es `false`, y un canal unidireccional está en uso y hay parámetros [fuera], también se genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="a09b1-119">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a09b1-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a09b1-120">Child Elements</span></span>  
  
|<span data-ttu-id="a09b1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a09b1-121">Element</span></span>|<span data-ttu-id="a09b1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a09b1-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a09b1-123">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="a09b1-123">persistableTypes</span></span>|<span data-ttu-id="a09b1-124">Todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="a09b1-124">All the persistable types.</span></span>|  
|<span data-ttu-id="a09b1-125">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="a09b1-125">userDefinedTypes</span></span>|<span data-ttu-id="a09b1-126">Una colección de tipos definidos por el usuario (UDT) que se va a incluir en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="a09b1-126">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="a09b1-127">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="a09b1-127">exposedMethods</span></span>|<span data-ttu-id="a09b1-128">Una colección de métodos COM+ que se exponen cuando la interfaz en un componente de COM+ se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="a09b1-128">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a09b1-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a09b1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="a09b1-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="a09b1-130">Element</span></span>|<span data-ttu-id="a09b1-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a09b1-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a09b1-132">comContracts</span><span class="sxs-lookup"><span data-stu-id="a09b1-132">comContracts</span></span>|<span data-ttu-id="a09b1-133">Contiene una colección de elementos `comContract`.</span><span class="sxs-lookup"><span data-stu-id="a09b1-133">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a09b1-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a09b1-134">Remarks</span></span>  

 <span data-ttu-id="a09b1-135">Los contratos de servicio de integración de COM+ están restringidos actualmente al `http://tempuri.org` espacio de nombres y el nombre del contrato se deriva de la interfaz com compatible.</span><span class="sxs-lookup"><span data-stu-id="a09b1-135">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="a09b1-136">Puede, sin embargo, especificar las alternativas utilizando la sección `comContracts`, así como el elemento `comContract` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a09b1-136">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="a09b1-137">Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres, el nombre del contrato y los tipos definidos por el usuario que se van incluir, así como otros valores para un contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="a09b1-137">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="a09b1-138">Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.</span><span class="sxs-lookup"><span data-stu-id="a09b1-138">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a09b1-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="a09b1-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="a09b1-140">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="a09b1-140">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="a09b1-141">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="a09b1-141">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
