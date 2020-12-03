---
title: 'Cambio importante: Blazor: Lógica de validación actualizada para los recursos web estáticos'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Lógica de validación actualizada para los recursos web estáticos'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f201818c0130739e8da4f42e7b1f3a1987f70d1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760162"
---
# <a name="blazor-updated-validation-logic-for-static-web-assets"></a>Blazor: Lógica de validación actualizada para los recursos web estáticos

Se ha producido una incidencia en la validación de conflictos para los recursos web estáticos en ASP.NET Core 3.1 y WebAssembly 3.2 de Blazor. La incidencia es la siguiente:

* Se ha impedido la detección de conflictos adecuada entre los recursos de host y los de las bibliotecas de clases de Razor (RCL) y las aplicaciones WebAssembly de Blazor.
* Principalmente afecta a las aplicaciones WebAssembly de Blazor, ya que, de forma predeterminada, los recursos web estáticos de las RCL se proporcionan con el prefijo `_content/$(PackageId)`.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="old-behavior"></a>Comportamiento anterior

Durante el desarrollo, se podrían reemplazar de forma silenciosa los recursos web estáticos de una RCL por los del proyecto del host en la misma ruta de acceso del host. Imagine que una RCL que haya definido un recurso web estático se proporciona en */carpeta/archivo.txt*. Si el host ha colocado un archivo en *wwwroot/carpeta/archivo.txt*, el archivo del servidor ha reemplazado en modo silencioso el de la RCL o la aplicación WebAssembly de Blazor.

## <a name="new-behavior"></a>Comportamiento nuevo

ASP.NET Core detecta correctamente el momento en el que se produce esta incidencia. Notifica el conflicto al usuario para que pueda tomar las medidas adecuadas.

## <a name="reason-for-change"></a>Motivo del cambio

Los recursos web estáticos no se han diseñado para que se puedan reemplazar por archivos en el host *wwwroot* del proyecto. Si se permite el reemplazo de esos archivos, se podrían producir errores difíciles de diagnosticar. Como resultado, se podrían producir cambios de comportamiento no definidos en las aplicaciones publicadas.

## <a name="recommended-action"></a>Acción recomendada

De forma predeterminada, no hay ningún motivo por el que un archivo de RCL esté en conflicto con un archivo en el host. Los archivos de RCL tienen el prefijo `_content/${PackageId}`. Los archivos WebAssembly de Blazor se colocan en la raíz del espacio de direcciones URL del host, lo que facilita los conflictos. Por ejemplo, las aplicaciones WebAssembly de Blazor contienen un archivo *favicon.ico* que el host también podría incluir en su carpeta *wwwroot*.

Si el origen del conflicto es un archivo de RCL, normalmente significa que el código copia recursos de la biblioteca en la carpeta *wwwroot* del proyecto. La escritura de código para copiar archivos anula uno de los objetivos principales de los recursos web estáticos. Este objetivo es fundamental para obtener actualizaciones en el explorador cuando se actualiza el contenido sin tener que desencadenar una nueva compilación.

Puede optar por conservar este comportamiento y mantener el archivo en el host. Para ello, quite el archivo de la lista de recursos web estáticos con un destino de MSBuild personalizado.

Para usar el archivo de la RCL o el de la aplicación WebAssembly de Blazor en lugar del archivo del proyecto de host, quite el archivo del proyecto del host.

## <a name="affected-apis"></a>API afectadas

None

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
