---
title: Características obsoletas en .NET 5+
description: Obtenga información sobre las API marcadas como obsoletas en .NET 5.0 y versiones posteriores que generan advertencias del compilador SYSLIB.
ms.date: 10/20/2020
ms.openlocfilehash: 336958c93e3db8f66cfbec89476a666e5e103b70
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593310"
---
# <a name="obsolete-features-in-net-5"></a>Características obsoletas en .NET 5

A partir de .NET 5.0, algunas API recién marcadas como obsoletas usan dos nuevas propiedades en <xref:System.ObsoleteAttribute>.

- La propiedad <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> indica al compilador que genere advertencias de compilación mediante un identificador de diagnóstico personalizado. El identificador personalizado permite que las advertencias de obsolescencia se supriman específicamente y de forma independiente entre sí. En el caso de las obsolescencias de .NET 5+, el formato del identificador de diagnóstico personalizado es `SYSLIBxxxx`.

- La propiedad <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> indica al compilador que incluya un vínculo de dirección URL para obtener más información sobre la obsolescencia.

Si se producen advertencias o errores de compilación debido al uso de una API obsoleta, siga las instrucciones específicas proporcionadas para el identificador de diagnóstico en la sección [Referencia](#reference). Las advertencias o los errores de estas obsolescencias *no* pueden suprimirse mediante el [identificador de diagnóstico estándar (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) para tipos o miembros obsoletos; use los valores del identificador de diagnóstico `SYSLIBxxxx` personalizado en su lugar. Para obtener más información, vea [Suprimir advertencias](#suppress-warnings).

## <a name="reference"></a>Referencia

En la tabla siguiente se proporciona un índice de las obsolescencias `SYSLIBxxxx` en .NET 5+.

| Id. de diagnóstico | Descripción |
| - | - |
| [SYSLIB0001](syslib-warnings/syslib0001.md) | La codificación UTF-7 no es segura y no debe usarse. Considere la posibilidad de usar UTF-8 en su lugar. |
| [SYSLIB0002](syslib-warnings/syslib0002.md) | El entorno de ejecución no respeta <xref:System.Security.Permissions.PrincipalPermissionAttribute> y no debe usarse. |
| [SYSLIB0003](syslib-warnings/syslib0003.md) | La seguridad de acceso del código (CAS) no es compatible o el entorno de ejecución no la respeta. |
| [SYSLIB0004](syslib-warnings/syslib0004.md) | No se admite la característica de regiones de ejecución restringidas (CER). |
| [SYSLIB0005](syslib-warnings/syslib0005.md) | No se admite la caché global de ensamblados (GAC). |
| [SYSLIB0006](syslib-warnings/syslib0006.md) | <xref:System.Threading.Thread.Abort?displayProperty=nameWithType> no se admite y produce una <xref:System.PlatformNotSupportedException>. |
| [SYSLIB0007](syslib-warnings/syslib0007.md) | La implementación predeterminada de este algoritmo de criptografía no es compatible. |
| [SYSLIB0008](syslib-warnings/syslib0008.md) | La API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> no se admite y produce una <xref:System.PlatformNotSupportedException>. |
| [SYSLIB0009](syslib-warnings/syslib0009.md) | Los métodos <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> y <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> no se admiten y producen una <xref:System.PlatformNotSupportedException>. |
| [SYSLIB0010](syslib-warnings/syslib0010.md) | No se admiten algunas API de comunicación remota y producen una <xref:System.PlatformNotSupportedException>. |
| [SYSLIB0011](syslib-warnings/syslib0011.md) | La serialización <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> está obsoleta y no debe usarse. |
| [SYSLIB0012](syslib-warnings/syslib0012.md) | <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> y <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> solo se incluyen para la compatibilidad con .NET Framework. Utilice <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> en su lugar. |

## <a name="suppress-warnings"></a>Suprimir advertencias

Si debe usar las API obsoletas y el diagnóstico `SYSLIBxxxx` no se ve como un error, puede suprimir la advertencia en el código o en el archivo del proyecto.

Mediante código:

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
   <!-- To suppress multiple warnings, you can use multiple NoWarn elements -->
   <NoWarn>$(NoWarn);SYSLIB0002</NoWarn>
   <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
   <!-- Alternatively, you can suppress multiple warnings by using a semicolon-delimited list -->
   <NoWarn>$(NoWarn);SYSLIB0001;SYSLIB0002;SYSLIB0003</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> La supresión de advertencias de esta manera solo deshabilita las advertencias de obsolescencia que especifique. No deshabilita ninguna otra advertencia, incluidas las de obsolescencia con otros identificadores de diagnóstico.
