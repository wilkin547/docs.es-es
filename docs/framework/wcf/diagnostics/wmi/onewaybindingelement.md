---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: d84184febd6db3f233aae6fe558b8e0f50a9cb82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608841"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="1bc33-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="1bc33-102">OneWayBindingElement</span></span>
<span data-ttu-id="1bc33-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="1bc33-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc33-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bc33-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1bc33-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1bc33-105">Methods</span></span>  
 <span data-ttu-id="1bc33-106">La clase OneWayBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1bc33-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1bc33-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1bc33-107">Properties</span></span>  
 <span data-ttu-id="1bc33-108">La clase OneWayBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="1bc33-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="1bc33-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1bc33-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="1bc33-110">Tipo de datos: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1bc33-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="1bc33-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1bc33-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1bc33-112">La configuración del grupo de canales.</span><span class="sxs-lookup"><span data-stu-id="1bc33-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="1bc33-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="1bc33-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="1bc33-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="1bc33-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="1bc33-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1bc33-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1bc33-116">El número máximo de canales aceptados.</span><span class="sxs-lookup"><span data-stu-id="1bc33-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="1bc33-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="1bc33-117">PacketRoutable</span></span>  
 <span data-ttu-id="1bc33-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="1bc33-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="1bc33-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1bc33-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1bc33-120">Valor que indica si el paquete se puede enrutar.</span><span class="sxs-lookup"><span data-stu-id="1bc33-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bc33-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bc33-121">Requirements</span></span>  
  
|<span data-ttu-id="1bc33-122">MOF</span><span class="sxs-lookup"><span data-stu-id="1bc33-122">MOF</span></span>|<span data-ttu-id="1bc33-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1bc33-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1bc33-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1bc33-124">Namespace</span></span>|<span data-ttu-id="1bc33-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1bc33-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bc33-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bc33-126">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement>
