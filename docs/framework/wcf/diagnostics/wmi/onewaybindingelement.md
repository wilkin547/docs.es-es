---
description: 'Más información acerca de: OneWayBindingElement'
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 9c2ccc301bd854c7b85fcc53551ed6def329a8fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803092"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="84158-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="84158-103">OneWayBindingElement</span></span>

<span data-ttu-id="84158-104">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="84158-104">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84158-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84158-105">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="84158-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="84158-106">Methods</span></span>  

 <span data-ttu-id="84158-107">La clase OneWayBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="84158-107">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="84158-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="84158-108">Properties</span></span>  

 <span data-ttu-id="84158-109">La clase OneWayBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="84158-109">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="84158-110">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="84158-110">ChannelPoolSettings</span></span>  

 <span data-ttu-id="84158-111">Tipo de datos: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="84158-111">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="84158-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="84158-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="84158-113">La configuración del grupo de canales.</span><span class="sxs-lookup"><span data-stu-id="84158-113">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="84158-114">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="84158-114">MaxAcceptedChannels</span></span>  

 <span data-ttu-id="84158-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="84158-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="84158-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="84158-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="84158-117">El número máximo de canales aceptados.</span><span class="sxs-lookup"><span data-stu-id="84158-117">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="84158-118">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="84158-118">PacketRoutable</span></span>  

 <span data-ttu-id="84158-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="84158-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="84158-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="84158-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="84158-121">Valor que indica si el paquete se puede enrutar.</span><span class="sxs-lookup"><span data-stu-id="84158-121">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84158-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84158-122">Requirements</span></span>  
  
|<span data-ttu-id="84158-123">MOF</span><span class="sxs-lookup"><span data-stu-id="84158-123">MOF</span></span>|<span data-ttu-id="84158-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="84158-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="84158-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="84158-125">Namespace</span></span>|<span data-ttu-id="84158-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="84158-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84158-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="84158-127">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
