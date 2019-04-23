---
title: Habilitar la depuración de adjuntos JIT
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1696f9054d44a5f80a1f67cc38e315a8627d295
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078789"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="f6685-102">Habilitar la depuración de adjuntos JIT</span><span class="sxs-lookup"><span data-stu-id="f6685-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="f6685-103">La depuración de adjuntos JIT es la frase usada para describir el hecho de adjuntar un depurador a un proceso cuando se detectan errores, o se puede desencadenar mediante métodos o funciones concretos.</span><span class="sxs-lookup"><span data-stu-id="f6685-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="f6685-104">La depuración de adjuntos JIT se usa en las siguientes condiciones de error:</span><span class="sxs-lookup"><span data-stu-id="f6685-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
-   <span data-ttu-id="f6685-105">Excepciones no controladas (el código nativo y administrado).</span><span class="sxs-lookup"><span data-stu-id="f6685-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
-   <span data-ttu-id="f6685-106">Método <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o función [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) (familia Windows 7).</span><span class="sxs-lookup"><span data-stu-id="f6685-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
-   <span data-ttu-id="f6685-107">Errores irrecuperables de runtime.</span><span class="sxs-lookup"><span data-stu-id="f6685-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="f6685-108">La depuración de adjuntos JIT también se desencadena mediante llamadas a los métodos y las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6685-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
-   <span data-ttu-id="f6685-109">Método <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6685-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="f6685-110">Método <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6685-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="f6685-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) (función) (Win32).</span><span class="sxs-lookup"><span data-stu-id="f6685-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="f6685-112">Antes de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework proporcionaba claves del Registro independientes para controlar el comportamiento de los depuradores administrados y nativos.</span><span class="sxs-lookup"><span data-stu-id="f6685-112">Before the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="f6685-113">A partir de la [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], control se consolida en una única clave del registro: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="f6685-113">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="f6685-114">Los valores que puede establecer para esa clave determinan si se invoca un depurador y, de ser así, si se invoca con un cuadro de diálogo que necesita interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="f6685-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="f6685-115">Para obtener información acerca de cómo establecer esta clave del registro, consulte [Configurar depuración automática](https://go.microsoft.com/fwlink/?LinkId=181767).</span><span class="sxs-lookup"><span data-stu-id="f6685-115">For information about setting this registry key, see [Configuring Automatic Debugging](https://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6685-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6685-116">See also</span></span>

- [<span data-ttu-id="f6685-117">Depurar, trazar y generar perfiles</span><span class="sxs-lookup"><span data-stu-id="f6685-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
- [<span data-ttu-id="f6685-118">Facilitar la depuración de una imagen</span><span class="sxs-lookup"><span data-stu-id="f6685-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
