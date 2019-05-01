---
title: Procedimiento para crear un control enlazado y aplicar formato a los datos mostrados
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: f7f1ed2fbca4ab8892cb6c439ae8841fa8828bf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008972"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="7a9a6-102">Procedimiento para crear un control enlazado y aplicar formato a los datos mostrados</span><span class="sxs-lookup"><span data-stu-id="7a9a6-102">How to: Create a Bound Control and Format the Displayed Data</span></span>
<span data-ttu-id="7a9a6-103">Con el enlace de datos de Windows Forms, puede dar formato a los datos mostrados en un control enlazado a datos mediante el uso de la **formato y enlace avanzada** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a9a6-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7a9a6-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="7a9a6-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7a9a6-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="7a9a6-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="7a9a6-107">Para enlazar un control y dar formato a los datos mostrados</span><span class="sxs-lookup"><span data-stu-id="7a9a6-107">To bind a control and format the displayed data</span></span>  
  
1. <span data-ttu-id="7a9a6-108">Conéctese a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-108">Connect to a data source.</span></span>  
  
     <span data-ttu-id="7a9a6-109">Para obtener más información, consulte [conectarse a un origen de datos](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="7a9a6-109">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2. <span data-ttu-id="7a9a6-110">En el formulario, seleccione el control y, después, abra la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-110">In the form, select the control, and then open the Properties window.</span></span>  
  
3. <span data-ttu-id="7a9a6-111">Expanda el **(DataBindings)** propiedad y, a continuación, en el **(avanzado)** cuadro, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](./media/vbellipsesbutton.png " vbEllipsesButton")) para mostrar el **formato y enlace de datos avanzado** cuadro de diálogo que muestra una lista completa de propiedades para ese control.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-111">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](./media/vbellipsesbutton.png "vbEllipsesButton")) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>  
  
4. <span data-ttu-id="7a9a6-112">Seleccione la propiedad que desea enlazar y, a continuación, haga clic en el **enlace** flecha.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-112">Select the property you want to bind, and then click the **Binding** arrow.</span></span>  
  
     <span data-ttu-id="7a9a6-113">Se muestra una lista de los orígenes de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-113">A list of available data sources is displayed.</span></span>  
  
5. <span data-ttu-id="7a9a6-114">Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos que desea.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-114">Expand the data source you want to bind to until you find the single data element you want.</span></span>  
  
     <span data-ttu-id="7a9a6-115">Por ejemplo, si va a enlazar a un valor de columna en la tabla de un conjunto de datos, expanda el nombre del conjunto de datos y, después, expanda el nombre de la tabla para mostrar los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-115">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
6. <span data-ttu-id="7a9a6-116">Haga clic en el nombre del elemento al que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-116">Click the name of an element to bind to.</span></span>  
  
7. <span data-ttu-id="7a9a6-117">En el **dar formato a tipo** cuadro, haga clic en el formato que desee aplicar a los datos mostrados en el control.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-117">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>  
  
     <span data-ttu-id="7a9a6-118">En cada caso, puede especificar el valor mostrado en el control si el origen de datos contiene <xref:System.DBNull>.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-118">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="7a9a6-119">De lo contrario, las opciones varían ligeramente, dependiendo del tipo de formato que elija.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-119">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="7a9a6-120">En la siguiente tabla se muestran los tipos de formato y las opciones.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-120">The following table shows the format types and options.</span></span>  
  
    |<span data-ttu-id="7a9a6-121">Tipo de formato</span><span class="sxs-lookup"><span data-stu-id="7a9a6-121">Format type</span></span>|<span data-ttu-id="7a9a6-122">Opción de formato</span><span class="sxs-lookup"><span data-stu-id="7a9a6-122">Formatting option</span></span>|  
    |-----------------|-----------------------|  
    |<span data-ttu-id="7a9a6-123">Sin formato</span><span class="sxs-lookup"><span data-stu-id="7a9a6-123">No Formatting</span></span>|<span data-ttu-id="7a9a6-124">No hay opciones.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-124">No options.</span></span>|  
    |<span data-ttu-id="7a9a6-125">Numérica</span><span class="sxs-lookup"><span data-stu-id="7a9a6-125">Numeric</span></span>|<span data-ttu-id="7a9a6-126">Especifique el número de posiciones decimales mediante **decimales** control de flechas.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-126">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="7a9a6-127">Moneda</span><span class="sxs-lookup"><span data-stu-id="7a9a6-127">Currency</span></span>|<span data-ttu-id="7a9a6-128">Especifique el número de posiciones decimales mediante **decimales** control de flechas.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-128">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="7a9a6-129">Fecha Hora</span><span class="sxs-lookup"><span data-stu-id="7a9a6-129">Date Time</span></span>|<span data-ttu-id="7a9a6-130">Seleccione cómo se deben mostrar la fecha y hora seleccionando uno de los elementos en el **tipo** cuadro de selección.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-130">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|  
    |<span data-ttu-id="7a9a6-131">Científica</span><span class="sxs-lookup"><span data-stu-id="7a9a6-131">Scientific</span></span>|<span data-ttu-id="7a9a6-132">Especifique el número de posiciones decimales mediante **decimales** control de flechas.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-132">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="7a9a6-133">Personalizados</span><span class="sxs-lookup"><span data-stu-id="7a9a6-133">Custom</span></span>|<span data-ttu-id="7a9a6-134">Especifique una cadena de formato personalizado using.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-134">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="7a9a6-135">Para obtener más información, consulte [Aplicar formato a tipos](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="7a9a6-135">For more information, see [Formatting Types](../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="7a9a6-136">**Nota:**  No se garantiza que las cadenas de formato personalizado realicen correctamente el recorrido de ida y vuelta entre el origen de datos y el control enlazado.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-136">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="7a9a6-137">En su lugar, controle el evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> del enlace y aplique el formato personalizado en el código de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-137">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|  
  
8. <span data-ttu-id="7a9a6-138">Haga clic en **Aceptar** para cerrar el **formato y enlace de datos avanzado** cuadro de diálogo y volver a la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="7a9a6-138">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9a6-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a9a6-139">See also</span></span>

- [<span data-ttu-id="7a9a6-140">Cómo: Crear un Control con enlace Simple en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="7a9a6-140">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="7a9a6-141">Validación de los datos proporcionados por el usuario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a9a6-141">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="7a9a6-142">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a9a6-142">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
