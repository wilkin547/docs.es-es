---
title: 'Cambio importante: Blazor: propiedad WebEventDescriptor.EventArgsType reemplazada'
description: Obtenga información sobre el cambio importante en ASP.NET Core 6.0 en el que la propiedad WebEventDescriptor.EventArgsType se reemplaza por la propiedad EventName.
author: scottaddie
ms.author: scaddie
ms.date: 02/24/2021
no-loc:
- Blazor
ms.openlocfilehash: 6df086ed234c0071ede83e9fe9d1710f011a2039
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260019"
---
# <a name="blazor-no-loc-textwebeventdescriptoreventargstype-property-replaced"></a>Blazor: propiedad :::no-loc text="WebEventDescriptor.EventArgsType"::: reemplazada

La clase <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor> forma parte del protocolo interno de Blazor para comunicar eventos de JavaScript en .NET. El código de la aplicación no suele usar esta clase, pero, en su lugar, sí la utilizan los autores de la plataforma.

A partir de ASP.NET Core 6.0, la propiedad <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A> de `WebEventDescriptor` se reemplaza por una nueva propiedad `EventName`. Es poco probable que este cambio afecte al código de la aplicación, ya que se trata de un detalle de implementación de plataforma de bajo nivel.

## <a name="version-introduced"></a>Versión introducida

6.0

## <a name="old-behavior"></a>Comportamiento anterior

En ASP.NET Core 5.0 y versiones anteriores, la propiedad `EventArgsType` describe un nombre de categoría no estándar específico de Blazor para grupos de tipos de eventos DOM. Por ejemplo, los eventos `click` y `mousedown` se asignan a un valor `EventArgsType` de `mouse`. De forma similar, los eventos `cut`, `copy` y `paste` se asignan a un valor `EventArgsType` de `clipboard`. Estos nombres de categoría se usan para determinar el tipo de .NET que se va a usar para deserializar los datos de los argumentos de eventos entrantes.

## <a name="new-behavior"></a>Comportamiento nuevo

A partir de ASP.NET Core 6.0, la nueva propiedad `EventName` solo especifica el nombre del evento original. Por ejemplo, `click`, `mousedown`, `cut`, `copy` o `paste`. Ya no es necesario proporcionar un nombre de categoría específico de Blazor. Por ese motivo, se quita la propiedad anterior `EventArgsType`.

## <a name="reason-for-change"></a>Motivo del cambio

En la solicitud de incorporación de cambios [dotnet/aspnetcore#29993](https://github.com/dotnet/aspnetcore/pull/29993), se presentó la compatibilidad con las clases de argumentos de eventos personalizados. Como parte de esta compatibilidad, el marco de trabajo ya no se basa en todos los eventos englobados dentro de conjunto predefinido de categorías. El marco de trabajo ahora solo necesita conocer el nombre de evento original.

## <a name="recommended-action"></a>Acción recomendada

El código de la aplicación no debe verse afectado y no es necesario modificarlo.

Si crea una plataforma de representación de Blazor personalizada, puede que tenga que actualizar el mecanismo para enviar eventos a `Renderer`. Reemplace cualquier regla codificada de forma rígida sobre las categorías de eventos con una lógica más sencilla que proporcione el nombre de evento sin formato original.

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`P:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType`

-->
