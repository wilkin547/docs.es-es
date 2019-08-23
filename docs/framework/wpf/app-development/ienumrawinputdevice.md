---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 5249d7ea359db5d5c58ae87600f61048b465b4c1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964767"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="d3b53-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="d3b53-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="d3b53-103">Esta interfaz enumera los dispositivos de entrada sin formato y solo la utiliza PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="d3b53-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3b53-104">Esta API solo está destinada y es compatible con el equipo cliente local</span><span class="sxs-lookup"><span data-stu-id="d3b53-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="d3b53-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d3b53-105">Members</span></span>  
  
|<span data-ttu-id="d3b53-106">Member</span><span class="sxs-lookup"><span data-stu-id="d3b53-106">Member</span></span>|<span data-ttu-id="d3b53-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d3b53-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3b53-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="d3b53-108">IEnumRAWINPUTDEVIC:Next</span></span>](ienumrawinputdevic-next.md)|<span data-ttu-id="d3b53-109">Enumera los elementos `celt` siguientes (es decir, las estructuras RAWINPUTDEVICE) de la lista del enumerador y los devuelve en `rgelt` junto con el número real de elementos enumerados en `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="d3b53-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="d3b53-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="d3b53-110">IEnumRAWINPUTDEVIC:Skip</span></span>](ienumrawinputdevic-skip.md)|<span data-ttu-id="d3b53-111">Indica al enumerador que omita los elementos `celt` siguientes en la enumeración para que la siguiente llamada a [IEnumRAWINPUTDEVIC: Next](ienumrawinputdevic-next.md) no devuelva esos elementos.</span><span class="sxs-lookup"><span data-stu-id="d3b53-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="d3b53-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="d3b53-112">IEnumRAWINPUTDEVIC:Reset</span></span>](ienumrawinputdevic-reset.md)|<span data-ttu-id="d3b53-113">Restablece la secuencia de enumeración al principio.</span><span class="sxs-lookup"><span data-stu-id="d3b53-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="d3b53-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="d3b53-114">IEnumRAWINPUTDEVIC:Clone</span></span>](ienumrawinputdevic-clone.md)|<span data-ttu-id="d3b53-115">Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.</span><span class="sxs-lookup"><span data-stu-id="d3b53-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3b53-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3b53-116">See also</span></span>

- [<span data-ttu-id="d3b53-117">Acerca de la entrada sin formato</span><span class="sxs-lookup"><span data-stu-id="d3b53-117">About Raw Input</span></span>](/windows/desktop/inputdev/about-raw-input)
