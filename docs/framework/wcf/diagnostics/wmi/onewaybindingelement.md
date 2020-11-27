---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 806066a8845068413d2a52c78878f76b5f5fa34f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250377"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="278ed-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="278ed-102">OneWayBindingElement</span></span>

<span data-ttu-id="278ed-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="278ed-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="278ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="278ed-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="278ed-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="278ed-105">Methods</span></span>  

 <span data-ttu-id="278ed-106">La clase OneWayBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="278ed-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="278ed-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="278ed-107">Properties</span></span>  

 <span data-ttu-id="278ed-108">La clase OneWayBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="278ed-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="278ed-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="278ed-109">ChannelPoolSettings</span></span>  

 <span data-ttu-id="278ed-110">Tipo de datos: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="278ed-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="278ed-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="278ed-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="278ed-112">La configuración del grupo de canales.</span><span class="sxs-lookup"><span data-stu-id="278ed-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="278ed-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="278ed-113">MaxAcceptedChannels</span></span>  

 <span data-ttu-id="278ed-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="278ed-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="278ed-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="278ed-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="278ed-116">El número máximo de canales aceptados.</span><span class="sxs-lookup"><span data-stu-id="278ed-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="278ed-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="278ed-117">PacketRoutable</span></span>  

 <span data-ttu-id="278ed-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="278ed-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="278ed-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="278ed-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="278ed-120">Valor que indica si el paquete se puede enrutar.</span><span class="sxs-lookup"><span data-stu-id="278ed-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="278ed-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="278ed-121">Requirements</span></span>  
  
|<span data-ttu-id="278ed-122">MOF</span><span class="sxs-lookup"><span data-stu-id="278ed-122">MOF</span></span>|<span data-ttu-id="278ed-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="278ed-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="278ed-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="278ed-124">Namespace</span></span>|<span data-ttu-id="278ed-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="278ed-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="278ed-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="278ed-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
