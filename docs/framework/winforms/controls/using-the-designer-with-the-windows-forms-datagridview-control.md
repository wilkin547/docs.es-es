---
title: "Utilizar el Diseñador con el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b29904954a593607a7872c0b59265bbf241dce98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="5c250-102">Utilizar el Diseñador con el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c250-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5c250-103">Visual Studio proporciona compatibilidad con el diseñador para el `DataGridView` control que le permite realizar muchas tareas de configuración sin escribir código.</span><span class="sxs-lookup"><span data-stu-id="5c250-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="5c250-104">Estas tareas incluyen enlace el control a un origen de datos, modificar las columnas que se utiliza para mostrar los datos y ajustar la apariencia y el comportamiento básico del control.</span><span class="sxs-lookup"><span data-stu-id="5c250-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c250-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5c250-105">In This Section</span></span>  
 [<span data-ttu-id="5c250-106">Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-107">Describe cómo utilizar el **agregar columnas** y **Editar columnas** cuadros de diálogo para rellenar y modificar la colección de columnas.</span><span class="sxs-lookup"><span data-stu-id="5c250-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="5c250-108">Enlazar datos al control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-109">Describe cómo utilizar el **Elegir origen de datos** opción de etiquetas inteligentes del control para conectarse a los datos.</span><span class="sxs-lookup"><span data-stu-id="5c250-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="5c250-110">Cambiar el orden de las columnas en el control DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-111">Describe cómo utilizar el **Editar columnas** cuadro de diálogo para reorganizar las columnas.</span><span class="sxs-lookup"><span data-stu-id="5c250-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="5c250-112">Cambiar el tipo de una columna DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="5c250-113">Describe cómo utilizar el **Editar columnas** cuadro de diálogo para cambiar los tipos de columna.</span><span class="sxs-lookup"><span data-stu-id="5c250-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="5c250-114">Habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-115">Describe cómo utilizar etiquetas inteligentes del control para permitir a los usuarios reorganizar columnas.</span><span class="sxs-lookup"><span data-stu-id="5c250-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="5c250-116">Inmovilizar columnas en el control DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-117">Describe cómo utilizar el **Editar columnas** cuadro de diálogo para evitar que las columnas concretas de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="5c250-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="5c250-118">Ocultar columnas en el control DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-119">Describe cómo utilizar el **Editar columnas** cuadro de diálogo para ocultar columnas concretas.</span><span class="sxs-lookup"><span data-stu-id="5c250-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="5c250-120">Crear columnas de sólo lectura en el control DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-121">Describe cómo utilizar el **Editar columnas** cuadro de diálogo para impedir que los usuarios editen valores en columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="5c250-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="5c250-122">Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-123">Describe cómo utilizar etiquetas inteligentes del control para evitar que los usuarios agreguen o eliminen filas.</span><span class="sxs-lookup"><span data-stu-id="5c250-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="5c250-124">Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="5c250-125">Describe cómo utilizar el **generador de CellStyle** cuadro de diálogo para crear un aspecto de carta en el control.</span><span class="sxs-lookup"><span data-stu-id="5c250-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="5c250-126">Establecer estilos de celdas y formatos de datos predeterminados en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="5c250-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/default-cell-styles-datagridview.md)  
 <span data-ttu-id="5c250-127">Describe cómo utilizar el **generador de CellStyle** formatos de cuadro de diálogo para configurar la apariencia básica y visualización de datos para el control.</span><span class="sxs-lookup"><span data-stu-id="5c250-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5c250-128">Referencia</span><span class="sxs-lookup"><span data-stu-id="5c250-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="5c250-129">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5c250-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c250-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c250-130">See Also</span></span>  
 [<span data-ttu-id="5c250-131">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="5c250-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
