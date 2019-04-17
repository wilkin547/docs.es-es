---
title: Identity and Access Tool para Visual Studio 2012
ms.date: 03/30/2017
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
author: BrucePerlerMS
ms.openlocfilehash: 65d771b87cd3198848ffac387446abb17df18250
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611593"
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a><span data-ttu-id="83b21-102">Identity and Access Tool para Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="83b21-102">Identity and Access Tool for Visual Studio 2012</span></span>
<span data-ttu-id="83b21-103">En este tema se describe la nueva Identity and Access Tool para Visual Studio 11.</span><span class="sxs-lookup"><span data-stu-id="83b21-103">This topic describes the new Identity and Access Tool for Visual Studio 11.</span></span> <span data-ttu-id="83b21-104">Puede descargar esta herramienta desde la siguiente dirección URL: <https://go.microsoft.com/fwlink/?LinkID=245849> o directamente desde Visual Studio 11 buscando "identity" en el Administrador de extensiones.</span><span class="sxs-lookup"><span data-stu-id="83b21-104">You can download this tool from the following URL: <https://go.microsoft.com/fwlink/?LinkID=245849> or directly from within Visual Studio 11 by searching for "identity" directly in the Extensions Manager.</span></span>  
  
 <span data-ttu-id="83b21-105">Identity and Access Tool para Visual Studio 11 ofrece una experiencia en tiempo de desarrollo considerablemente simplificada en la que destacan los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="83b21-105">The Identity and Access Tool for Visual Studio 11 delivers a dramatically simplified development-time experience with the following highlights:</span></span>  
  
-   <span data-ttu-id="83b21-106">Al usar la nueva herramienta, se puede desarrollar mediante tipos de proyecto de aplicaciones web y tener IIS Express como destino.</span><span class="sxs-lookup"><span data-stu-id="83b21-106">Using the new tool, you can develop using web applications project types and target IIS express.</span></span>  
  
-   <span data-ttu-id="83b21-107">A diferencia de la autenticación abierta de solo protección, con la nueva herramienta se puede especificar el controlador o la página de detección de dominios de inicio locales (o cualquier otro punto de conexión que controle la experiencia de autenticación en la aplicación) y WIF configurará todas las solicitudes no autenticadas para dirigirse a estos, en lugar de redirigirlas al STS.</span><span class="sxs-lookup"><span data-stu-id="83b21-107">Unlike with the blanket protection-only authentication, with the new tool, you can specify your local home realm discovery page/controller (or any other endpoint handling the authentication experience within your application) and WIF will configure all unauthenticated requests to go there, instead of redirecting them to the STS.</span></span>  
  
-   <span data-ttu-id="83b21-108">La herramienta incluye un servicio de token de seguridad (STS) de prueba que se ejecuta en el equipo local al iniciar una sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="83b21-108">The tool includes a test Security Token Service (STS) which runs on your local machine when you launch a debug session.</span></span> <span data-ttu-id="83b21-109">Por consiguiente, ya no es necesario crear proyectos de STS personalizados ni ajustarlos para obtener las notificaciones requeridas para probar las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="83b21-109">Therefore, you no longer need to create custom STS projects and tweak them in order to get the claims you need to test your applications.</span></span> <span data-ttu-id="83b21-110">Los tipos y valores de notificación son totalmente personalizables.</span><span class="sxs-lookup"><span data-stu-id="83b21-110">The claim types and values are fully customizable.</span></span>  
  
-   <span data-ttu-id="83b21-111">La configuración general puede modificarse directamente a través de la interfaz de usuario de la herramienta, sin necesidad de editar el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="83b21-111">You can modify common settings directly via the tool’s UI, without the need to edit web.config.</span></span>  
  
-   <span data-ttu-id="83b21-112">Se puede establecer la federación con los Servicios de federación de Active Directory (AD FS) 2.0 (u otros proveedores de WS-Federation) en una única pantalla.</span><span class="sxs-lookup"><span data-stu-id="83b21-112">You can establish federation with Active Directory Federation Services (AD FS) 2.0 (or other WS-Federation providers) in a single screen.</span></span>  
  
-   <span data-ttu-id="83b21-113">La herramienta aprovecha las capacidades de Windows Azure Access Control Service (ACS) con una simple lista de casillas de verificación para todos los proveedores de identidad que desea usar: Facebook, Google, Live ID, Yahoo!, los proveedores de OpenID y cualquier proveedor de WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="83b21-113">The tool leverages Windows Azure Access Control Service (ACS) capabilities with a simple list of checkboxes for all the identity providers that you want to use: Facebook, Google, Live ID, Yahoo!, any OpenID provider, and any WS-Federation provider.</span></span> <span data-ttu-id="83b21-114">Seleccione los proveedores de identidad, haga clic en Aceptar y, a continuación, presione F5. Tanto la aplicación como ACS se configurarán automáticamente y la aplicación de prueba será compatible con ACS.</span><span class="sxs-lookup"><span data-stu-id="83b21-114">Select your identity providers, click OK, then F5, and both your application and ACS will be automatically configured and your test application will be ACS-aware.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b21-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="83b21-115">See also</span></span>

- [<span data-ttu-id="83b21-116">Características de WIF</span><span class="sxs-lookup"><span data-stu-id="83b21-116">WIF Features</span></span>](../../../docs/framework/security/wif-features.md)
