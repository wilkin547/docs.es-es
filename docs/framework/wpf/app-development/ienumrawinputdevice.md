---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 04caca0c580d26fde7fc9a3e3a11b7a8fed26d65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949570"
---
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
Esta interfaz enumera los dispositivos de entrada sin formato y solo la utiliza PresentationHost.exe.  
  
> [!NOTE]
>  Esta API solo está destinada y es compatible con el equipo cliente local  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md)|Enumera los elementos `celt` siguientes (es decir, las estructuras RAWINPUTDEVICE) de la lista del enumerador y los devuelve en `rgelt` junto con el número real de elementos enumerados en `pceltFetched`.|  
|[IEnumRAWINPUTDEVIC:Skip](ienumrawinputdevic-skip.md)|Indica al enumerador para omitir la próxima `celt` elementos de la enumeración para que la siguiente llamada a [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) no devolverá los elementos.|  
|[IEnumRAWINPUTDEVIC:Reset](ienumrawinputdevic-reset.md)|Restablece la secuencia de enumeración al principio.|  
|[IEnumRAWINPUTDEVIC:Clone](ienumrawinputdevic-clone.md)|Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.|  
  
## <a name="see-also"></a>Vea también

- [Acerca de la entrada sin formato](/windows/desktop/inputdev/about-raw-input)
