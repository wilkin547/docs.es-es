---
title: <add> de <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 69a0bbbc8774251dbdc062875bb06453f355c882
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149145"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="90788-102">\<add> de \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="90788-102">\<add> of \<contractTypeNames></span></span>

<span data-ttu-id="90788-103">Un elemento de configuración que especifica el nombre del contrato de los servicios que se están buscando y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="90788-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="90788-104">Si se especifica más de un nombre del contrato, solo responderán los extremos del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="90788-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="90788-105">Tenga en cuenta que en Windows Communication Foundation (WCF), un punto de conexión solo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="90788-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="90788-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90788-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90788-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="90788-107">Attributes and Elements</span></span>  

 <span data-ttu-id="90788-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="90788-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90788-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="90788-109">Attributes</span></span>  
  
|<span data-ttu-id="90788-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="90788-110">Attribute</span></span>|<span data-ttu-id="90788-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="90788-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90788-112">name</span><span class="sxs-lookup"><span data-stu-id="90788-112">name</span></span>|<span data-ttu-id="90788-113">Cadena que especifica el nombre del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="90788-113">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="90788-114">namespace</span><span class="sxs-lookup"><span data-stu-id="90788-114">namespace</span></span>|<span data-ttu-id="90788-115">Cadena que especifica el espacio de nombres del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="90788-115">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90788-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="90788-116">Child Elements</span></span>  

 <span data-ttu-id="90788-117">None</span><span class="sxs-lookup"><span data-stu-id="90788-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90788-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="90788-118">Parent Elements</span></span>  
  
|<span data-ttu-id="90788-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="90788-119">Element</span></span>|<span data-ttu-id="90788-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="90788-120">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="90788-121">Colección de nombres de tipos de contrato.</span><span class="sxs-lookup"><span data-stu-id="90788-121">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90788-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="90788-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
