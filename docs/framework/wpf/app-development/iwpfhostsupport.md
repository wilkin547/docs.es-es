---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964781"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="8d6e7-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="8d6e7-102">IWpfHostSupport</span></span>
<span data-ttu-id="8d6e7-103">Las aplicaciones que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] hospedan contenido a través de PresentationHost. exe implementan esta interfaz para proporcionar un punto de integración entre el host y PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d6e7-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d6e7-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="8d6e7-105">las aplicaciones como los exploradores Web pueden [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] hospedar contenido [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] , incluido y código XAML dinámico.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-105">applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="8d6e7-106">Para hospedar [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenido [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] , las aplicaciones crean una instancia del [control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="8d6e7-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="8d6e7-107">Para hospedar, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] crea una instancia de PresentationHost. exe, que proporciona el contenido [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] hospedado al host para su presentación en el [control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="8d6e7-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="8d6e7-108">La integración habilitada `IWpfHostSupport` por permite a PresentationHost. exe:</span><span class="sxs-lookup"><span data-stu-id="8d6e7-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="8d6e7-109">Detecte y registre con los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesado la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="8d6e7-110">Recibir mensajes de entrada de los dispositivos de entrada sin procesar registrados y reenviar los mensajes adecuados a la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="8d6e7-111">Consulte la aplicación host para obtener interfaces de usuario de progreso y error personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d6e7-112">Esta API solo está destinada y es compatible con el equipo cliente local</span><span class="sxs-lookup"><span data-stu-id="8d6e7-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="8d6e7-113">Miembros</span><span class="sxs-lookup"><span data-stu-id="8d6e7-113">Members</span></span>  
  
|<span data-ttu-id="8d6e7-114">Member</span><span class="sxs-lookup"><span data-stu-id="8d6e7-114">Member</span></span>|<span data-ttu-id="8d6e7-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8d6e7-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d6e7-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="8d6e7-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="8d6e7-117">Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="8d6e7-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="8d6e7-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="8d6e7-119">Lo llama PresentationHost.exe cada vez que se recibe un mensaje a menos que se devuelva E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="8d6e7-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="8d6e7-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="8d6e7-121">De forma predeterminada, PresentationHost. exe proporciona sus propias interfaces de usuario de error de implementación y progreso de implementación que se muestran cuando se implementa el contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
