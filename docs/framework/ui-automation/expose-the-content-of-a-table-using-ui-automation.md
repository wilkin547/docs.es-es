---
title: Exponer el contenido de una tabla mediante UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables, exposing content of
- UI Automation, exposing content of tables
- exposing content of tables using UI Automation
ms.assetid: ac3c5eaa-49c7-4653-b83e-532e2a2604a2
ms.openlocfilehash: ee565fa07a8b137152bbc0ef6aa4038f2cf6d421
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043797"
---
# <a name="expose-the-content-of-a-table-using-ui-automation"></a><span data-ttu-id="bd7f0-102">Exponer el contenido de una tabla mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="bd7f0-102">Expose the Content of a Table Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="bd7f0-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="bd7f0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bd7f0-104">Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="bd7f0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="bd7f0-105">En este tema se [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] muestra cómo se puede usar para exponer el contenido y las propiedades intrínsecas de cada celda de un control tabular.</span><span class="sxs-lookup"><span data-stu-id="bd7f0-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose the content and intrinsic properties of each cell within a tabular control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd7f0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd7f0-106">Example</span></span>  
 <span data-ttu-id="bd7f0-107">En el ejemplo de código siguiente se muestra cómo <xref:System.Windows.Automation.AutomationElement> obtener un que representa el contenido de una celda de tabla; también se obtienen las propiedades de celda, como índices de fila y columna, intervalos de filas y columnas, y la información de encabezado de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="bd7f0-107">The following code example demonstrates how to obtain a <xref:System.Windows.Automation.AutomationElement> that represents the content of a table cell; cell properties such as row and column indices, row and column spans, and row and column header information are also obtained.</span></span> <span data-ttu-id="bd7f0-108">En este ejemplo se usa un controlador de eventos de cambio de foco para simular el recorrido del teclado de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un control tabular que implementa.</span><span class="sxs-lookup"><span data-stu-id="bd7f0-108">This example uses a focus change event handler to simulate keyboard traversal of a tabular control that implements [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="bd7f0-109">La información de cada elemento de la tabla se expone en un evento de cambio de foco.</span><span class="sxs-lookup"><span data-stu-id="bd7f0-109">Information for each table item is exposed on a focus change event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd7f0-110">Dado que los cambios de foco son eventos de escritorio globales, se deben filtrar los eventos de cambio de foco fuera de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd7f0-110">Since focus changes are global desktop events, focus change events outside the table should be filtered.</span></span> <span data-ttu-id="bd7f0-111">Vea el [ejemplo TrackFocus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) para obtener una implementación relacionada.</span><span class="sxs-lookup"><span data-stu-id="bd7f0-111">See the [TrackFocus Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771428(v=vs.90)) for a related implementation.</span></span>  
  
 [!code-csharp[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#starttarget)]
 [!code-vb[UIATableItemPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#starttarget)]  
[!code-csharp[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#gettableelement)]
[!code-vb[UIATableItemPattern_snip#GetTableElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#gettableelement)]  
[!code-csharp[UIATableItemPattern_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#101)]
[!code-vb[UIATableItemPattern_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#101)]  
[!code-csharp[UIATableItemPattern_snip#1015](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#1015)]
[!code-vb[UIATableItemPattern_snip#1015](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#1015)]  
[!code-csharp[UIATableItemPattern_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#102)]
[!code-vb[UIATableItemPattern_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#102)]  
[!code-csharp[UIATableItemPattern_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATableItemPattern_snip/CSharp/UIATableItemPattern_snippets.cs#103)]
[!code-vb[UIATableItemPattern_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATableItemPattern_snip/VisualBasic/UIATableItemPattern_snippets.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="bd7f0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd7f0-112">See also</span></span>

- [<span data-ttu-id="bd7f0-113">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bd7f0-113">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="bd7f0-114">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="bd7f0-114">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="bd7f0-115">Implementación del patrón de control Table de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bd7f0-115">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="bd7f0-116">Implementación del patrón de control TableItem de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bd7f0-116">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="bd7f0-117">Implementación del patrón de control Grid de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bd7f0-117">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="bd7f0-118">Implementación del patrón de control GridItem de Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bd7f0-118">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
