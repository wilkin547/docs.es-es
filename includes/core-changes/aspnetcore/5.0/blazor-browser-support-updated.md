---
ms.openlocfilehash: 584014572ab799e1e3ab2f02c9fbf4fe6b0c17e7
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804936"
---
### <a name="blazor-updated-browser-support"></a>Blazor: compatibilidad con exploradores actualizada

En ASP.NET Core 5.0 se presentan [nuevas características de Blazor](https://github.com/dotnet/aspnetcore/issues/21514) y algunas son incompatibles con los exploradores más antiguos. La lista de exploradores admitidos por Blazor en ASP.NET Core 5.0 se ha actualizado en consecuencia.

Para obtener información, vea la incidencia de GitHub [n.º 26475 (dotnet/aspnetcore)](https://github.com/dotnet/aspnetcore/issues/26475).

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="old-behavior"></a>Comportamiento anterior

Blazor Server es compatible con Microsoft Internet Explorer 11 con polyfill suficientes. Blazor Server y Blazor WebAssembly también funcionan en [Microsoft Edge (versión anterior)](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy).

#### <a name="new-behavior"></a>Comportamiento nuevo

Blazor Server en ASP.NET Core 5.0 no es compatible con Microsoft Internet Explorer 11. Blazor Server y Blazor WebAssembly no son totalmente funcionales en Microsoft Edge (versión anterior).

#### <a name="reason-for-change"></a>Motivo del cambio

Las nuevas características de Blazor en ASP.NET Core 5.0 no son compatibles con estos exploradores más antiguos, cuyo uso está disminuyendo. Para obtener más información, vea los siguientes recursos:

* [La compatibilidad de Windows con Microsoft Edge (versión anterior) también finaliza el 9 de marzo de 2021](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [Las aplicaciones y servicios de Microsoft 365 finalizarán la compatibilidad con Microsoft Internet Explorer 11 el 17 de agosto de 2021](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

#### <a name="recommended-action"></a>Acción recomendada

Actualice estos exploradores antiguos al [nuevo Microsoft Edge basado en Chromium](https://www.microsoft.com/edge). En el caso de las aplicaciones de Blazor que necesiten admitir estos exploradores antiguos, use ASP.NET Core 3.1. La lista de exploradores admitidos para Blazor en ASP.NET Core 3.1 no ha cambiado y está documentada en [Plataformas admitidas](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!--

#### Affected APIs

Not detectable via API analysis

-->
