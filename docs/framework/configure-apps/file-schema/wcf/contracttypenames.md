---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: c67e5b9e82b96e27ce73512680bd4236b26ef4dd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855451"
---
# <a name="contracttypenames"></a><span data-ttu-id="fa8fd-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="fa8fd-101">\<contractTypeNames></span></span>
<span data-ttu-id="fa8fd-102">Una sección de configuración que especifica una lista de nombres de tipos de contrato, que son los nombres del contrato de los servicios que se están buscando, y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="fa8fd-103">Si se especifica más de un nombre del contrato, solo responderán los extremos del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="fa8fd-104">Tenga en cuenta que en Windows Communication Foundation (WCF), un punto de conexión solo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="fa8fd-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa8fd-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa8fd-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fa8fd-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fa8fd-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="fa8fd-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="fa8fd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dynamicEndpoint**](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="fa8fd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="fa8fd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> standardEndpoint**</span><span class="sxs-lookup"><span data-stu-id="fa8fd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="fa8fd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> discoveryClientSettings**](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="fa8fd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="fa8fd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> findCriteria**](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="fa8fd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="fa8fd-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> contractTypeNames**</span><span class="sxs-lookup"><span data-stu-id="fa8fd-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa8fd-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa8fd-113">Syntax</span></span>  
  
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
              <add name="String"
                   namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa8fd-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa8fd-114">Attributes and Elements</span></span>  
 <span data-ttu-id="fa8fd-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa8fd-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa8fd-116">Attributes</span></span>  
 <span data-ttu-id="fa8fd-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa8fd-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa8fd-118">Child Elements</span></span>  
  
|<span data-ttu-id="fa8fd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa8fd-119">Element</span></span>|<span data-ttu-id="fa8fd-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fa8fd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa8fd-121">\<add></span><span class="sxs-lookup"><span data-stu-id="fa8fd-121">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="fa8fd-122">Un nombre de tipo de contrato es una propiedad que hace referencia al conjunto de criterios que suele usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-122">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa8fd-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa8fd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fa8fd-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa8fd-124">Element</span></span>|<span data-ttu-id="fa8fd-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fa8fd-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa8fd-126">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="fa8fd-126">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="fa8fd-127">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="fa8fd-127">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="fa8fd-128">Los criterios se pueden agrupar en criterios de búsqueda (especificando qué servicios está buscando) y criterios de finalización de búsqueda (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="fa8fd-128">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa8fd-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa8fd-129">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
