---
title: "Mitigación: CspParameters.ParentWindowHandle espera HWND"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- CspParameters.ParentWindowHandle
- CspParameters.ParentWindowHandle retargeting change
ms.assetid: 33264333-71d6-4d43-8827-9c98878cfea7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b65aaf7149ca29b2af3efdf44ee9489a04c73a2
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-cspparametersparentwindowhandle-expects-an-hwnd"></a><span data-ttu-id="8e294-102">Mitigación: CspParameters.ParentWindowHandle espera HWND</span><span class="sxs-lookup"><span data-stu-id="8e294-102">Mitigation: CspParameters.ParentWindowHandle Expects an HWND</span></span>

<span data-ttu-id="8e294-103">La propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A>, introducida en .NET Framework 2.0, permite que una aplicación registre un valor de identificador de ventana principal, de modo que cualquier interfaz de usuario necesaria para tener acceso a la clave (por ejemplo, la solicitud del PIN o un cuadro de diálogo de consentimiento) se abra como elemento secundario modal de la ventana especificada.</span><span class="sxs-lookup"><span data-stu-id="8e294-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property, introduced in the .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or a consent dialog) opens as a modal child to the specified window.</span></span> <span data-ttu-id="8e294-104">A partir de las aplicaciones orientadas a .NET Framework 4.7, un identificador de ventana (HWND) puede asignarse a esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e294-104">Starting with applications that target the .NET Framework 4.7, a window handle (HWND) can be assigned to this property.</span></span>

<span data-ttu-id="8e294-105">Hasta la versión de .NET Framework 4.6.2, se esperaba que el valor asignado a la propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> fuese <xref:System.IntPtr>, que representa la ubicación de la memoria donde reside el valor del identificador de ventana.</span><span class="sxs-lookup"><span data-stu-id="8e294-105">In versions of the .NET Framework through the .NET Framework 4.6.2, the value assigned to the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property was expected to be an <xref:System.IntPtr> that represents the location in memory where the HWND value resided.</span></span> <span data-ttu-id="8e294-106">En Windows 7 y versiones anteriores del sistema operativo Windows, establecer la propiedad en `form.Handle` no tiene ningún efecto, pero en Windows 8 y versiones posteriores, da como resultado <xref:System.Security.Cryptography> con el mensaje "El parámetro no es correcto".</span><span class="sxs-lookup"><span data-stu-id="8e294-106">On Windows 7 and earlier versions of the Windows operating system, setting the property to `form.Handle` had no effect, but on Windows 8 and later versions, it results in a <xref:System.Security.Cryptography> with the message, "The parameter is incorrect."</span></span>

<span data-ttu-id="8e294-107">A partir de las aplicaciones que tienen como destino .NET Framework 4.7, una aplicación de Windows Forms puede establecer la propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> con un código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e294-107">Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="impact"></a><span data-ttu-id="8e294-108">Impacto</span><span class="sxs-lookup"><span data-stu-id="8e294-108">Impact</span></span>

<span data-ttu-id="8e294-109">Para las aplicaciones orientadas a .NET Framework 4.7 o versiones posteriores que desean registrar una relación de ventana principal, se recomienda usar la forma simplificada:</span><span class="sxs-lookup"><span data-stu-id="8e294-109">Applications targeting the .NET Framework 4.7 or later that wish to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
``` 

## <a name="mitigation"></a><span data-ttu-id="8e294-110">Mitigación</span><span class="sxs-lookup"><span data-stu-id="8e294-110">Mitigation</span></span>

<span data-ttu-id="8e294-111">Los desarrolladores que hayan identificado que el valor correcto es la dirección de la ubicación de memoria que mantiene el valor `form.Handle`, pueden rechazar este cambio de comportamiento si establecen el modificador de <xref:System.AppContext> `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` en `true`:</span><span class="sxs-lookup"><span data-stu-id="8e294-111">Developers who had identified that the correct value was the address of the memory location that held the `form.Handle` value can opt out of this change in behavior by setting the <xref:System.AppContext> switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="8e294-112">Configurando mediante programación los modificadores de compatibilidad en la instancia <xref:System.AppContext>.</span><span class="sxs-lookup"><span data-stu-id="8e294-112">By programmatically setting compatibility switches on the <xref:System.AppContext> instance.</span></span>

- <span data-ttu-id="8e294-113">Agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="8e294-113">By adding the following line to the `<runtime>` section of the app.config file:</span></span>
   
   ```xml
   <runtime>
     <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
   </runtime>
   ```

<span data-ttu-id="8e294-114">En cambio, los usuarios que deseen optar por el nuevo comportamiento de las aplicaciones ejecutadas en .NET Framework 4.7, pero que están orientadas a una versión anterior de .NET Framework, pueden establecer el modificador <xref:System.AppContext> en `false`.</span><span class="sxs-lookup"><span data-stu-id="8e294-114">Conversely, users who wish to opt in to the new behavior for applications that run under the .NET Framework 4.7 but target an earlier version of the .NET Framework versions can set the <xref:System.AppContext> switch to `false`.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="8e294-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e294-115">See also</span></span>

[<span data-ttu-id="8e294-116">Cambios de redestinación en .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8e294-116">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

