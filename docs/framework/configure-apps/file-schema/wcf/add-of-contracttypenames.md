---
title: <add> de <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850536"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="00bd8-102">\<Agregar > de \<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="00bd8-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="00bd8-103">Un elemento de configuración que especifica el nombre del contrato de los servicios que se están buscando y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="00bd8-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="00bd8-104">Si se especifica más de un nombre del contrato, solo responderán los extremos del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="00bd8-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="00bd8-105">Tenga en cuenta que en Windows Communication Foundation (WCF), un punto de conexión solo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="00bd8-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="00bd8-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00bd8-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00bd8-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="00bd8-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="00bd8-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="00bd8-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="00bd8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dynamicEndpoint**](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="00bd8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="00bd8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> standardEndpoint**</span><span class="sxs-lookup"><span data-stu-id="00bd8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="00bd8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> discoveryClientSettings**](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="00bd8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="00bd8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> findCriteria**](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="00bd8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="00bd8-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> contractTypeNames**](contracttypenames.md)</span><span class="sxs-lookup"><span data-stu-id="00bd8-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)</span></span>\
<span data-ttu-id="00bd8-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="00bd8-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00bd8-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00bd8-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00bd8-116">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00bd8-116">Attributes and Elements</span></span>  
 <span data-ttu-id="00bd8-117">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="00bd8-117">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00bd8-118">Atributos</span><span class="sxs-lookup"><span data-stu-id="00bd8-118">Attributes</span></span>  
  
|<span data-ttu-id="00bd8-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="00bd8-119">Attribute</span></span>|<span data-ttu-id="00bd8-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="00bd8-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00bd8-121">Nombre</span><span class="sxs-lookup"><span data-stu-id="00bd8-121">name</span></span>|<span data-ttu-id="00bd8-122">Cadena que especifica el nombre del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="00bd8-122">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="00bd8-123">namespace</span><span class="sxs-lookup"><span data-stu-id="00bd8-123">namespace</span></span>|<span data-ttu-id="00bd8-124">Cadena que especifica el espacio de nombres del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="00bd8-124">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00bd8-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00bd8-125">Child Elements</span></span>  
 <span data-ttu-id="00bd8-126">None</span><span class="sxs-lookup"><span data-stu-id="00bd8-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00bd8-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00bd8-127">Parent Elements</span></span>  
  
|<span data-ttu-id="00bd8-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="00bd8-128">Element</span></span>|<span data-ttu-id="00bd8-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="00bd8-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00bd8-130">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="00bd8-130">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="00bd8-131">Colección de nombres de tipos de contrato.</span><span class="sxs-lookup"><span data-stu-id="00bd8-131">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00bd8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="00bd8-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
