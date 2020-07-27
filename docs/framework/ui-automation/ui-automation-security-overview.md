---
title: Información general sobre la seguridad de UI Automation
description: Lea información general sobre el modelo de seguridad para la automatización de la interfaz de usuario de Microsoft. Comprender el control de cuentas de usuario, las tareas que requieren más privilegios y archivos de manifiesto.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: d483f282db8ce8e5653d6d83361fa44df05f63f5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163140"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="8a34c-104">Información general sobre la seguridad de UI Automation</span><span class="sxs-lookup"><span data-stu-id="8a34c-104">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="8a34c-105">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8a34c-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8a34c-106">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="8a34c-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="8a34c-107">En esta información general se describe el modelo de seguridad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="8a34c-107">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="8a34c-108">Control de cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="8a34c-108">User Account Control</span></span>

<span data-ttu-id="8a34c-109">La seguridad es un enfoque importante de Windows Vista y entre las innovaciones es la posibilidad de que los usuarios se ejecuten como usuarios estándar (no administradores) sin que sea necesario bloquear la ejecución de aplicaciones y servicios que requieran privilegios más altos.</span><span class="sxs-lookup"><span data-stu-id="8a34c-109">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="8a34c-110">En Windows Vista, la mayoría de las aplicaciones se proporcionan con un token estándar o administrativo.</span><span class="sxs-lookup"><span data-stu-id="8a34c-110">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="8a34c-111">Si una aplicación no se puede identificar como aplicación administrativa, se inicia como aplicación estándar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8a34c-111">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="8a34c-112">Antes de que se pueda iniciar una aplicación identificada como administrativa, Windows Vista solicita al usuario su consentimiento para ejecutar la aplicación con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="8a34c-112">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="8a34c-113">La petición de consentimiento se muestra de forma predeterminada, aunque el usuario sea miembro del grupo de administradores local, porque los administradores ejecutan como usuarios estándar hasta que una aplicación o un componente del sistema que requiere credenciales administrativas solicita permiso para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="8a34c-113">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="8a34c-114">Tareas que requieren privilegios de mayor nivel</span><span class="sxs-lookup"><span data-stu-id="8a34c-114">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="8a34c-115">Cuando un usuario intenta realizar una tarea que requiere privilegios administrativos, Windows Vista muestra un cuadro de diálogo que pide al usuario que continúe.</span><span class="sxs-lookup"><span data-stu-id="8a34c-115">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="8a34c-116">Este cuadro de diálogo está protegido contra la comunicación entre procesos, por lo que el software malintencionado no puede simular una entrada de usuario.</span><span class="sxs-lookup"><span data-stu-id="8a34c-116">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="8a34c-117">De forma similar, la pantalla de inicio de sesión de escritorio normalmente no es accesible para otros procesos.</span><span class="sxs-lookup"><span data-stu-id="8a34c-117">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="8a34c-118">Los clientes de Automatización de la interfaz de usuario deben comunicarse con otros procesos, algunos de los cuales podrían ejecutarse con un nivel de privilegios superior.</span><span class="sxs-lookup"><span data-stu-id="8a34c-118">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="8a34c-119">Los clientes también podrían necesitar acceder a los cuadros de diálogo del sistema que normalmente no son visibles para otros procesos.</span><span class="sxs-lookup"><span data-stu-id="8a34c-119">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="8a34c-120">Por lo tanto, el sistema debe confiar en los clientes de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y se deben ejecutar con privilegios especiales.</span><span class="sxs-lookup"><span data-stu-id="8a34c-120">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="8a34c-121">Para que las aplicaciones sean de confianza y poder comunicarse con aplicaciones que se ejecutan con un nivel de privilegios superior, deben estar firmadas.</span><span class="sxs-lookup"><span data-stu-id="8a34c-121">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="8a34c-122">Archivo de manifiesto</span><span class="sxs-lookup"><span data-stu-id="8a34c-122">Manifest Files</span></span>

<span data-ttu-id="8a34c-123">Para obtener acceso a la interfaz de usuario del sistema protegida, las aplicaciones deben compilarse con un archivo de manifiesto que incluya el `uiAccess` atributo en la `requestedExecutionLevel` etiqueta, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8a34c-123">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="8a34c-124">El valor del atributo `level` en este código es solo un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8a34c-124">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="8a34c-125">`uiAccess`es "false" de forma predeterminada; es decir, si se omite el atributo o si no hay ningún manifiesto para el ensamblado, la aplicación no podrá obtener acceso a la interfaz de usuario protegida.</span><span class="sxs-lookup"><span data-stu-id="8a34c-125">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>
