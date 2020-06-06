---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855311"
---
# \<exposedMethod>
<span data-ttu-id="89090-101">Representa un método de COM+ que se expone cuando la interfaz en un componente COM+ se expone como un servicio web.</span><span class="sxs-lookup"><span data-stu-id="89090-101">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="89090-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89090-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89090-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="89090-103">Attributes and Elements</span></span>  
 <span data-ttu-id="89090-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="89090-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89090-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="89090-105">Attributes</span></span>  
  
|<span data-ttu-id="89090-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="89090-106">Attribute</span></span>|<span data-ttu-id="89090-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="89090-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89090-108">name</span><span class="sxs-lookup"><span data-stu-id="89090-108">name</span></span>|<span data-ttu-id="89090-109">Una cadena que contiene el método de COM+ que se expone cuando la interfaz de un componente COM+ se expone como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="89090-109">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89090-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="89090-110">Child Elements</span></span>  
 <span data-ttu-id="89090-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="89090-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89090-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="89090-112">Parent Elements</span></span>  
  
|<span data-ttu-id="89090-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="89090-113">Element</span></span>|<span data-ttu-id="89090-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="89090-114">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="89090-115">Colección de [\<exposedMethod>](exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="89090-115">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89090-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89090-116">Remarks</span></span>  
 <span data-ttu-id="89090-117">La herramienta de configuración de integración (ComSvcConfig.exe) de COM+ se puede usar para agregar métodos concretos de una interfaz COM para que aparezca en el contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="89090-117">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="89090-118">Por ejemplo, puede usar el comando siguiente para agregar los tres métodos con nombre de la interfaz COM `IFinances`, en el componente financiero `ItemOrders`, al contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="89090-118">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="89090-119">Al ejecutar también el archivo ComSvcConfig. exe, se genera el contrato de servicio siguiente que hace una lista de los métodos previamente mencionados como [\<exposedMethod>](exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="89090-119">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="89090-120">En el momento de la inicialización del servicio, el tiempo de ejecución intenta generar un contrato de servicio reflejando y agregando solo los métodos incluidos en la lista de [\<exposedMethod>](exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="89090-120">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="89090-121">Un seguimiento se genera para cada método de interfaz que no está incluido en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="89090-121">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89090-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89090-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="89090-123">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="89090-123">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="89090-124">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="89090-124">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
