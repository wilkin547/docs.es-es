---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 91eafa46aa73b5e6d359fcbe48f098f9f8a4d0f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174517"
---
# <a name="exposedmethod"></a><span data-ttu-id="26160-101">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="26160-101">\<exposedMethod></span></span>
<span data-ttu-id="26160-102">Representa un método de COM+ que se expone cuando la interfaz en un componente COM+ se expone como un servicio web.</span><span class="sxs-lookup"><span data-stu-id="26160-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="26160-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="26160-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="26160-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="26160-104">\<comContracts></span></span>  
<span data-ttu-id="26160-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="26160-105">\<comContract></span></span>  
<span data-ttu-id="26160-106">\<métodos ></span><span class="sxs-lookup"><span data-stu-id="26160-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26160-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26160-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26160-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="26160-108">Attributes and Elements</span></span>  
 <span data-ttu-id="26160-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="26160-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26160-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="26160-110">Attributes</span></span>  
  
|<span data-ttu-id="26160-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="26160-111">Attribute</span></span>|<span data-ttu-id="26160-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="26160-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26160-113">name</span><span class="sxs-lookup"><span data-stu-id="26160-113">name</span></span>|<span data-ttu-id="26160-114">Una cadena que contiene el método de COM+ que se expone cuando la interfaz de un componente COM+ se expone como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="26160-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26160-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="26160-115">Child Elements</span></span>  
 <span data-ttu-id="26160-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="26160-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26160-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26160-117">Parent Elements</span></span>  
  
|<span data-ttu-id="26160-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="26160-118">Element</span></span>|<span data-ttu-id="26160-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="26160-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26160-120">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="26160-120">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="26160-121">Una colección de [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="26160-121">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26160-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26160-122">Remarks</span></span>  
 <span data-ttu-id="26160-123">La herramienta de configuración de integración (ComSvcConfig.exe) de COM+ se puede usar para agregar métodos concretos de una interfaz COM para que aparezca en el contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="26160-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="26160-124">Por ejemplo, puede usar el comando siguiente para agregar los tres métodos con nombre de la interfaz COM `IFinances`, en el componente financiero `ItemOrders`, al contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="26160-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="26160-125">Al ejecutar también la ComSvcConfig.exe, se genera el siguiente contrato de servicio lista de los métodos mencionados anteriormente como [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="26160-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="26160-126">En el momento de inicialización del servicio, el tiempo de ejecución intenta generar un contrato de servicio reflejando y agregando sólo los métodos incluidos en la lista de [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="26160-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="26160-127">Un seguimiento se genera para cada método de interfaz que no está incluido en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="26160-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26160-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="26160-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="26160-129">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="26160-129">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="26160-130">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="26160-130">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="26160-131">Cómo: Configurar el servicio COM +</span><span class="sxs-lookup"><span data-stu-id="26160-131">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
