---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 3499131fcb52f0a0ab6d0e78e165522b7092612f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781906"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="96d1d-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="96d1d-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="96d1d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="96d1d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96d1d-104">ID</span><span class="sxs-lookup"><span data-stu-id="96d1d-104">ID</span></span>|<span data-ttu-id="96d1d-105">208</span><span class="sxs-lookup"><span data-stu-id="96d1d-105">208</span></span>|  
|<span data-ttu-id="96d1d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="96d1d-106">Keywords</span></span>|<span data-ttu-id="96d1d-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="96d1d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="96d1d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="96d1d-108">Level</span></span>|<span data-ttu-id="96d1d-109">Información</span><span class="sxs-lookup"><span data-stu-id="96d1d-109">Information</span></span>|  
|<span data-ttu-id="96d1d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="96d1d-110">Channel</span></span>|<span data-ttu-id="96d1d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="96d1d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="96d1d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="96d1d-112">Description</span></span>  
 <span data-ttu-id="96d1d-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterReceive` en un inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="96d1d-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="96d1d-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="96d1d-114">Message</span></span>  
 <span data-ttu-id="96d1d-115">El distribuidor invocó 'AfterReceiveReply' en un MessageInspector del tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="96d1d-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="96d1d-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="96d1d-116">Details</span></span>  
  
|<span data-ttu-id="96d1d-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="96d1d-117">Data Item Name</span></span>|<span data-ttu-id="96d1d-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="96d1d-118">Data Item Type</span></span>|<span data-ttu-id="96d1d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="96d1d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="96d1d-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="96d1d-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="96d1d-121">Nombre completo (FullName) de CLR del tipo del `MessageInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="96d1d-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="96d1d-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="96d1d-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="96d1d-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="96d1d-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="96d1d-124">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="96d1d-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="96d1d-125">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="96d1d-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="96d1d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="96d1d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="96d1d-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="96d1d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
