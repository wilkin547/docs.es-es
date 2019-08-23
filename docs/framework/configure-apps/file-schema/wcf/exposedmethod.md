---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 032139b714aa11079c7ee8610c332e404b3981ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919002"
---
# <a name="exposedmethod"></a><span data-ttu-id="4e0d0-101">\<> exposedMethod</span><span class="sxs-lookup"><span data-stu-id="4e0d0-101">\<exposedMethod></span></span>
<span data-ttu-id="4e0d0-102">Representa un método de COM+ que se expone cuando la interfaz en un componente COM+ se expone como un servicio web.</span><span class="sxs-lookup"><span data-stu-id="4e0d0-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="4e0d0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4e0d0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e0d0-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="4e0d0-104">\<comContracts></span></span>  
<span data-ttu-id="4e0d0-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="4e0d0-105">\<comContract></span></span>  
<span data-ttu-id="4e0d0-106">\<métodos ></span><span class="sxs-lookup"><span data-stu-id="4e0d0-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e0d0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e0d0-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e0d0-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4e0d0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4e0d0-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4e0d0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e0d0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4e0d0-110">Attributes</span></span>  
  
|<span data-ttu-id="4e0d0-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4e0d0-111">Attribute</span></span>|<span data-ttu-id="4e0d0-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e0d0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e0d0-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="4e0d0-113">name</span></span>|<span data-ttu-id="4e0d0-114">Una cadena que contiene el método de COM+ que se expone cuando la interfaz de un componente COM+ se expone como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="4e0d0-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e0d0-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4e0d0-115">Child Elements</span></span>  
 <span data-ttu-id="4e0d0-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4e0d0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e0d0-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4e0d0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4e0d0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e0d0-118">Element</span></span>|<span data-ttu-id="4e0d0-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e0d0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e0d0-120">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="4e0d0-120">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="4e0d0-121">Colección de [ \<elementos > exposedMethod](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="4e0d0-121">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e0d0-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e0d0-122">Remarks</span></span>  
 <span data-ttu-id="4e0d0-123">La herramienta de configuración de integración (ComSvcConfig.exe) de COM+ se puede usar para agregar métodos concretos de una interfaz COM para que aparezca en el contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="4e0d0-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="4e0d0-124">Por ejemplo, puede usar el comando siguiente para agregar los tres métodos con nombre de la interfaz COM `IFinances`, en el componente financiero `ItemOrders`, al contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="4e0d0-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="4e0d0-125">Al ejecutar también el archivo ComSvcConfig. exe, se genera el contrato de servicio siguiente que hace una lista de los métodos previamente mencionados como [ \<exposedMethod >](exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="4e0d0-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="4e0d0-126">En el momento de la inicialización del servicio, el tiempo de ejecución intenta generar un contrato de servicio reflejando y agregando solo los métodos incluidos en la lista de [ \<elementos > exposedMethod](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="4e0d0-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="4e0d0-127">Un seguimiento se genera para cada método de interfaz que no está incluido en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="4e0d0-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0d0-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e0d0-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="4e0d0-129">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="4e0d0-129">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="4e0d0-130">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="4e0d0-130">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="4e0d0-131">Cómo: Configurar el servicio COM+</span><span class="sxs-lookup"><span data-stu-id="4e0d0-131">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
