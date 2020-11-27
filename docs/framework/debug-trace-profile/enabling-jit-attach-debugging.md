---
title: Habilitar la depuración de adjuntos JIT
description: Habilite la depuración de adjuntos Just-in-Time (JIT) para adjuntar un depurador a un proceso cuando se encuentre con errores. Se puede desencadenar mediante determinados métodos o funciones.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
ms.openlocfilehash: dc1c8608b0d16e618b5ad6144d492db3302532dc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273508"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="12a04-104">Habilitar la depuración de adjuntos JIT</span><span class="sxs-lookup"><span data-stu-id="12a04-104">Enabling JIT-Attach Debugging</span></span>

<span data-ttu-id="12a04-105">La depuración de adjuntos JIT es la frase usada para describir el hecho de adjuntar un depurador a un proceso cuando se detectan errores, o se puede desencadenar mediante métodos o funciones concretos.</span><span class="sxs-lookup"><span data-stu-id="12a04-105">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="12a04-106">La depuración de adjuntos JIT se usa en las siguientes condiciones de error:</span><span class="sxs-lookup"><span data-stu-id="12a04-106">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="12a04-107">Excepciones no controladas (el código nativo y administrado).</span><span class="sxs-lookup"><span data-stu-id="12a04-107">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="12a04-108">Método <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o función [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) (familia Windows 7).</span><span class="sxs-lookup"><span data-stu-id="12a04-108"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="12a04-109">Errores irrecuperables de runtime.</span><span class="sxs-lookup"><span data-stu-id="12a04-109">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="12a04-110">La depuración de adjuntos JIT también se desencadena mediante llamadas a los métodos y las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="12a04-110">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="12a04-111">Método <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="12a04-111"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="12a04-112">Método <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="12a04-112"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="12a04-113">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) (función) (Win32).</span><span class="sxs-lookup"><span data-stu-id="12a04-113">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) function (Win32).</span></span>  
  
 <span data-ttu-id="12a04-114">Antes del .NET Framework 4, el .NET Framework proporcionó claves de registro independientes para controlar el comportamiento de los depuradores administrados y nativos.</span><span class="sxs-lookup"><span data-stu-id="12a04-114">Before the .NET Framework 4, the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="12a04-115">A partir de la .NET Framework 4, el control se consolida en una única clave del registro: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="12a04-115">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="12a04-116">Los valores que puede establecer para esa clave determinan si se invoca un depurador y, de ser así, si se invoca con un cuadro de diálogo que necesita interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="12a04-116">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="12a04-117">Para obtener información acerca de cómo establecer esta clave del registro, vea configuración de la [depuración automática](/windows/win32/debug/configuring-automatic-debugging).</span><span class="sxs-lookup"><span data-stu-id="12a04-117">For information about setting this registry key, see [Configuring Automatic Debugging](/windows/win32/debug/configuring-automatic-debugging).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a04-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="12a04-118">See also</span></span>

- [<span data-ttu-id="12a04-119">Depurar, trazar y generar perfiles</span><span class="sxs-lookup"><span data-stu-id="12a04-119">Debugging, Tracing, and Profiling</span></span>](index.md)
- [<span data-ttu-id="12a04-120">Facilitar la depuración de una imagen</span><span class="sxs-lookup"><span data-stu-id="12a04-120">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)
