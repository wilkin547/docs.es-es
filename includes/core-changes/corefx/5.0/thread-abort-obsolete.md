---
ms.openlocfilehash: 85488de561a2298f2ff4009ec78b9a6e294053f3
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598178"
---
### <a name="threadabort-is-obsolete"></a><span data-ttu-id="18380-101">Thread.Abort obsoleto</span><span class="sxs-lookup"><span data-stu-id="18380-101">Thread.Abort is obsolete</span></span>

<span data-ttu-id="18380-102">Las API de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="18380-102">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="18380-103">Los proyectos que tienen como destino .NET 5.0 o una versión posterior detectarán advertencias en tiempo de compilación si se llama a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="18380-103">Projects that target .NET 5.0 or a later version will encounter compile-time warnings if these methods are called.</span></span> <span data-ttu-id="18380-104">Si suprime las advertencias, se producirá una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18380-104">If you suppress the warnings, a <xref:System.PlatformNotSupportedException> will be thrown at run time.</span></span>

#### <a name="change-description"></a><span data-ttu-id="18380-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="18380-105">Change description</span></span>

<span data-ttu-id="18380-106">Anteriormente, las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> no producían advertencias en tiempo de compilación, pero el método sí producía una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18380-106">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="18380-107">A partir de .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> está marcado como obsoleto como advertencia.</span><span class="sxs-lookup"><span data-stu-id="18380-107">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="18380-108">La llamada a este método produce la advertencia del compilador `SYSLIB0006`.</span><span class="sxs-lookup"><span data-stu-id="18380-108">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="18380-109">La implementación del método no cambia y continúa generando una excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="18380-109">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="18380-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="18380-110">Reason for change</span></span>

<span data-ttu-id="18380-111">Dado que <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> siempre produce una excepción <xref:System.PlatformNotSupportedException> en todas las implementaciones de .NET, excepto en .NET Framework, se ha agregado <xref:System.ObsoleteAttribute> al método para avisar en los lugares donde se llama a este.</span><span class="sxs-lookup"><span data-stu-id="18380-111">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="18380-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="18380-112">Version introduced</span></span>

<span data-ttu-id="18380-113">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="18380-113">5.0 RC 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="18380-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="18380-114">Recommended action</span></span>

- <span data-ttu-id="18380-115">Use un token ce cancelación (<xref:System.Threading.CancellationToken>) para anular el procesamiento de una unidad de trabajo en lugar de llamar a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="18380-115">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="18380-116">En el siguiente ejemplo se muestra el uso de <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="18380-116">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

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

  <span data-ttu-id="18380-117">Para más información, consulte [Cancelación de subprocesos administrados](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="18380-117">For more information, see [Cancellation in managed threads](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="18380-118">Para suprimir la advertencia en tiempo de compilación, suprima el código de advertencia `SYSLIB0006`.</span><span class="sxs-lookup"><span data-stu-id="18380-118">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="18380-119">El código de advertencia es específico de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> y, al suprimirlo, no se suprimen otras advertencias de obsolescencia en el código.</span><span class="sxs-lookup"><span data-stu-id="18380-119">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="18380-120">Pero se recomienda que elimine las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> en lugar de suprimir la advertencia.</span><span class="sxs-lookup"><span data-stu-id="18380-120">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="18380-121">También puede suprimir la advertencia en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="18380-121">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="18380-122">Categoría</span><span class="sxs-lookup"><span data-stu-id="18380-122">Category</span></span>

- <span data-ttu-id="18380-123">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="18380-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="18380-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="18380-124">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
