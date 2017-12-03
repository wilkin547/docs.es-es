---
title: '&lt;exposedMethod&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ecef8049a980f662cce4c421f62ccd3703400d69
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltexposedmethodgt"></a><span data-ttu-id="aa52f-102">&lt;exposedMethod&gt;</span><span class="sxs-lookup"><span data-stu-id="aa52f-102">&lt;exposedMethod&gt;</span></span>
<span data-ttu-id="aa52f-103">Representa un método de COM+ que se expone cuando la interfaz en un componente COM+ se expone como un servicio web.</span><span class="sxs-lookup"><span data-stu-id="aa52f-103">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="aa52f-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="aa52f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="aa52f-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="aa52f-105">\<comContracts></span></span>  
<span data-ttu-id="aa52f-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="aa52f-106">\<comContract></span></span>  
<span data-ttu-id="aa52f-107">\<métodos ></span><span class="sxs-lookup"><span data-stu-id="aa52f-107">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa52f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa52f-108">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa52f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aa52f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aa52f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aa52f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa52f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="aa52f-111">Attributes</span></span>  
  
|<span data-ttu-id="aa52f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="aa52f-112">Attribute</span></span>|<span data-ttu-id="aa52f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa52f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa52f-114">name</span><span class="sxs-lookup"><span data-stu-id="aa52f-114">name</span></span>|<span data-ttu-id="aa52f-115">Una cadena que contiene el método de COM+ que se expone cuando la interfaz de un componente COM+ se expone como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="aa52f-115">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa52f-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aa52f-116">Child Elements</span></span>  
 <span data-ttu-id="aa52f-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="aa52f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa52f-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aa52f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="aa52f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa52f-119">Element</span></span>|<span data-ttu-id="aa52f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa52f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa52f-121">\<exposedMethods ></span><span class="sxs-lookup"><span data-stu-id="aa52f-121">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="aa52f-122">Una colección de [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="aa52f-122">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa52f-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa52f-123">Remarks</span></span>  
 <span data-ttu-id="aa52f-124">La herramienta de configuración de integración (ComSvcConfig.exe) de COM+ se puede usar para agregar métodos concretos de una interfaz COM para que aparezca en el contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="aa52f-124">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="aa52f-125">Por ejemplo, puede usar el comando siguiente para agregar los tres métodos con nombre de la interfaz COM `IFinances`, en el componente financiero `ItemOrders`, al contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="aa52f-125">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="aa52f-126">Al ejecutar también el ComSvcConfig.exe, se genera el siguiente contrato de servicio lista de los métodos mencionados anteriormente como [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="aa52f-126">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 <span data-ttu-id="aa52f-127">En el momento de inicialización del servicio, el tiempo de ejecución intenta generar un contrato de servicio reflejando y agregando sólo los métodos incluidos en la lista de [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="aa52f-127">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="aa52f-128">Un seguimiento se genera para cada método de interfaz que no está incluido en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="aa52f-128">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa52f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa52f-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>  
 <xref:System.ServiceModel.Configuration.ComMethodElement>  
 [<span data-ttu-id="aa52f-130">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="aa52f-130">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="aa52f-131">Integración con aplicaciones COM +</span><span class="sxs-lookup"><span data-stu-id="aa52f-131">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="aa52f-132">Cómo: configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="aa52f-132">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
