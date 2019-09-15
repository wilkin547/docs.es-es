---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 4fc7a5021f9f8d9e6badcd3e13266fb8f4bfe7a4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991756"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="a5fab-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="a5fab-102">GetRawInputDevices</span></span>
<span data-ttu-id="a5fab-103">Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="a5fab-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5fab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5fab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5fab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5fab-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="a5fab-106">enuncia Un puntero a un [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) para enumerar los dispositivos de entrada sin formato.</span><span class="sxs-lookup"><span data-stu-id="a5fab-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a5fab-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a5fab-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="a5fab-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="a5fab-108">HRESULT:</span></span>  
  
 <span data-ttu-id="a5fab-109">PresentationHost. exe solo usará S_OK- [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) si se devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="a5fab-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="a5fab-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a5fab-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5fab-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5fab-111">Remarks</span></span>  
 <span data-ttu-id="a5fab-112">Los dispositivos de entrada sin formato constituyen el conjunto de dispositivos de entrada que incluye teclados, mouse y otros dispositivos menos tradicionales, como los de control remoto.</span><span class="sxs-lookup"><span data-stu-id="a5fab-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="a5fab-113">Una vez que se ha recuperado la lista de dispositivos de entrada sin formato, PresentationHost.exe se registra con los dispositivos para recibir mensajes de notificación WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="a5fab-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5fab-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5fab-114">See also</span></span>

- [<span data-ttu-id="a5fab-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="a5fab-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="a5fab-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="a5fab-116">FilterInputMessage</span></span>](filterinputmessage.md)
