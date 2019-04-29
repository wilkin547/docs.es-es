---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 02d4a4ed1e96983e132a1943dd39f9f885e5596a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781854"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="522eb-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="522eb-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="522eb-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="522eb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="522eb-104">ID</span><span class="sxs-lookup"><span data-stu-id="522eb-104">ID</span></span>|<span data-ttu-id="522eb-105">212</span><span class="sxs-lookup"><span data-stu-id="522eb-105">212</span></span>|  
|<span data-ttu-id="522eb-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="522eb-106">Keywords</span></span>|<span data-ttu-id="522eb-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="522eb-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="522eb-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="522eb-108">Level</span></span>|<span data-ttu-id="522eb-109">Información</span><span class="sxs-lookup"><span data-stu-id="522eb-109">Information</span></span>|  
|<span data-ttu-id="522eb-110">Canal</span><span class="sxs-lookup"><span data-stu-id="522eb-110">Channel</span></span>|<span data-ttu-id="522eb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="522eb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="522eb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="522eb-112">Description</span></span>  
 <span data-ttu-id="522eb-113">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeCall` en `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="522eb-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="522eb-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="522eb-114">Message</span></span>  
 <span data-ttu-id="522eb-115">El distribuidor invocó 'BeforeCall' en un ParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="522eb-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="522eb-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="522eb-116">Details</span></span>  
  
|<span data-ttu-id="522eb-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="522eb-117">Data Item Name</span></span>|<span data-ttu-id="522eb-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="522eb-118">Data Item Type</span></span>|<span data-ttu-id="522eb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="522eb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="522eb-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="522eb-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="522eb-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="522eb-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="522eb-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="522eb-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="522eb-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="522eb-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="522eb-124">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="522eb-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="522eb-125">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="522eb-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="522eb-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="522eb-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="522eb-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="522eb-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
