---
ms.openlocfilehash: 85488de561a2298f2ff4009ec78b9a6e294053f3
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598178"
---
### <a name="threadabort-is-obsolete"></a>Thread.Abort obsoleto

Las API de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> están obsoletas. Los proyectos que tienen como destino .NET 5.0 o una versión posterior detectarán advertencias en tiempo de compilación si se llama a estos métodos. Si suprime las advertencias, se producirá una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.

#### <a name="change-description"></a>Descripción del cambio

Anteriormente, las llamadas a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> no producían advertencias en tiempo de compilación, pero el método sí producía una excepción <xref:System.PlatformNotSupportedException> en tiempo de ejecución.

A partir de .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> está marcado como obsoleto como advertencia. La llamada a este método produce la advertencia del compilador `SYSLIB0006`. La implementación del método no cambia y continúa generando una excepción <xref:System.PlatformNotSupportedException>.

#### <a name="reason-for-change"></a>Motivo del cambio

Dado que <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> siempre produce una excepción <xref:System.PlatformNotSupportedException> en todas las implementaciones de .NET, excepto en .NET Framework, se ha agregado <xref:System.ObsoleteAttribute> al método para avisar en los lugares donde se llama a este.

#### <a name="version-introduced"></a>Versión introducida

5.0 RC 1

#### <a name="recommended-action"></a>Acción recomendada

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

  Para más información, consulte [Cancelación de subprocesos administrados](../../../../docs/standard/threading/cancellation-in-managed-threads.md).

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

#### <a name="category"></a>Categoría

- Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
