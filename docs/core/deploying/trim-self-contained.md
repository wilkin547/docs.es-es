---
title: Recorte de aplicaciones autocontenidas
description: Obtenga información sobre cómo recortar aplicaciones autocontenidas para reducir su tamaño. .NET Core agrupa el tiempo de ejecución con una aplicación que se publica autocontenida y que, por lo general, incluye más tiempo de ejecución del que es necesario.
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665624"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Recorte de implementaciones autocontenidas y ejecutables

Al publicar una aplicación autocontenida, el tiempo de ejecución de .NET Core se agrupa junto con la aplicación. Esta agrupación agrega una cantidad considerable de contenido a la aplicación empaquetada.

En lo que respecta a la implementación de la aplicación, el tamaño suele ser un factor importante. Mantener lo más pequeño posible el tamaño de la aplicación del paquete suele ser un objetivo para los desarrolladores de aplicaciones.

En función de la complejidad de la aplicación, solo se necesita un subconjunto del tiempo de ejecución para ejecutarla. Estas partes sin usar del tiempo de ejecución no son necesarias y se pueden recortar de la aplicación empaquetada.

> [!NOTE]
> El recorte es una característica experimental en .NET Core 3.1 y _solo_ está disponible para las aplicaciones que se publican autocontenidas.

## <a name="trim-your-application"></a>Recorte de la aplicación

En el ejemplo siguiente se muestra cómo recortar la aplicación mediante el comando [dotnet publish](../tools/dotnet-publish.md):

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

La característica recorte funciona examinando los archivos binarios de la aplicación para descubrir y compilar un gráfico de los ensamblados en tiempo de ejecución necesarios. Los ensamblados en tiempo de ejecución restantes a los que no se hace referencia se recortan.

## <a name="trimming-issues-when-using-reflection"></a>Recorte de incidencias al usar reflexión

Hay escenarios en los que la función de recorte no podrá detectar referencias. Por ejemplo, una aplicación que utiliza reflexión podría encontrarse con esta incidencia porque la dependencia del ensamblado solo se conocerá en tiempo de ejecución.

El recorte es solo un problema si el uso de la reflexión depende de un ensamblado en tiempo de ejecución al que no se hace referencia directamente. Tenga en cuenta que es posible que el código de la aplicación no esté usando la reflexión directamente, sino que lo haga un ensamblado de terceros al que haga referencia.

Cuando el código hace referencia a una API mediante reflexión y no se quiere que el enlazador recorte el ensamblado que contiene esa API, se puede modificar el archivo del proyecto para excluir el ensamblado del proceso de recorte. En el ejemplo siguiente se muestra cómo evitar que un ensamblado llamado `System.Security` se recorte:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a>Vea también

- [Implementación de aplicaciones .NET Core](index.md)
