---
title: Procedimiento para crear un control enlazado y aplicar formato a los datos mostrados
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 052e619acb23fb2e25f42daf7b4eaaacb0688f31
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039424"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="37345-102">Procedimiento para crear un control enlazado y aplicar formato a los datos mostrados</span><span class="sxs-lookup"><span data-stu-id="37345-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="37345-103">Con Windows Forms enlace de datos, puede dar formato a los datos mostrados en un control enlazado a datos mediante el cuadro de diálogo **formato y enlace avanzado** .</span><span class="sxs-lookup"><span data-stu-id="37345-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>


### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="37345-104">Para enlazar un control y dar formato a los datos mostrados</span><span class="sxs-lookup"><span data-stu-id="37345-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="37345-105">Conéctese a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="37345-105">Connect to a data source.</span></span>

     <span data-ttu-id="37345-106">Para obtener más información, vea [conectarse a un origen de datos](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="37345-106">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="37345-107">En el formulario, seleccione el control y, después, abra la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="37345-107">In the form, select the control, and then open the Properties window.</span></span>

3. <span data-ttu-id="37345-108">Expanda la propiedad **(DataBindings)** y, a continuación, en el cuadro **(avanzado)** , haga clic en el![botón de puntos suspensivos (el botón de puntos suspensivos (...)](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)en el ventana Propiedades de Visual Studio) para mostrar el **formato y opciones avanzadas.** Cuadro de diálogo de enlace, que tiene una lista completa de las propiedades de ese control.</span><span class="sxs-lookup"><span data-stu-id="37345-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="37345-109">Seleccione la propiedad que desea enlazar y, a continuación, haga clic en la flecha de **enlace** .</span><span class="sxs-lookup"><span data-stu-id="37345-109">Select the property you want to bind, and then click the **Binding** arrow.</span></span>

     <span data-ttu-id="37345-110">Se muestra una lista de los orígenes de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="37345-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="37345-111">Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos que desea.</span><span class="sxs-lookup"><span data-stu-id="37345-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="37345-112">Por ejemplo, si va a enlazar a un valor de columna en la tabla de un conjunto de datos, expanda el nombre del conjunto de datos y, después, expanda el nombre de la tabla para mostrar los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="37345-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="37345-113">Haga clic en el nombre del elemento al que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="37345-113">Click the name of an element to bind to.</span></span>

7. <span data-ttu-id="37345-114">En el cuadro **tipo de formato** , haga clic en el formato que desea aplicar a los datos mostrados en el control.</span><span class="sxs-lookup"><span data-stu-id="37345-114">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="37345-115">En cada caso, puede especificar el valor mostrado en el control si el origen de datos contiene <xref:System.DBNull>.</span><span class="sxs-lookup"><span data-stu-id="37345-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="37345-116">De lo contrario, las opciones varían ligeramente, dependiendo del tipo de formato que elija.</span><span class="sxs-lookup"><span data-stu-id="37345-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="37345-117">En la siguiente tabla se muestran los tipos de formato y las opciones.</span><span class="sxs-lookup"><span data-stu-id="37345-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="37345-118">Tipo de formato</span><span class="sxs-lookup"><span data-stu-id="37345-118">Format type</span></span>|<span data-ttu-id="37345-119">Opción de formato</span><span class="sxs-lookup"><span data-stu-id="37345-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="37345-120">Sin formato</span><span class="sxs-lookup"><span data-stu-id="37345-120">No Formatting</span></span>|<span data-ttu-id="37345-121">No hay opciones.</span><span class="sxs-lookup"><span data-stu-id="37345-121">No options.</span></span>|
    |<span data-ttu-id="37345-122">Numeric</span><span class="sxs-lookup"><span data-stu-id="37345-122">Numeric</span></span>|<span data-ttu-id="37345-123">Especifique el número de posiciones decimales mediante el control de flechas de **posiciones** decimales.</span><span class="sxs-lookup"><span data-stu-id="37345-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="37345-124">Currency</span><span class="sxs-lookup"><span data-stu-id="37345-124">Currency</span></span>|<span data-ttu-id="37345-125">Especifique el número de posiciones decimales mediante el control de flechas de **posiciones** decimales.</span><span class="sxs-lookup"><span data-stu-id="37345-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="37345-126">Fecha Hora</span><span class="sxs-lookup"><span data-stu-id="37345-126">Date Time</span></span>|<span data-ttu-id="37345-127">Seleccione el modo en que se debe mostrar la fecha y la hora seleccionando uno de los elementos en el cuadro de selección **tipo** .</span><span class="sxs-lookup"><span data-stu-id="37345-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="37345-128">Científica</span><span class="sxs-lookup"><span data-stu-id="37345-128">Scientific</span></span>|<span data-ttu-id="37345-129">Especifique el número de posiciones decimales mediante el control de flechas de **posiciones** decimales.</span><span class="sxs-lookup"><span data-stu-id="37345-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="37345-130">Personalizados</span><span class="sxs-lookup"><span data-stu-id="37345-130">Custom</span></span>|<span data-ttu-id="37345-131">Especifique una cadena de formato personalizado using.</span><span class="sxs-lookup"><span data-stu-id="37345-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="37345-132">Para obtener más información, consulte [Aplicar formato a tipos](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="37345-132">For more information, see [Formatting Types](../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="37345-133">**Nota:**  No se garantiza que las cadenas de formato personalizado realicen correctamente el recorrido de ida y vuelta entre el origen de datos y el control enlazado.</span><span class="sxs-lookup"><span data-stu-id="37345-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="37345-134">En su lugar, controle el evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> del enlace y aplique el formato personalizado en el código de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="37345-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="37345-135">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **formato y enlace avanzado** y volver al ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="37345-135">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="37345-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="37345-136">See also</span></span>

- [<span data-ttu-id="37345-137">Cómo: Crear un control de enlace simple en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37345-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="37345-138">Validación de los datos proporcionados por el usuario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37345-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="37345-139">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37345-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
