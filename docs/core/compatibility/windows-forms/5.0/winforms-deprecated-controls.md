---
title: 'Cambio importante: Controles de barra de estado quitados'
description: Obtenga información sobre el cambio importante en .NET 5 donde algunos controles de Windows Forms ya no están disponibles.
ms.date: 07/18/2020
ms.openlocfilehash: c93b16047896b263248858e807b74c547cfa6d9d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256196"
---
# <a name="removed-status-bar-controls"></a>Controles de barra de estado quitados

A partir de .NET 5, algunos controles de Windows Forms ya no están disponibles.

## <a name="change-description"></a>Descripción del cambio

A partir de .NET 5, algunos de los controles de Windows Forms relacionados con la barra de estado ya no están disponibles. Los controles de reemplazo, con un mejor diseño y soporte técnico, se introdujeron en .NET Framework 2.0. Los controles en desuso se eliminaron previamente de los cuadros de herramientas del diseñador, pero todavía estaban disponibles para su uso. Ahora, se han quitado por completo.

Los siguientes tipos ya no están disponibles:

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Vaya a las API de reemplazo de estos controles y sus escenarios:

| Control anterior (API) | Reemplazo recomendado                          |
|-------------------|--------------------------------------------------|
| StatusBar         | <xref:System.Windows.Forms.StatusStrip>          |
| StatusBarPanel    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

## <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle`

### Category

Windows Forms

-->
