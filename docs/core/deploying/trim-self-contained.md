---
title: Recorte de aplicaciones autocontenidas
description: Obtenga información sobre cómo recortar aplicaciones autocontenidas para reducir su tamaño. .NET Core agrupa el tiempo de ejecución con una aplicación que se publica autocontenida y que, por lo general, incluye más tiempo de ejecución del que es necesario.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bf38ffe4d47986ae78c6cf2b2e5ecb292411ba6c
ms.sourcegitcommit: 6d09ae36acba0b0e2ba47999f8f1a725795462a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2020
ms.locfileid: "92925290"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Recorte de implementaciones autocontenidas y ejecutables

El [modelo de implementación dependiente del marco](index.md#publish-framework-dependent) ha sido el modelo de implementación más eficaz desde el inicio de .NET. En este escenario, el desarrollador de la aplicación agrupa solo la aplicación y los ensamblados de terceros con la expectativa de que las bibliotecas del entorno de ejecución y el marco de .NET estén disponibles en el equipo cliente. Este modelo de implementación sigue siendo el dominante en .NET Core, pero hay algunos escenarios en los que el modelo dependiente del marco no es óptimo. La alternativa es publicar una [aplicación independiente](index.md#publish-self-contained), donde el entorno de ejecución y el marco de .NET Core están agrupados con la aplicación y ensamblados de terceros.

El modelo de implementación trim independiente es una versión especializada del modelo de implementación independiente que está optimizado para reducir el tamaño de la implementación. Minimizar el tamaño de la implementación es un requisito fundamental para algunos escenarios del lado cliente, como las aplicaciones Blazor. En función de la complejidad de la aplicación, solo se hace referencia a un subconjunto de ensamblados de marco, y se requiere un subconjunto del código en cada ensamblado para ejecutar la aplicación. Las partes sin usar de las bibliotecas no son necesarias y se pueden recortar de la aplicación empaquetada.

No obstante, existe el riesgo de que el análisis del tiempo de compilación de la aplicación pueda causar errores en tiempo de ejecución, debido a que no puede analizar de forma confiable diversos patrones de código problemáticos (centrados en gran medida en el uso de la reflexión). Dado que no se puede garantizar la confiabilidad, este modelo de implementación se ofrece como una característica en versión preliminar.

El motor de análisis en tiempo de compilación proporciona advertencias al desarrollador de los patrones de código problemáticos para detectar qué otro código es necesario. El código se puede anotar con atributos para indicar al recortador qué más se debe incluir. Muchos patrones de reflexión se pueden reemplazar por la generación de código en tiempo de compilación mediante [generadores de código fuente](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).

El modo de recorte de las aplicaciones se configura con `TrimMode`. El valor predeterminado es `copyused` y agrupa los ensamblados a los que se hace referencia con la aplicación. El valor `link` se usa con las aplicaciones WebAssembly de Blazor y recorta el código no usado dentro de los ensamblados. Las advertencias de análisis de recorte proporcionan información sobre patrones de código en los que no es posible realizar análisis de dependencias completas. Estas advertencias se suprimen de forma predeterminada y se pueden activar estableciendo la marca `SuppressTrimAnalysisWarnings` en `false`. Para obtener más información acerca de las opciones de recorte disponibles, vea [Opciones de recorte](trimming-options.md).

> [!NOTE]
> El recorte es una característica experimental en .NET Core 3.1 y .NET 5.0. _Solo_ está disponible para las aplicaciones que se publican como independientes.

## <a name="prevent-assemblies-from-being-trimmed"></a>Impedir que los ensamblados se recorten

Hay escenarios en los que la función de recorte no podrá detectar referencias. Por ejemplo, cuando se usa la reflexión en un ensamblado en tiempo de ejecución, ya sea por parte de la aplicación o por una biblioteca a la que haga referencia la aplicación, no se hace referencia directamente al ensamblado. El recorte desconoce estas referencias indirectas y excluirá la biblioteca de la carpeta publicada.

Cuando el código hace referencia indirectamente a un ensamblado mediante la reflexión, puede evitar que el ensamblado se recorte con la configuración `<TrimmerRootAssembly>`. En el ejemplo siguiente se muestra cómo evitar que un ensamblado llamado `System.Security` se recorte:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="support-for-ssl-certificates"></a>Compatibilidad con certificados SSL

Si la aplicación carga certificados SSL, como en el caso de una aplicación de ASP.NET Core, querrá asegurarse de evitar el recorte de los ensamblados que facilitan la carga de los certificados SSL.

Se puede actualizar el archivo del proyecto para incluir lo siguiente en ASP.NET Core 3.1:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>...</PropertyGroup>
  <!--Include the following for .aspnetcore 3.1-->
  <ItemGroup>
    <TrimmerRootAssembly Include="System.Net" />
    <TrimmerRootAssembly Include="System.Net.Security" />
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
  ...
</Project>
```

Si se usa .NET 5.0, se puede actualizar el archivo del proyecto para incluir lo siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
 <PropertyGroup>...</PropertyGroup>
 <!--Include the following for .net 5.0-->
 <ItemGroup>
    <TrimmerRootAssembly Include="System.Net.Security" />
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
  ...
</Project>
```

## <a name="trim-your-app---cli"></a>Recorte de la aplicación: CLI

Recorte la aplicación mediante el comando [dotnet publish](../tools/dotnet-publish.md). Al publicar la aplicación, establezca las propiedades siguientes:

- Publicar como una aplicación independiente para un entorno de ejecución específico: `-r win-x64`
- Habilitar recorte: `/p:PublishTrimmed=true`

En este ejemplo se publica una aplicación para Windows como independiente y se recorta la salida.

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

En este ejemplo se publica una aplicación en el modo de recorte agresivo en el que el código no usado dentro de los ensamblados se desactivará y se habilitarán las advertencias de recorte.

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).

