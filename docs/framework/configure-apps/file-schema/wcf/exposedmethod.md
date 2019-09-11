---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855311"
---
# <a name="exposedmethod"></a><span data-ttu-id="e5de4-101">\<> exposedMethod</span><span class="sxs-lookup"><span data-stu-id="e5de4-101">\<exposedMethod></span></span>
<span data-ttu-id="e5de4-102">Representa un método de COM+ que se expone cuando la interfaz en un componente COM+ se expone como un servicio web.</span><span class="sxs-lookup"><span data-stu-id="e5de4-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
<span data-ttu-id="e5de4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5de4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5de4-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e5de4-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e5de4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de compactos**](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="e5de4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="e5de4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> compactos**](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="e5de4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="e5de4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> exposedMethods**](exposedmethods.md)</span><span class="sxs-lookup"><span data-stu-id="e5de4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)</span></span>\
<span data-ttu-id="e5de4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> exposedMethod**</span><span class="sxs-lookup"><span data-stu-id="e5de4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5de4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5de4-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5de4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e5de4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e5de4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e5de4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5de4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5de4-112">Attributes</span></span>  
  
|<span data-ttu-id="e5de4-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e5de4-113">Attribute</span></span>|<span data-ttu-id="e5de4-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e5de4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5de4-115">Nombre</span><span class="sxs-lookup"><span data-stu-id="e5de4-115">name</span></span>|<span data-ttu-id="e5de4-116">Una cadena que contiene el método de COM+ que se expone cuando la interfaz de un componente COM+ se expone como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="e5de4-116">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5de4-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e5de4-117">Child Elements</span></span>  
 <span data-ttu-id="e5de4-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e5de4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5de4-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e5de4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e5de4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5de4-120">Element</span></span>|<span data-ttu-id="e5de4-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e5de4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5de4-122">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="e5de4-122">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="e5de4-123">Colección de [ \<elementos > exposedMethod](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="e5de4-123">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5de4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5de4-124">Remarks</span></span>  
 <span data-ttu-id="e5de4-125">La herramienta de configuración de integración (ComSvcConfig.exe) de COM+ se puede usar para agregar métodos concretos de una interfaz COM para que aparezca en el contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="e5de4-125">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="e5de4-126">Por ejemplo, puede usar el comando siguiente para agregar los tres métodos con nombre de la interfaz COM `IFinances`, en el componente financiero `ItemOrders`, al contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="e5de4-126">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="e5de4-127">Al ejecutar también el archivo ComSvcConfig. exe, se genera el contrato de servicio siguiente que hace una lista de los métodos previamente mencionados como [ \<exposedMethod >](exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="e5de4-127">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="e5de4-128">En el momento de la inicialización del servicio, el tiempo de ejecución intenta generar un contrato de servicio reflejando y agregando solo los métodos incluidos en la lista de [ \<elementos > exposedMethod](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="e5de4-128">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="e5de4-129">Un seguimiento se genera para cada método de interfaz que no está incluido en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="e5de4-129">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5de4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5de4-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="e5de4-131">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e5de4-131">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="e5de4-132">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="e5de4-132">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e5de4-133">Cómo: Configurar el servicio COM+</span><span class="sxs-lookup"><span data-stu-id="e5de4-133">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
