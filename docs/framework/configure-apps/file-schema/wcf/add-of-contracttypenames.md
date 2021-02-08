---
description: 'Más información sobre: <add> de <contractTypeNames>'
title: <add> de <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 0708aa277b4250cb4134a98ddf7af661840981a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804002"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="4b268-103">\<add> de \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="4b268-103">\<add> of \<contractTypeNames></span></span>

<span data-ttu-id="4b268-104">Un elemento de configuración que especifica el nombre del contrato de los servicios que se están buscando y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="4b268-104">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="4b268-105">Si se especifica más de un nombre del contrato, solo responderán los extremos del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="4b268-105">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="4b268-106">Tenga en cuenta que en Windows Communication Foundation (WCF), un punto de conexión solo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="4b268-106">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="4b268-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b268-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b268-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4b268-108">Attributes and Elements</span></span>  

 <span data-ttu-id="4b268-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4b268-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b268-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4b268-110">Attributes</span></span>  
  
|<span data-ttu-id="4b268-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4b268-111">Attribute</span></span>|<span data-ttu-id="4b268-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b268-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b268-113">name</span><span class="sxs-lookup"><span data-stu-id="4b268-113">name</span></span>|<span data-ttu-id="4b268-114">Cadena que especifica el nombre del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="4b268-114">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="4b268-115">espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4b268-115">namespace</span></span>|<span data-ttu-id="4b268-116">Cadena que especifica el espacio de nombres del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="4b268-116">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b268-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4b268-117">Child Elements</span></span>  

 <span data-ttu-id="4b268-118">None</span><span class="sxs-lookup"><span data-stu-id="4b268-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b268-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4b268-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4b268-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b268-120">Element</span></span>|<span data-ttu-id="4b268-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b268-121">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="4b268-122">Colección de nombres de tipos de contrato.</span><span class="sxs-lookup"><span data-stu-id="4b268-122">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b268-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b268-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
