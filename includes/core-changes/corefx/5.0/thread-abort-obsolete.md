---
ms.openlocfilehash: ee67b32b093ebd42f8ac685b34b12f2f6833be86
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332940"
---
### <a name="threadabort-is-obsolete"></a><span data-ttu-id="e4654-101">Thread.Abort obsoleto</span><span class="sxs-lookup"><span data-stu-id="e4654-101">Thread.Abort is obsolete</span></span>

<span data-ttu-id="e4654-102">Las API de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="e4654-102">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="e4654-103">Los proyectos que tienen como destino .NET 5.0 o una versión posterior detectan advertencias en tiempo de compilación `SYSLIB0006` si se llama a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="e4654-103">Projects that target .NET 5.0 or a later version will encounter compile-time warning `SYSLIB0006` if these methods are called.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e4654-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="e4654-104">Change description</span></span>

<span data-ttu-id="e4654-105">Anteriormente, las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> no producían advertencias en tiempo de compilación, pero el método sí producía una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e4654-105">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="e4654-106">A partir de .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> está marcado como obsoleto como advertencia.</span><span class="sxs-lookup"><span data-stu-id="e4654-106">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="e4654-107">La llamada a este método produce la advertencia del compilador `SYSLIB0006`.</span><span class="sxs-lookup"><span data-stu-id="e4654-107">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="e4654-108">La implementación del método no cambia y continúa generando una excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="e4654-108">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e4654-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="e4654-109">Reason for change</span></span>

<span data-ttu-id="e4654-110">Dado que <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> siempre produce una excepción <xref:System.PlatformNotSupportedException> en todas las implementaciones de .NET, excepto en .NET Framework, se ha agregado <xref:System.ObsoleteAttribute> al método para avisar en los lugares donde se llama a este.</span><span class="sxs-lookup"><span data-stu-id="e4654-110">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e4654-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e4654-111">Version introduced</span></span>

<span data-ttu-id="e4654-112">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="e4654-112">5.0 RC 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e4654-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e4654-113">Recommended action</span></span>

- <span data-ttu-id="e4654-114">Use un token ce cancelación (<xref:System.Threading.CancellationToken>) para anular el procesamiento de una unidad de trabajo en lugar de llamar a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4654-114">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e4654-115">En el siguiente ejemplo se muestra el uso de <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="e4654-115">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

  ```csharp
  void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
  {
      if (QueryIsMoreWorkPending())
      {
          // If the CancellationToken is marked as "needs to cancel",
          // this will throw the appropriate exception.
          cancellationToken.ThrowIfCancellationRequested();

          WorkItem work = DequeueWorkItem();
          ProcessWorkItem(work);
      }
  }
  ```

  <span data-ttu-id="e4654-116">Para más información, consulte [Cancelación de subprocesos administrados](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="e4654-116">For more information, see [Cancellation in managed threads](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="e4654-117">Para suprimir la advertencia en tiempo de compilación, suprima el código de advertencia `SYSLIB0006`.</span><span class="sxs-lookup"><span data-stu-id="e4654-117">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="e4654-118">El código de advertencia es específico de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> y, al suprimirlo, no se suprimen otras advertencias de obsolescencia en el código.</span><span class="sxs-lookup"><span data-stu-id="e4654-118">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="e4654-119">Pero se recomienda que elimine las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> en lugar de suprimir la advertencia.</span><span class="sxs-lookup"><span data-stu-id="e4654-119">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="e4654-120">También puede suprimir la advertencia en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e4654-120">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="e4654-121">Categoría</span><span class="sxs-lookup"><span data-stu-id="e4654-121">Category</span></span>

- <span data-ttu-id="e4654-122">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="e4654-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e4654-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e4654-123">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
