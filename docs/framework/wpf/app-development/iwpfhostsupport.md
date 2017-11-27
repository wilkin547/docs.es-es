---
title: IWpfHostSupport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 85d4ed09d6c5ca17e148d531e6aac483ff737d51
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="de2d0-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="de2d0-102">IWpfHostSupport</span></span>
<span data-ttu-id="de2d0-103">Las aplicaciones que hospedan [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenido a través de PresentationHost.exe implementan esta interfaz para proporcionar un punto de integración entre el host y PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="de2d0-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de2d0-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de2d0-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="de2d0-105">pueden hospedar aplicaciones como exploradores Web [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] de contenido, incluidos los [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] perder XAML.</span><span class="sxs-lookup"><span data-stu-id="de2d0-105"> applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="de2d0-106">Para host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenido, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] aplicaciones crean una instancia de la [WebBrowser (control)](http://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="de2d0-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](http://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="de2d0-107">Hospedar, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] crea una instancia de PresentationHost.exe, que proporciona hospedado [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenido en el host para su presentación en el [WebBrowser (control)](http://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="de2d0-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](http://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="de2d0-108">La integración habilitada por `IWpfHostSupport` permite a PresentationHost.exe:</span><span class="sxs-lookup"><span data-stu-id="de2d0-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
-   <span data-ttu-id="de2d0-109">Detectar y registrar con los dispositivos de entrada sin formato (dispositivos de interfaz humana) que la aplicación host está interesada en.</span><span class="sxs-lookup"><span data-stu-id="de2d0-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
-   <span data-ttu-id="de2d0-110">Recibir mensajes de entrada de los dispositivos de entrada sin formato registrados y reenvíe los mensajes adecuados a la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="de2d0-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
-   <span data-ttu-id="de2d0-111">Consultar la aplicación host para interfaces de usuario personalizadas de progreso y de error.</span><span class="sxs-lookup"><span data-stu-id="de2d0-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de2d0-112">Esta API solo está destinada y es compatible con el equipo cliente local</span><span class="sxs-lookup"><span data-stu-id="de2d0-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="de2d0-113">Miembros</span><span class="sxs-lookup"><span data-stu-id="de2d0-113">Members</span></span>  
  
|<span data-ttu-id="de2d0-114">Miembro</span><span class="sxs-lookup"><span data-stu-id="de2d0-114">Member</span></span>|<span data-ttu-id="de2d0-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="de2d0-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de2d0-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="de2d0-116">GetRawInputDevices</span></span>](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|<span data-ttu-id="de2d0-117">Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="de2d0-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="de2d0-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="de2d0-118">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|<span data-ttu-id="de2d0-119">Lo llama PresentationHost.exe cada vez que se recibe un mensaje a menos que se devuelva E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="de2d0-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="de2d0-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="de2d0-120">GetCustomUI</span></span>](../../../../docs/framework/wpf/app-development/getcustomui.md)|<span data-ttu-id="de2d0-121">De manera predeterminada, PresentationHost.exe proporciona su propio progreso de la implementación y el error de implementación de interfaces de usuario que se muestran cuando se implementa contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="de2d0-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
