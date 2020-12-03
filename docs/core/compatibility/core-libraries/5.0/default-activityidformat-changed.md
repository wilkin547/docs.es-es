---
title: 'Cambio importante: El valor predeterminado de ActivityIdFormat es W3C'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde el valor ActivityIdFormat predeterminado ahora es W3C.
ms.date: 11/01/2020
ms.openlocfilehash: 77ee705ac18065c84ddeab3127e01b6a40c3b84d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760204"
---
# <a name="default-activityidformat-is-w3c"></a>El valor predeterminado de ActivityIdFormat es W3C

Ahora el formato de identificador predeterminado de la actividad (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) es <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.

## <a name="change-description"></a>Descripción del cambio

El formato de id. de actividad del W3C se presentó en .NET Core 3.0 como alternativa al formato de identificador jerárquico. Pero para conservar la compatibilidad, el formato del W3C no se ha convertido en el predeterminado hasta .NET 5.0. El valor predeterminado se ha cambiado en .NET 5.0 porque el formato del W3C se ha [ratificado](https://www.w3.org/TR/trace-context/) y consolidado en las implementaciones de varios lenguajes.

Si la aplicación tiene como destino una plataforma distinta a .NET 5.0 o posterior, experimentará el comportamiento anterior, donde <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> es el formato predeterminado. Este formato predeterminado. se aplica a las plataformas net45+, netstandard1.1+ y netcoreapp (1.x, 2.x y 3.x). En .NET 5.0 y versiones posteriores, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> se establece en <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Si la aplicación es independiente del identificador que se usa para el seguimiento distribuido, no es necesario realizar ninguna acción. Las bibliotecas como ASP.NET Core y <xref:System.Net.Http.HttpClient> pueden consumir o propagar las dos versiones de <xref:System.Diagnostics.ActivityIdFormat>.

Si requiere interoperabilidad con sistemas existentes, o los sistemas actuales dependen del formato del identificador, puede conservar el comportamiento anterior si establece <xref:System.Diagnostics.Activity.DefaultIdFormat> en <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>. Como alternativa, puede establecer un modificador AppContext de una de estas tres maneras:

- En el archivo del proyecto.

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- En el archivo *runtimeconfig.json*.

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- A través de una variable de entorno.

  Establezca `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` en `true` o 1.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
