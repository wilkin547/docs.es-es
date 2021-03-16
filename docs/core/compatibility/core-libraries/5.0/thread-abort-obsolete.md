---
title: 'Cambio importante: Thread.Abort obsoleto'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde las API Thread.Abort están obsoletas.
ms.date: 11/01/2020
ms.openlocfilehash: 29c688250593801bab9b32b9e787911e561ec000
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257068"
---
# <a name="threadabort-is-obsolete"></a><span data-ttu-id="14850-103">Thread.Abort obsoleto</span><span class="sxs-lookup"><span data-stu-id="14850-103">Thread.Abort is obsolete</span></span>

<span data-ttu-id="14850-104">Las API de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="14850-104">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="14850-105">Los proyectos que tienen como destino .NET 5 o una versión posterior detectan advertencias en tiempo de compilación `SYSLIB0006` si se llama a estos métodos.</span><span class="sxs-lookup"><span data-stu-id="14850-105">Projects that target .NET 5 or a later version will encounter compile-time warning `SYSLIB0006` if these methods are called.</span></span>

## <a name="change-description"></a><span data-ttu-id="14850-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="14850-106">Change description</span></span>

<span data-ttu-id="14850-107">Anteriormente, las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> no producían advertencias en tiempo de compilación, pero el método sí producía una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="14850-107">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="14850-108">A partir de .NET 5, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> está marcado como obsoleto como advertencia.</span><span class="sxs-lookup"><span data-stu-id="14850-108">Starting in .NET 5, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="14850-109">La llamada a este método produce la advertencia del compilador `SYSLIB0006`.</span><span class="sxs-lookup"><span data-stu-id="14850-109">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="14850-110">La implementación del método no cambia y continúa generando una excepción <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="14850-110">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="14850-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="14850-111">Reason for change</span></span>

<span data-ttu-id="14850-112">Dado que <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> siempre produce una excepción <xref:System.PlatformNotSupportedException> en todas las implementaciones de .NET, excepto en .NET Framework, se ha agregado <xref:System.ObsoleteAttribute> al método para avisar en los lugares donde se llama a este.</span><span class="sxs-lookup"><span data-stu-id="14850-112">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="14850-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="14850-113">Version introduced</span></span>

<span data-ttu-id="14850-114">5.0</span><span class="sxs-lookup"><span data-stu-id="14850-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="14850-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="14850-115">Recommended action</span></span>

- <span data-ttu-id="14850-116">Use un token ce cancelación (<xref:System.Threading.CancellationToken>) para anular el procesamiento de una unidad de trabajo en lugar de llamar a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="14850-116">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="14850-117">En el siguiente ejemplo se muestra el uso de <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="14850-117">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

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

  <span data-ttu-id="14850-118">Para más información, consulte [Cancelación de subprocesos administrados](../../../../standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="14850-118">For more information, see [Cancellation in managed threads](../../../../standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="14850-119">Para suprimir la advertencia en tiempo de compilación, suprima el código de advertencia `SYSLIB0006`.</span><span class="sxs-lookup"><span data-stu-id="14850-119">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="14850-120">El código de advertencia es específico de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> y, al suprimirlo, no se suprimen otras advertencias de obsolescencia en el código.</span><span class="sxs-lookup"><span data-stu-id="14850-120">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="14850-121">Pero se recomienda que elimine las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> en lugar de suprimir la advertencia.</span><span class="sxs-lookup"><span data-stu-id="14850-121">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="14850-122">También puede suprimir la advertencia en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="14850-122">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

## <a name="affected-apis"></a><span data-ttu-id="14850-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="14850-123">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
