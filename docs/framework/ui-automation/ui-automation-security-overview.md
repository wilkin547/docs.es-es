---
title: Información general sobre la seguridad de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 293cee72e80e88215fccb3902eb88963814cb2ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400203"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="dd70d-102">Información general sobre la seguridad de UI Automation</span><span class="sxs-lookup"><span data-stu-id="dd70d-102">UI Automation Security Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="dd70d-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="dd70d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="dd70d-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="dd70d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="dd70d-105">Esta información general describe el modelo de seguridad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] en [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd70d-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span></span>  
  
<a name="User_Account_Control"></a>   
## <a name="user-account-control"></a><span data-ttu-id="dd70d-106">Control de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="dd70d-106">User Account Control</span></span>  
 <span data-ttu-id="dd70d-107">La seguridad es un aspecto muy importante de [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] y una de las innovaciones es la posibilidad de que los usuarios ejecuten como usuarios estándar (no administrador) sin que necesariamente se les impida ejecutar aplicaciones y servicios que requieren privilegios más altos.</span><span class="sxs-lookup"><span data-stu-id="dd70d-107">Security is a major focus of [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>  
  
 <span data-ttu-id="dd70d-108">En [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], la mayoría de las aplicaciones se proporcionan con un token estándar o un token administrativo.</span><span class="sxs-lookup"><span data-stu-id="dd70d-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="dd70d-109">Si una aplicación no se puede identificar como aplicación administrativa, se inicia como aplicación estándar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dd70d-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="dd70d-110">Para poder iniciar una aplicación identificada como administrativa, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] pide al usuario su consentimiento para ejecutar la aplicación con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="dd70d-110">Before an application identified as administrative can be launched, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="dd70d-111">La petición de consentimiento se muestra de forma predeterminada, aunque el usuario sea miembro del grupo de administradores local, porque los administradores ejecutan como usuarios estándar hasta que una aplicación o un componente del sistema que requiere credenciales administrativas solicita permiso para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="dd70d-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>  
  
<a name="Tasks_Requiring_Higher_Privileges"></a>   
## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="dd70d-112">Tareas que requieren privilegios de mayor nivel</span><span class="sxs-lookup"><span data-stu-id="dd70d-112">Tasks Requiring Higher Privileges</span></span>  
 <span data-ttu-id="dd70d-113">Cuando un usuario intenta realizar una tarea que requiere privilegios administrativos, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presenta un cuadro de diálogo que pide al usuario su consentimiento para continuar.</span><span class="sxs-lookup"><span data-stu-id="dd70d-113">When a user attempts to perform a task that requires administrative privileges, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="dd70d-114">Este cuadro de diálogo está protegido contra la comunicación entre procesos, por lo que el software malintencionado no puede simular una entrada de usuario.</span><span class="sxs-lookup"><span data-stu-id="dd70d-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="dd70d-115">De forma similar, la pantalla de inicio de sesión de escritorio normalmente no es accesible para otros procesos.</span><span class="sxs-lookup"><span data-stu-id="dd70d-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>  
  
 <span data-ttu-id="dd70d-116">Los clientes de Automatización de la interfaz de usuario deben comunicarse con otros procesos, algunos de los cuales podrían ejecutarse con un nivel de privilegios superior.</span><span class="sxs-lookup"><span data-stu-id="dd70d-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="dd70d-117">Los clientes también podrían necesitar acceder a los cuadros de diálogo del sistema que normalmente no son visibles para otros procesos.</span><span class="sxs-lookup"><span data-stu-id="dd70d-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="dd70d-118">Por lo tanto, el sistema debe confiar en los clientes de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y se deben ejecutar con privilegios especiales.</span><span class="sxs-lookup"><span data-stu-id="dd70d-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>  
  
 <span data-ttu-id="dd70d-119">Para que las aplicaciones sean de confianza y poder comunicarse con aplicaciones que se ejecutan con un nivel de privilegios superior, deben estar firmadas.</span><span class="sxs-lookup"><span data-stu-id="dd70d-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>  
  
<a name="Manifest_Files"></a>   
## <a name="manifest-files"></a><span data-ttu-id="dd70d-120">Archivo de manifiesto</span><span class="sxs-lookup"><span data-stu-id="dd70d-120">Manifest Files</span></span>  
 <span data-ttu-id="dd70d-121">Para obtener acceso a la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]protegida del sistema, las aplicaciones deben compilarse con un archivo de manifiesto que incluya un atributo especial.</span><span class="sxs-lookup"><span data-stu-id="dd70d-121">To gain access to the protected system [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], applications must be built with a manifest file that includes a special attribute in the manifest file.</span></span> <span data-ttu-id="dd70d-122">Este atributo `uiAccess` se incluye en la etiqueta `requestedExecutionLevel` , como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dd70d-122">This `uiAccess` attribute is included in the `requestedExecutionLevel` tag, as follows:</span></span>  
  
 `<trustInfo xmlns="urn:0073chemas-microsoft-com:asm.v3">`  
  
 `<security>`  
  
 `<requestedPrivileges>`  
  
 `<requestedExecutionLevel`  
  
 `level="highestAvailable"`  
  
 `UIAccess="true" />`  
  
 `</requestedPrivileges>`  
  
 `</security>`  
  
 `</trustInfo>`  
  
 <span data-ttu-id="dd70d-123">El valor del atributo `level` en este código es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dd70d-123">The value of the `level` attribute in this code is an example only.</span></span>  
  
 <span data-ttu-id="dd70d-124">`UIAccess` es "false" de forma predeterminada; es decir, si se omite el atributo o si no hay ningún manifiesto para el ensamblado, la aplicación no podrá acceder a la [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]protegida.</span><span class="sxs-lookup"><span data-stu-id="dd70d-124">`UIAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="dd70d-125">Para más información sobre la seguridad de [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] , sobre cómo firmar aplicaciones y sobre la creación de manifiestos de ensamblado, vea "Procedimientos recomendados para desarrolladores e instrucciones para aplicaciones en un entorno con menos privilegios" en  [MSDN](http://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp).</span><span class="sxs-lookup"><span data-stu-id="dd70d-125">For more information on [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] security, on signing applications, and on creating assembly manifests, see "Developer Best Practices and Guidelines for Applications in a Least Privileged Environment" on  [MSDN](http://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp).</span></span>
