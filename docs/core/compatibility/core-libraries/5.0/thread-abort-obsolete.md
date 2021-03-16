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
# <a name="threadabort-is-obsolete"></a>Thread.Abort obsoleto

Las API de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> están obsoletas. Los proyectos que tienen como destino .NET 5 o una versión posterior detectan advertencias en tiempo de compilación `SYSLIB0006` si se llama a estos métodos.

## <a name="change-description"></a>Descripción del cambio

Anteriormente, las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> no producían advertencias en tiempo de compilación, pero el método sí producía una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.

A partir de .NET 5, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> está marcado como obsoleto como advertencia. La llamada a este método produce la advertencia del compilador `SYSLIB0006`. La implementación del método no cambia y continúa generando una excepción <xref:System.PlatformNotSupportedException>.

## <a name="reason-for-change"></a>Motivo del cambio

Dado que <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> siempre produce una excepción <xref:System.PlatformNotSupportedException> en todas las implementaciones de .NET, excepto en .NET Framework, se ha agregado <xref:System.ObsoleteAttribute> al método para avisar en los lugares donde se llama a este.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- Use un token ce cancelación (<xref:System.Threading.CancellationToken>) para anular el procesamiento de una unidad de trabajo en lugar de llamar a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. En el siguiente ejemplo se muestra el uso de <xref:System.Threading.CancellationToken>.

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

  Para más información, consulte [Cancelación de subprocesos administrados](../../../../standard/threading/cancellation-in-managed-threads.md).

- Para suprimir la advertencia en tiempo de compilación, suprima el código de advertencia `SYSLIB0006`. El código de advertencia es específico de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> y, al suprimirlo, no se suprimen otras advertencias de obsolescencia en el código. Pero se recomienda que elimine las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> en lugar de suprimir la advertencia.

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  También puede suprimir la advertencia en el archivo del proyecto.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

## <a name="affected-apis"></a>API afectadas

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
