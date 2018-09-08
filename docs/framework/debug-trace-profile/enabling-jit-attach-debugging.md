---
title: Habilitar la depuración de adjuntos JIT
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b92592500f0babf29891710cedf1228b0ddcb0e4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208444"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="271a3-102">Habilitar la depuración de adjuntos JIT</span><span class="sxs-lookup"><span data-stu-id="271a3-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="271a3-103">La depuración de adjuntos JIT es la frase usada para describir el hecho de adjuntar un depurador a un proceso cuando se detectan errores, o se puede desencadenar mediante métodos o funciones concretos.</span><span class="sxs-lookup"><span data-stu-id="271a3-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="271a3-104">La depuración de adjuntos JIT se usa en las siguientes condiciones de error:</span><span class="sxs-lookup"><span data-stu-id="271a3-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
-   <span data-ttu-id="271a3-105">Excepciones no controladas (el código nativo y administrado).</span><span class="sxs-lookup"><span data-stu-id="271a3-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
-   <span data-ttu-id="271a3-106">Método <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o función [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) (familia Windows 7).</span><span class="sxs-lookup"><span data-stu-id="271a3-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
-   <span data-ttu-id="271a3-107">Errores irrecuperables de runtime.</span><span class="sxs-lookup"><span data-stu-id="271a3-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="271a3-108">La depuración de adjuntos JIT también se desencadena mediante llamadas a los métodos y las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="271a3-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
-   <span data-ttu-id="271a3-109">Método <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="271a3-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="271a3-110">Método <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="271a3-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="271a3-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) (función) (Win32).</span><span class="sxs-lookup"><span data-stu-id="271a3-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="271a3-112">Antes de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework proporcionaba claves del Registro independientes para controlar el comportamiento de los depuradores administrados y nativos.</span><span class="sxs-lookup"><span data-stu-id="271a3-112">Before the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="271a3-113">A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], el control se consolida en una única clave del Registro: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="271a3-113">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="271a3-114">Los valores que puede establecer para esa clave determinan si se invoca un depurador y, de ser así, si se invoca con un cuadro de diálogo que necesita interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="271a3-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="271a3-115">Para obtener información acerca de cómo establecer esta clave del registro, consulte [Configurar depuración automática](https://go.microsoft.com/fwlink/?LinkId=181767).</span><span class="sxs-lookup"><span data-stu-id="271a3-115">For information about setting this registry key, see [Configuring Automatic Debugging](https://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="271a3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="271a3-116">See Also</span></span>  
 [<span data-ttu-id="271a3-117">Depurar, trazar y generar perfiles</span><span class="sxs-lookup"><span data-stu-id="271a3-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)  
 [<span data-ttu-id="271a3-118">Facilitar la depuración de una imagen</span><span class="sxs-lookup"><span data-stu-id="271a3-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 [<span data-ttu-id="271a3-119">Habilitar la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="271a3-119">Enabling Profiling</span></span>](https://msdn.microsoft.com/library/3b669676-f0e0-4ebf-8674-68986dd2020d)
