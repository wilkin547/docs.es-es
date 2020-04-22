---
title: Recorte de aplicaciones autocontenidas
description: Obtenga información sobre cómo recortar aplicaciones autocontenidas para reducir su tamaño. .NET Core agrupa el tiempo de ejecución con una aplicación que se publica autocontenida y que, por lo general, incluye más tiempo de ejecución del que es necesario.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242932"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Recorte de implementaciones autocontenidas y ejecutables

Al publicar una aplicación autocontenida, el tiempo de ejecución de .NET Core se agrupa junto con la aplicación. Esta agrupación agrega una cantidad considerable de contenido a la aplicación empaquetada. En lo que respecta a la implementación de la aplicación, el tamaño suele ser un factor importante. Mantener lo más pequeño posible el tamaño de la aplicación del paquete suele ser un objetivo para los desarrolladores de aplicaciones.

En función de la complejidad de la aplicación, solo se necesita un subconjunto del tiempo de ejecución para ejecutarla. Estas partes sin usar del tiempo de ejecución no son necesarias y se pueden recortar de la aplicación empaquetada.

La característica recorte funciona examinando los archivos binarios de la aplicación para descubrir y compilar un gráfico de los ensamblados en tiempo de ejecución necesarios. Se excluyen los ensamblados en tiempo de ejecución restantes a los que no se hace referencia.

> [!NOTE]
> El recorte es una característica experimental en .NET Core 3.1 y _solo_ está disponible para las aplicaciones que se publican autocontenidas.

## <a name="prevent-assemblies-from-being-trimmed"></a>Impedir que los ensamblados se recorten

Hay escenarios en los que la función de recorte no podrá detectar referencias. Por ejemplo, cuando se usa la reflexión en un ensamblado en tiempo de ejecución, ya sea por parte de la aplicación o por una biblioteca a la que haga referencia la aplicación, no se hace referencia directamente al ensamblado. El recorte desconoce estas referencias indirectas y excluirá la biblioteca de la carpeta publicada.

Cuando el código hace referencia indirectamente a un ensamblado mediante la reflexión, puede evitar que el ensamblado se recorte con la configuración `<TrimmerRootAssembly>`. En el ejemplo siguiente se muestra cómo evitar que un ensamblado llamado `System.Security` se recorte:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a>Recorte de la aplicación: CLI

Recorte la aplicación mediante el comando [dotnet publish](../tools/dotnet-publish.md). Al publicar la aplicación, establezca las tres opciones siguientes:

- Publicación como independiente: `--self-contained true`
- Deshabilitar la publicación de un solo archivo: `-p:PublishSingleFile=false`
- Habilitar recorte: `p:PublishTrimmed=true`

En el ejemplo siguiente se publica una aplicación para Windows 10 como independiente y se recorta la salida.

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).

## <a name="trim-your-app---visual-studio"></a>Recorte de la aplicación: Visual Studio

Visual Studio crea perfiles de publicación reutilizables que controlan cómo se publica la aplicación.

01. En el panel **Explorador de soluciones**, haga clic con el botón derecho en el proyecto que quiera publicar. Seleccione **Publicar...** .

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Explorador de soluciones con un menú contextual en el que se resalta la opción Publicar.":::

    Si todavía no tiene un perfil de publicación, siga las instrucciones para crear uno y elija el tipo de destino **Carpeta**.

01. Elija **Editar**.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Perfil de publicación de Visual Studio con el botón Editar.":::

01. En el cuadro de diálogo **Configuración de perfil**, establezca las opciones siguientes:

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
