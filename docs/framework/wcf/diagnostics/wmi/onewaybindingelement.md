---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 016ff823eb2c84a9f54c0763edadef1224e31517
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040058"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="74c55-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="74c55-102">OneWayBindingElement</span></span>
<span data-ttu-id="74c55-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="74c55-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c55-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74c55-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="74c55-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="74c55-105">Methods</span></span>  
 <span data-ttu-id="74c55-106">La clase OneWayBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="74c55-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="74c55-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="74c55-107">Properties</span></span>  
 <span data-ttu-id="74c55-108">La clase OneWayBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="74c55-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="74c55-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="74c55-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="74c55-110">Tipo de datos: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="74c55-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="74c55-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="74c55-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74c55-112">La configuración del grupo de canales.</span><span class="sxs-lookup"><span data-stu-id="74c55-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="74c55-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="74c55-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="74c55-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="74c55-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="74c55-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="74c55-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74c55-116">El número máximo de canales aceptados.</span><span class="sxs-lookup"><span data-stu-id="74c55-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="74c55-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="74c55-117">PacketRoutable</span></span>  
 <span data-ttu-id="74c55-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="74c55-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="74c55-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="74c55-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74c55-120">Valor que indica si el paquete se puede enrutar.</span><span class="sxs-lookup"><span data-stu-id="74c55-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74c55-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74c55-121">Requirements</span></span>  
  
|<span data-ttu-id="74c55-122">MOF</span><span class="sxs-lookup"><span data-stu-id="74c55-122">MOF</span></span>|<span data-ttu-id="74c55-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="74c55-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="74c55-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="74c55-124">Namespace</span></span>|<span data-ttu-id="74c55-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="74c55-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74c55-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="74c55-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
