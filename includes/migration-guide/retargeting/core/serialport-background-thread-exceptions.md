---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614749"
---
### <a name="serialport-background-thread-exceptions"></a><span data-ttu-id="eab9e-101">Excepciones de subprocesos en segundo plano SerialPort</span><span class="sxs-lookup"><span data-stu-id="eab9e-101">SerialPort background thread exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="eab9e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="eab9e-102">Details</span></span>

<span data-ttu-id="eab9e-103">Los subprocesos en segundo plano creados con secuencias <xref:System.IO.Ports.SerialPort> ya no finalizan el proceso cuando se inician excepciones del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="eab9e-103">Background threads created with <xref:System.IO.Ports.SerialPort> streams no longer terminate the process when OS exceptions are thrown.</span></span> <br/><span data-ttu-id="eab9e-104">En las aplicaciones destinadas a .NET Framework 4.7 y versiones anteriores, un proceso se termina cuando se inicia una excepción del sistema operativo en un subproceso en segundo plano creado con una secuencia <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="eab9e-104">In applications that target the .NET Framework 4.7 and earlier versions, a process is terminated when an operating system exception is thrown on a background thread created with a <xref:System.IO.Ports.SerialPort> stream.</span></span> <br/><span data-ttu-id="eab9e-105">En las aplicaciones destinadas a .NET Framework 4.7.1 o una versión posterior, los subprocesos en segundo plano esperan eventos del sistema operativo relacionados con el puerto serie activo y pueden dejar de funcionar en algunos casos, como la eliminación repentina del puerto serie.</span><span class="sxs-lookup"><span data-stu-id="eab9e-105">In applications that target the .NET Framework 4.7.1 or a later version, background threads wait for OS events related to the active serial port and could crash in some cases, such as sudden removal of the serial port.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eab9e-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="eab9e-106">Suggestion</span></span>

<span data-ttu-id="eab9e-107">Para las aplicaciones que tienen como destino .NET Framework 4.7.1, se puede rechazar el control de excepciones si no es adecuado si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:</span><span class="sxs-lookup"><span data-stu-id="eab9e-107">For apps that target the .NET Framework 4.7.1, you can opt out of the exception handling if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

<span data-ttu-id="eab9e-108">Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.7.1 o versiones posteriores, se puede incluir el control de excepciones si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:</span><span class="sxs-lookup"><span data-stu-id="eab9e-108">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.1 or later, you can opt in to the exception handling by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| <span data-ttu-id="eab9e-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="eab9e-109">Name</span></span>    | <span data-ttu-id="eab9e-110">Valor</span><span class="sxs-lookup"><span data-stu-id="eab9e-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eab9e-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="eab9e-111">Scope</span></span>   | <span data-ttu-id="eab9e-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="eab9e-112">Minor</span></span>       |
| <span data-ttu-id="eab9e-113">Versión</span><span class="sxs-lookup"><span data-stu-id="eab9e-113">Version</span></span> | <span data-ttu-id="eab9e-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="eab9e-114">4.7.1</span></span>       |
| <span data-ttu-id="eab9e-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="eab9e-115">Type</span></span>    | <span data-ttu-id="eab9e-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="eab9e-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="eab9e-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="eab9e-117">Affected APIs</span></span>

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
