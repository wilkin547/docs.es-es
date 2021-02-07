---
description: 'Más información acerca de: <exposedMethod>'
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 7bf271ba03ee16c6a45726e2bcb522bf6f55d441
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664735"
---
# \<exposedMethod>

<span data-ttu-id="a7e8e-102">Representa un método de COM+ que se expone cuando la interfaz en un componente COM+ se expone como un servicio web.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="a7e8e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7e8e-103">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7e8e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a7e8e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a7e8e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7e8e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7e8e-106">Attributes</span></span>  
  
|<span data-ttu-id="a7e8e-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="a7e8e-107">Attribute</span></span>|<span data-ttu-id="a7e8e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7e8e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7e8e-109">name</span><span class="sxs-lookup"><span data-stu-id="a7e8e-109">name</span></span>|<span data-ttu-id="a7e8e-110">Una cadena que contiene el método de COM+ que se expone cuando la interfaz de un componente COM+ se expone como servicio Web.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-110">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7e8e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a7e8e-111">Child Elements</span></span>  

 <span data-ttu-id="a7e8e-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7e8e-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a7e8e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a7e8e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7e8e-114">Element</span></span>|<span data-ttu-id="a7e8e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7e8e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="a7e8e-116">Colección de [\<exposedMethod>](exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-116">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7e8e-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a7e8e-117">Remarks</span></span>  

 <span data-ttu-id="a7e8e-118">La herramienta de configuración de integración (ComSvcConfig.exe) de COM+ se puede usar para agregar métodos concretos de una interfaz COM para que aparezca en el contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-118">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="a7e8e-119">Por ejemplo, puede usar el comando siguiente para agregar los tres métodos con nombre de la interfaz COM `IFinances`, en el componente financiero `ItemOrders`, al contrato del servicio generado.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-119">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="a7e8e-120">Al ejecutar también el ComSvcConfig.exe, se genera el contrato de servicio siguiente que hace una lista de los métodos previamente mencionados como [\<exposedMethod>](exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-120">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="a7e8e-121">En el momento de la inicialización del servicio, el tiempo de ejecución intenta generar un contrato de servicio reflejando y agregando solo los métodos incluidos en la lista de [\<exposedMethod>](exposedmethod.md) elementos.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-121">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="a7e8e-122">Un seguimiento se genera para cada método de interfaz que no está incluido en el contrato del servicio.</span><span class="sxs-lookup"><span data-stu-id="a7e8e-122">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e8e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7e8e-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="a7e8e-124">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="a7e8e-124">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="a7e8e-125">Procedimiento para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="a7e8e-125">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