## <a name="trim-your-app---visual-studio"></a>Recorte de la aplicación: Visual Studio

Visual Studio crea perfiles de publicación reutilizables que controlan cómo se publica la aplicación.

01. En el panel **Explorador de soluciones** , haga clic con el botón derecho en el proyecto que quiera publicar. Seleccione **Publicar...** .

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Explorador de soluciones con un menú contextual en el que se resalta la opción Publicar.":::

    Si todavía no tiene un perfil de publicación, siga las instrucciones para crear uno y elija el tipo de destino **Carpeta**.

01. Elija **Editar**.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Perfil de publicación de Visual Studio con el botón Editar.":::

01. En el cuadro de diálogo **Configuración de perfil** , establezca las opciones siguientes:

    - Establezca **Modo de implementación** en **Independiente**.
    - Establezca **Tiempo de ejecución de destino** en la plataforma en la que quiera publicar.
    - Seleccione **Quitar los ensamblados no usados (en versión preliminar)** .

    Elija **Guardar** para guardar la configuración y volver al cuadro de diálogo **Publicar**.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Cuadro de diálogo Configuración de perfil con las opciones Modo de implementación, Tiempo de ejecución de destino y Quitar los ensamblados no usados resaltadas.":::

01. Elija **Publicar** para publicar la aplicación recortada.

Para obtener más información, vea [Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).

## <a name="trim-your-app---visual-studio-for-mac"></a>Recorte de la aplicación: Visual Studio para Mac

Visual Studio para Mac no proporciona opciones para recortar la aplicación durante la publicación. Tendrá que publicar de forma manual mediante las instrucciones de la sección [Recorte de la aplicación: CLI](#trim-your-app---cli). Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).

## <a name="see-also"></a>Vea también

- [Implementación de aplicaciones .NET Core](index.md).
- [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).
- [Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).
- [Comando dotnet publish](../tools/dotnet-publish.md).
