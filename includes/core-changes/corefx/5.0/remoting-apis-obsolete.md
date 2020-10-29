---
ms.openlocfilehash: 35041a035041fd4ad5402e1bc0dd137a74d4f949
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434926"
---
### <a name="remoting-apis-are-obsolete"></a>Las API de comunicación remota están obsoletas

Algunas API relacionadas con la comunicación remota se han marcado como obsoletas y generan una advertencia `SYSLIB0010` en tiempo de compilación. Estas API podrían eliminarse en una próxima versión de .NET.

#### <a name="change-description"></a>Descripción del cambio

Las siguientes API de comunicación remota se han marcado como obsoletas.

| API | Marcada como obsoleta en... |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | 5.0 RC1 |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | 5.0 RC1 |

En .NET Framework 2.x-4.x, los métodos <xref:System.MarshalByRefObject.GetLifetimeService> y <xref:System.MarshalByRefObject.InitializeLifetimeService> controlan la duración de las instancias implicadas con .NET Remoting. En .NET Core 2.x-3.x, estos métodos siempre producen una <xref:System.PlatformNotSupportedException> en tiempo de ejecución.

En .NET 5.0 y versiones posteriores, los métodos <xref:System.MarshalByRefObject.GetLifetimeService> y <xref:System.MarshalByRefObject.InitializeLifetimeService> se han marcado como obsoletos como advertencia, pero siguen produciendo una <xref:System.PlatformNotSupportedException> en tiempo de ejecución.

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

Se trata de un cambio solo en tiempo de compilación. No hay ningún cambio en tiempo de ejecución con respecto a versiones anteriores de .NET Core.

#### <a name="reason-for-change"></a>Motivo del cambio

[.NET Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) es una tecnología heredada. Permite crear instancias de un objeto en otro proceso (potencialmente incluso en otra máquina) e interactuar con ese objeto como si fuera una instancia de objeto .NET normal en proceso. La infraestructura de .NET Remoting solo existe en .NET Framework 2.x-4.x. .NET Core y .NET 5.0 y versiones posteriores no tienen compatibilidad con .NET Remoting, y las API de comunicación remota o no existen o siempre producen excepciones en estos entornos de ejecución.

Para ayudar a los desarrolladores a apartarse de estas API, se están marcando como obsoletas API seleccionadas relacionadas con la comunicación remota. Estas API podrían eliminarse por completo en una próxima versión de .NET.

#### <a name="version-introduced"></a>Versión introducida

.NET 5.0

#### <a name="recommended-action"></a>Acción recomendada

- Considere la posibilidad de usar servicios REST basados en WCF o HTTP para comunicarse con objetos de otras aplicaciones o entre máquinas. Para obtener más información, vea [Tecnologías de .NET Framework no disponibles en .NET Core](../../../../docs/core/porting/net-framework-tech-unavailable.md).

- Si tiene que seguir usando las API obsoletas, puede suprimir la advertencia `SYSLIB0010` en el código.

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  También puede suprimir la advertencia en el archivo del proyecto, lo que la deshabilita en todos los archivos de código fuente del proyecto.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  La supresión de `SYSLIB0010` solo deshabilita las advertencias de obsolescencia de la API de comunicación remota. No se deshabilita ninguna otra advertencia. Además, no cambia el comportamiento codificado en tiempo de ejecución de producir siempre una <xref:System.PlatformNotSupportedException>.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
