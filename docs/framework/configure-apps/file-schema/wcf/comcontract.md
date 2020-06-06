---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850027"
---
# \<comContract>
<span data-ttu-id="dbd7a-101">Especifica un contrato de servicio de integración de COM+.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-101">Specifies a COM+ integration service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a><span data-ttu-id="dbd7a-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbd7a-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbd7a-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dbd7a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="dbd7a-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbd7a-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="dbd7a-105">Attributes</span></span>  
  
|<span data-ttu-id="dbd7a-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="dbd7a-106">Attribute</span></span>|<span data-ttu-id="dbd7a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbd7a-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbd7a-108">contrato</span><span class="sxs-lookup"><span data-stu-id="dbd7a-108">contract</span></span>|<span data-ttu-id="dbd7a-109">Una cadena que contiene el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-109">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="dbd7a-110">name</span><span class="sxs-lookup"><span data-stu-id="dbd7a-110">name</span></span>|<span data-ttu-id="dbd7a-111">Una cadena que contiene el nombre del contrato.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-111">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="dbd7a-112">espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="dbd7a-112">namespace</span></span>|<span data-ttu-id="dbd7a-113">Una cadena que contiene el espacio de nombres del contrato.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-113">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="dbd7a-114">requiresSession</span><span class="sxs-lookup"><span data-stu-id="dbd7a-114">requiresSession</span></span>|<span data-ttu-id="dbd7a-115">Un valor booleano que especifica si el contrato sólo se puede utilizar en enlaces con canal.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-115">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="dbd7a-116">Cuando se inicializa el servicio, el tiempo de ejecución de integración garantiza que este valor es coherente con el tipo de enlace que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-116">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="dbd7a-117">Se genera una excepción si uno o más de los enlaces para el contrato están en conflicto.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-117">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="dbd7a-118">Si esta propiedad es `false`, y un canal unidireccional está en uso y hay parámetros [fuera], también se genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-118">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbd7a-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dbd7a-119">Child Elements</span></span>  
  
|<span data-ttu-id="dbd7a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbd7a-120">Element</span></span>|<span data-ttu-id="dbd7a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbd7a-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbd7a-122">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="dbd7a-122">persistableTypes</span></span>|<span data-ttu-id="dbd7a-123">Todos los tipos con persistencia.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-123">All the persistable types.</span></span>|  
|<span data-ttu-id="dbd7a-124">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="dbd7a-124">userDefinedTypes</span></span>|<span data-ttu-id="dbd7a-125">Una colección de tipos definidos por el usuario (UDT) que se va a incluir en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-125">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="dbd7a-126">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="dbd7a-126">exposedMethods</span></span>|<span data-ttu-id="dbd7a-127">Una colección de métodos COM+ que se exponen cuando la interfaz en un componente de COM+ se expone como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-127">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dbd7a-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dbd7a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="dbd7a-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbd7a-129">Element</span></span>|<span data-ttu-id="dbd7a-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbd7a-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbd7a-131">comContracts</span><span class="sxs-lookup"><span data-stu-id="dbd7a-131">comContracts</span></span>|<span data-ttu-id="dbd7a-132">Contiene una colección de elementos `comContract`.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-132">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbd7a-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbd7a-133">Remarks</span></span>  
 <span data-ttu-id="dbd7a-134">Los contratos de servicio de integración de COM+ están restringidos actualmente al `http://tempuri.org` espacio de nombres y el nombre del contrato se deriva de la interfaz com compatible.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-134">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="dbd7a-135">Puede, sin embargo, especificar las alternativas utilizando la sección `comContracts`, así como el elemento `comContract` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-135">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="dbd7a-136">Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres, el nombre del contrato y los tipos definidos por el usuario que se van incluir, así como otros valores para un contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-136">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="dbd7a-137">Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.</span><span class="sxs-lookup"><span data-stu-id="dbd7a-137">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd7a-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbd7a-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="dbd7a-139">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="dbd7a-139">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="dbd7a-140">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="dbd7a-140">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
