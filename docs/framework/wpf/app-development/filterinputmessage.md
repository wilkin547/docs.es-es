---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 1a22071696ca012968e042e15cd8a9f4b876fd9f
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075363"
---
# <a name="filterinputmessage"></a><span data-ttu-id="09afa-102">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="09afa-102">FilterInputMessage</span></span>
<span data-ttu-id="09afa-103">Lo llama PresentationHost.exe cada vez que se recibe un mensaje a menos que se devuelva E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="09afa-103">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09afa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09afa-104">Syntax</span></span>  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09afa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09afa-105">Parameters</span></span>  
 `pMsg`  
  
 <span data-ttu-id="09afa-106">[in] Mensaje WM_INPUT enviado a la ventana que obtiene la entrada sin formato.</span><span class="sxs-lookup"><span data-stu-id="09afa-106">[in] The WM_INPUT message sent to the window that is getting raw input.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="09afa-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09afa-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="09afa-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="09afa-108">HRESULT:</span></span>  
  
 <span data-ttu-id="09afa-109">S_OK: el filtro no procesó el mensaje y se puede producir un procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="09afa-109">S_OK - The filter did not process the message and further processing may occur.</span></span>  
  
 <span data-ttu-id="09afa-110">S_FALSE: el filtro procesó este mensaje y no debe realizarse ningún procesamiento adicional.</span><span class="sxs-lookup"><span data-stu-id="09afa-110">S_FALSE - The filter processed this message and no further processing should occur.</span></span>  
  
 <span data-ttu-id="09afa-111">E_NOTIMPL: si se devuelve este valor, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) no se llama de nuevo.</span><span class="sxs-lookup"><span data-stu-id="09afa-111">E_NOTIMPL – If this value is returned, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) is not called again.</span></span> <span data-ttu-id="09afa-112">Esto se podría devolver desde una aplicación host que solo esté interesada en proporcionar interfaces de usuario personalizadas de progreso y error a PresentationHost.exe y que no esté interesada en que se reenvíen mensajes de entrada sin formato desde PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="09afa-112">This might be returned from a host application that is only interested in providing custom progress and error user interfaces to PresentationHost.exe is not interested in being forwarded raw input messages from PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09afa-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09afa-113">Remarks</span></span>  
 <span data-ttu-id="09afa-114">PresentationHost.exe es el destino de varios dispositivos de entrada sin formato, incluidos controles remotos, mouse y teclado.</span><span class="sxs-lookup"><span data-stu-id="09afa-114">PresentationHost.exe is the target of various raw input devices, including keyboard, mice, and remote controls.</span></span> <span data-ttu-id="09afa-115">A veces, el comportamiento de la aplicación host depende de entradas que de otra forma serían consumidas por PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="09afa-115">Sometimes, behavior in the host application is dependent on input that would otherwise be consumed by PresentationHost.exe.</span></span> <span data-ttu-id="09afa-116">Por ejemplo, una aplicación host puede depender de recibir ciertos mensajes de entrada para determinar si se debe o no mostrar determinados elementos de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="09afa-116">For example, a host application may depend on receiving certain input messages to determine whether or not to display specific user interface elements.</span></span>  
  
 <span data-ttu-id="09afa-117">Para permitir que la aplicación host recibir los mensajes de entrada necesarios para proporcionar estos comportamientos, PresentationHost.exe reenvía los mensajes de entrada sin formato adecuados para la aplicación hospedada mediante una llamada a [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span><span class="sxs-lookup"><span data-stu-id="09afa-117">To allow the host application to receive the necessary input messages to provide these behaviors, PresentationHost.exe forwards appropriate raw input messages to the hosted application by calling [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span></span>  
  
 <span data-ttu-id="09afa-118">La aplicación hospedada recibe los mensajes de entrada sin formato registrándose con el conjunto de dispositivos de entrada sin formato (dispositivos de interfaz humana) devueltos por [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span><span class="sxs-lookup"><span data-stu-id="09afa-118">The hosted application receives raw input messages by registering with the set of raw input devices (Human Interface Devices) returned by [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09afa-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="09afa-119">See Also</span></span>  
 [<span data-ttu-id="09afa-120">Notificación WM_INPUT</span><span class="sxs-lookup"><span data-stu-id="09afa-120">WM_INPUT Notification</span></span>](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
