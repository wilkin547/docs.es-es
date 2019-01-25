---
title: '&lt;exposedMethod&gt;'
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 0bfb56395217283eeba69c2f3b7569a89f576423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702046"
---
# <a name="ltexposedmethodgt"></a><span data-ttu-id="113c2-102">&lt;exposedMethod&gt;</span><span class="sxs-lookup"><span data-stu-id="113c2-102">&lt;exposedMethod&gt;</span></span>
<span data-ttu-id="113c2-103">Representa un método de COM+ que se expone cuando la interfaz en un componente COM+ se expone como un servicio web.</span><span class="sxs-lookup"><span data-stu-id="113c2-103">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="113c2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="113c2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="113c2-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="113c2-105">\<comContracts></span></span>  
<span data-ttu-id="113c2-106">\<comContract></span><span class="sxs-lookup"><span data-stu-id="113c2-106">\<comContract></span></span>  
<span data-ttu-id="113c2-107">\<métodos ></span><span class="sxs-lookup"><span data-stu-id="113c2-107">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113c2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="113c2-108">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="113c2-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="113c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="113c2-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="113c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="113c2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="113c2-111">Attributes</span></span>  
  
|<span data-ttu-id="113c2-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="113c2-112">Attribute</span></span>|<span data-ttu-id="113c2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="113c2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="113c2-114">name</span><span class="sxs-lookup"><span data-stu-id="113c2-114">name</span></span>|<span data-ttu-id="113c2-115">Una cadena que contiene el método de COM+ que se expone cuando la interfaz de un componente COM+ se expone como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="113c2-115">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="113c2-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="113c2-116">Child Elements</span></span>  
 <span data-ttu-id="113c2-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="113c2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="113c2-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="113c2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="113c2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="113c2-119">Element</span></span>|<span data-ttu-id="113c2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="113c2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="113c2-121">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="113c2-121">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="113c2-122">Una colección de [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="113c2-122">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="113c2-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="113c2-123">Remarks</span></span>  
 <span data-ttu-id="113c2-124">La herramienta de configuración de integración (ComSvcConfig.exe) de COM+ se puede usar para agregar métodos concretos de una interfaz COM para que aparezca en el contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="113c2-124">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="113c2-125">Por ejemplo, puede usar el comando siguiente para agregar los tres métodos con nombre de la interfaz COM `IFinances`, en el componente financiero `ItemOrders`, al contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="113c2-125">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="113c2-126">Al ejecutar también la ComSvcConfig.exe, se genera el siguiente contrato de servicio lista de los métodos mencionados anteriormente como [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="113c2-126">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="113c2-127">En el momento de inicialización del servicio, el tiempo de ejecución intenta generar un contrato de servicio reflejando y agregando sólo los métodos incluidos en la lista de [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="113c2-127">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="113c2-128">Un seguimiento se genera para cada método de interfaz que no está incluido en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="113c2-128">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113c2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="113c2-129">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="113c2-130">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="113c2-130">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="113c2-131">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="113c2-131">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="113c2-132">Cómo: Configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="113c2-132">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
