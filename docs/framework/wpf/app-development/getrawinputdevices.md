---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 18564e0de8f88e89f8fb71d28ee3bfeccceea4ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507569"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="369e3-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="369e3-102">GetRawInputDevices</span></span>
<span data-ttu-id="369e3-103">Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="369e3-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="369e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="369e3-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="369e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="369e3-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="369e3-106">[out] Un puntero a un [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) para enumerar los dispositivos de entrada sin formato.</span><span class="sxs-lookup"><span data-stu-id="369e3-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="369e3-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="369e3-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="369e3-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="369e3-108">HRESULT:</span></span>  
  
 <span data-ttu-id="369e3-109">S_OK: [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) solo se usará PresentationHost.exe si se devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="369e3-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="369e3-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="369e3-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="369e3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="369e3-111">Remarks</span></span>  
 <span data-ttu-id="369e3-112">Los dispositivos de entrada sin formato constituyen el conjunto de dispositivos de entrada que incluye teclados, mouse y otros dispositivos menos tradicionales, como los de control remoto.</span><span class="sxs-lookup"><span data-stu-id="369e3-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="369e3-113">Una vez que se ha recuperado la lista de dispositivos de entrada sin formato, PresentationHost.exe se registra con los dispositivos para recibir mensajes de notificación WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="369e3-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="369e3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="369e3-114">See also</span></span>
- [<span data-ttu-id="369e3-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="369e3-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="369e3-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="369e3-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
