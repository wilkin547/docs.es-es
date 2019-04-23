---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 04caca0c580d26fde7fc9a3e3a11b7a8fed26d65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225526"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="dab8e-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="dab8e-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="dab8e-103">Esta interfaz enumera los dispositivos de entrada sin formato y solo la utiliza PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="dab8e-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dab8e-104">Esta API solo está destinada y es compatible con el equipo cliente local</span><span class="sxs-lookup"><span data-stu-id="dab8e-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="dab8e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="dab8e-105">Members</span></span>  
  
|<span data-ttu-id="dab8e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="dab8e-106">Member</span></span>|<span data-ttu-id="dab8e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dab8e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dab8e-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="dab8e-108">IEnumRAWINPUTDEVIC:Next</span></span>](ienumrawinputdevic-next.md)|<span data-ttu-id="dab8e-109">Enumera los elementos `celt` siguientes (es decir, las estructuras RAWINPUTDEVICE) de la lista del enumerador y los devuelve en `rgelt` junto con el número real de elementos enumerados en `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="dab8e-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="dab8e-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="dab8e-110">IEnumRAWINPUTDEVIC:Skip</span></span>](ienumrawinputdevic-skip.md)|<span data-ttu-id="dab8e-111">Indica al enumerador para omitir la próxima `celt` elementos de la enumeración para que la siguiente llamada a [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) no devolverá los elementos.</span><span class="sxs-lookup"><span data-stu-id="dab8e-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="dab8e-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="dab8e-112">IEnumRAWINPUTDEVIC:Reset</span></span>](ienumrawinputdevic-reset.md)|<span data-ttu-id="dab8e-113">Restablece la secuencia de enumeración al principio.</span><span class="sxs-lookup"><span data-stu-id="dab8e-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="dab8e-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="dab8e-114">IEnumRAWINPUTDEVIC:Clone</span></span>](ienumrawinputdevic-clone.md)|<span data-ttu-id="dab8e-115">Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.</span><span class="sxs-lookup"><span data-stu-id="dab8e-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dab8e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dab8e-116">See also</span></span>

- [<span data-ttu-id="dab8e-117">Acerca de la entrada sin formato</span><span class="sxs-lookup"><span data-stu-id="dab8e-117">About Raw Input</span></span>](/windows/desktop/inputdev/about-raw-input)
