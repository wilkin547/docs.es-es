---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 016ff823eb2c84a9f54c0763edadef1224e31517
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168745"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="00076-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="00076-102">OneWayBindingElement</span></span>
<span data-ttu-id="00076-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="00076-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00076-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00076-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="00076-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="00076-105">Methods</span></span>  
 <span data-ttu-id="00076-106">La clase OneWayBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="00076-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="00076-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="00076-107">Properties</span></span>  
 <span data-ttu-id="00076-108">La clase OneWayBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="00076-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="00076-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="00076-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="00076-110">Tipo de datos: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="00076-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="00076-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="00076-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00076-112">La configuración del grupo de canales.</span><span class="sxs-lookup"><span data-stu-id="00076-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="00076-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="00076-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="00076-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="00076-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="00076-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="00076-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00076-116">El número máximo de canales aceptados.</span><span class="sxs-lookup"><span data-stu-id="00076-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="00076-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="00076-117">PacketRoutable</span></span>  
 <span data-ttu-id="00076-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="00076-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="00076-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="00076-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00076-120">Valor que indica si el paquete se puede enrutar.</span><span class="sxs-lookup"><span data-stu-id="00076-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00076-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00076-121">Requirements</span></span>  
  
|<span data-ttu-id="00076-122">MOF</span><span class="sxs-lookup"><span data-stu-id="00076-122">MOF</span></span>|<span data-ttu-id="00076-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="00076-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="00076-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="00076-124">Namespace</span></span>|<span data-ttu-id="00076-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="00076-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00076-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="00076-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
