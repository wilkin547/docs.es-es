---
title: 'Cambio importante: Las API de caché global de ensamblados están obsoletas'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde las API que controlan la GAC generan un error o no realizan ninguna operación.
ms.date: 11/01/2020
ms.openlocfilehash: 2f74fccc68b7a925d909938d77578df8ebe8d60d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760202"
---
# <a name="global-assembly-cache-apis-are-obsolete"></a>Las API de caché global de ensamblados están obsoletas

.NET Core y .NET 5.0 y versiones posteriores eliminan el concepto de caché global de ensamblados (GAC) presente en .NET Framework. Por lo tanto, todas las API de .NET Core y .NET 5+ que se ocupan de GAC producen errores o no hacen nada.

Para ayudar a los desarrolladores a apartarse de estas API, algunas relacionadas con GAC se han marcado como obsoletas y generan una advertencia `SYSLIB0005` en tiempo de compilación. Estas API podrían eliminarse en una próxima versión de .NET.

## <a name="change-description"></a>Descripción del cambio

Las siguientes API se han marcado como obsoletas.

| API | Marcada como obsoleta en... |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | 5.0 RC1 |

En .NET Framework 2.x-4.x, la propiedad <xref:System.Reflection.Assembly.GlobalAssemblyCache> devuelve `true` si el ensamblado consultado se ha cargado desde GAC y `false` si se ha cargado desde otra ubicación en el disco. En .NET Core 2.x-3.x, <xref:System.Reflection.Assembly.GlobalAssemblyCache> siempre devuelve `false`, lo que refleja que GAC no existe en .NET Core.

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

En .NET 5.0 y versiones posteriores, la propiedad <xref:System.Reflection.Assembly.GlobalAssemblyCache> sigue devolviendo `false`. Pero el captador de propiedad también se ha marcado como obsoleto para indicar a los autores de llamadas que deben dejar de acceder a la propiedad. Las bibliotecas y aplicaciones no deben usar la API <xref:System.Reflection.Assembly.GlobalAssemblyCache> para realizar determinaciones sobre el comportamiento en tiempo de ejecución, ya que siempre devuelve `false` en .NET Core y .NET 5.0 y versiones posteriores.

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

Se trata de un cambio solo en tiempo de compilación. No hay ningún cambio en tiempo de ejecución con respecto a versiones anteriores de .NET Core.

## <a name="reason-for-change"></a>Motivo del cambio

La caché global de ensamblados (GAC) no existe como concepto en .NET Core y .NET 5.0 y versiones posteriores.

## <a name="version-introduced"></a>Versión introducida

.NET 5.0

## <a name="recommended-action"></a>Acción recomendada

- Si la aplicación consulta a la propiedad <xref:System.Reflection.Assembly.GlobalAssemblyCache>, considere la posibilidad de eliminar la llamada. Si usa el valor <xref:System.Reflection.Assembly.GlobalAssemblyCache> para elegir entre un flujo de "ensamblado en GAC" frente a un flujo de "ensamblado no en GAC" en tiempo de ejecución, vuelva a considerar si el flujo sigue teniendo sentido para una aplicación .NET Core o .NET 5.0+.

- Si tiene que seguir usando las API obsoletas, puede suprimir la advertencia `SYSLIB0005` en el código.

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  También puede suprimir la advertencia en el archivo del proyecto, lo que la deshabilita en todos los archivos de código fuente del proyecto.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  La supresión de `SYSLIB0005` solo deshabilita la advertencia de obsolescencia <xref:System.Reflection.Assembly.GlobalAssemblyCache>. No se deshabilita ninguna otra advertencia.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
