---
title: 'NETSDK1071: Un elemento PackageReference establecido en "{0}" ha especificado una versión de `{1}`.'
description: Procedimiento para resolver el problema de un elemento PackageReference de un metapaquete incluido con el marco con una versión.
author: Forgind
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1071
ms.openlocfilehash: 1381fc63941ec04efb31035d13913620a195c236
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713085"
---
# <a name="netsdk1071-explicitly-versioned-packagereference-to-a-metapackage-that-would-be-included-with-the-framework"></a>NETSDK1071: Elemento PackageReference con una versión explícita a un metapaquete que se incluiría con el marco.

**Este artículo se aplica a:** ✔️ SDK de .NET 5.0.100 y versiones posteriores

Si el SDK de .NET emite una advertencia NETSDK1071, sugiere que puede haber un conflicto de versiones en el futuro entre la versión de un metapaquete especificada en un elemento PackageReference y la versión de ese metapaquete a la que se hace referencia de forma implícita a través de una propiedad TargetFramework:

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

Como TargetFramework aporta de forma automática una versión del metapaquete, las versiones entrarán en conflicto en caso de que difieran.

Para resolver este problema:

1. Al seleccionar como destino .NET Core o .NET Standard, considere la posibilidad de evitar referencias explícitas a `Microsoft.NETCore.App` o `NETStandard.Library` en el archivo del proyecto.
2. Si necesita una versión concreta del entorno de ejecución cuando el destino es .NET Core, use la propiedad `<RuntimeFrameworkVersion>` en lugar de hacer referencia de forma directa al metapaquete. Por ejemplo, esto puede ocurrir si usa [implementaciones independientes](../../deploying/index.md#publish-self-contained) y necesita una versión específica del entorno de ejecución de LTS 1.0.0.
3. Si necesita una versión concreta de `NetStandard.Library` cuando el destino es .NET Standard, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecerla en la versión necesaria.
4. No agregue referencias a `Microsoft.NETCore.App` y `NETSTandard.Library` ni las actualice de forma explícita en proyectos de .NET Framework. NuGet instala de forma automática cualquier versión de `NETStandard.Library` que necesite al usar un paquete NuGet basado en .NET Standard.
5. No especifique una versión para `Microsoft.AspNetCore.App` o `Microsoft.AspNetCore.All` al usar .NET Core 2.1 y posteriores, ya que el SDK de .NET Core selecciona de forma automática la versión adecuada. (Nota: Esto solo funciona cuando el destino es .NET Core 2.1 si el proyecto también utiliza `Microsoft.NET.Sdk.Web`. Este problema se ha resuelto en el SDK de .NET Core 2.2).
6. Si quiere que desaparezca la advertencia, también puede deshabilitarla:

   ```xml
   <PackageReference Include="Microsoft.NetCore.App" Version="2.2.8" >
     <AllowExplicitVersion>true</AllowExplicitVersion>
   </PackageReference>
   ```
