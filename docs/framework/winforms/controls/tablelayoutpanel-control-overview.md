---
title: "Información general sobre el control TableLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd8d68aa57ffe8b6fb84ceddf9d01aed56d40bdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="861f2-102">Información general sobre el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="861f2-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="861f2-103">El control <xref:System.Windows.Forms.TableLayoutPanel> organiza su contenido en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="861f2-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="861f2-104">Como el diseño se realiza en tiempo de diseño y en tiempo de ejecución, puede cambiar dinámicamente cuando cambie el entorno de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="861f2-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="861f2-105">Esto proporciona a los controles del panel la capacidad de ajustar el tamaño proporcionalmente para poder responder a cambios como el ajuste de tamaño del control primario o el cambio de longitud del texto debido a la localización.</span><span class="sxs-lookup"><span data-stu-id="861f2-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="861f2-106">Cualquier control de Windows Forms puede ser un control secundario del control <xref:System.Windows.Forms.TableLayoutPanel>, incluidas otras instancias de <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="861f2-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="861f2-107">Esto permite construir diseños sofisticados que se adaptan a los cambios en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="861f2-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="861f2-108">El control <xref:System.Windows.Forms.TableLayoutPanel> puede expandirse para acomodar nuevos controles cuando se agreguen, dependiendo del valor de las propiedades <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> y <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="861f2-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="861f2-109">Establecer las propiedades <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> o <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> en un valor de 0 especifica que el <xref:System.Windows.Forms.TableLayoutPanel> se desenlazará en la dirección correspondiente.</span><span class="sxs-lookup"><span data-stu-id="861f2-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="861f2-110">También puede controlar la dirección de expansión (horizontal o vertical) cuando el control <xref:System.Windows.Forms.TableLayoutPanel> se llene de controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="861f2-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="861f2-111">De forma predeterminada, el control <xref:System.Windows.Forms.TableLayoutPanel> se expande hacia abajo agregando filas.</span><span class="sxs-lookup"><span data-stu-id="861f2-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="861f2-112">Si quiere que el comportamiento de las filas y columnas sea diferente del predeterminado, puede controlar las propiedades de las filas y columnas mediante las propiedades <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> y <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="861f2-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="861f2-113">Puede establecer las propiedades de las filas o columnas individualmente.</span><span class="sxs-lookup"><span data-stu-id="861f2-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="861f2-114">El control <xref:System.Windows.Forms.TableLayoutPanel> agrega las siguientes propiedades a sus controles secundarios: `Cell`, `Column`, `Row`, `ColumnSpan` y `RowSpan`.</span><span class="sxs-lookup"><span data-stu-id="861f2-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="861f2-115">Puede combinar las celdas del control <xref:System.Windows.Forms.TableLayoutPanel> estableciendo las propiedades `ColumnSpan` o `RowSpan` de un control secundario.</span><span class="sxs-lookup"><span data-stu-id="861f2-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1.  <span data-ttu-id="861f2-116">[Cómo: Alinear y expandir un control en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="861f2-116">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="861f2-117">[Cómo: Abarcar filas y columnas en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="861f2-117">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="861f2-118">[Cómo: Editar columnas y filas en un control TableLayoutPanel](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="861f2-118">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="861f2-119">[Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="861f2-119">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="861f2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="861f2-120">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 [<span data-ttu-id="861f2-121">Crear un diseño de formularios Windows Forms que sea apropiado para la localización</span><span class="sxs-lookup"><span data-stu-id="861f2-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="861f2-122">Crear Windows Forms de entrada de datos de tamaño variable</span><span class="sxs-lookup"><span data-stu-id="861f2-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 [<span data-ttu-id="861f2-123">Procedimientos recomendados para el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="861f2-123">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)
