---
title: Procedimiento para crear un control con enlace simple en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: df87f00e6e03de67c3fb1adc28472c96f4a47ef4
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015630"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="d9d0f-102">Procedimiento Crear un control de enlace simple en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9d0f-102">How to: Create a simple-bound control on a Windows Form</span></span>

<span data-ttu-id="d9d0f-103">Con el *enlace simple*, puede mostrar un único elemento de datos, como un valor de columna de una tabla de conjunto de datos, en un control.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="d9d0f-104">Puede enlazar de forma sencilla cualquier propiedad de un control con un valor de datos.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-104">You can simple-bind any property of a control to a data value.</span></span>

## <a name="to-simple-bind-a-control"></a><span data-ttu-id="d9d0f-105">Para enlazar un control de forma simple</span><span class="sxs-lookup"><span data-stu-id="d9d0f-105">To simple-bind a control</span></span>

1. <span data-ttu-id="d9d0f-106">Conéctese a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-106">Connect to a data source.</span></span> <span data-ttu-id="d9d0f-107">Para obtener más información, vea [conectarse a un origen de datos](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="d9d0f-107">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="d9d0f-108">En Visual Studio, seleccione el control en el formulario y muestre la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="d9d0f-108">In Visual Studio, select the control on the form and display the **Properties** window.</span></span>

3. <span data-ttu-id="d9d0f-109">Expanda la propiedad **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="d9d0f-109">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="d9d0f-110">Las propiedades que se enlazan con mayor frecuencia se muestran debajo de la propiedad **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="d9d0f-110">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="d9d0f-111">Por ejemplo, en la mayoría de los controles, la propiedad de **texto** se enlaza con mayor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-111">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="d9d0f-112">Si la propiedad que desea enlazar no es una de las propiedades enlazadas normalmente, haga clic en el![botón de **puntos suspensivos** (el botón de puntos suspensivos (...)](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)en el ventana Propiedades de Visual Studio) en el cuadro **(avanzado)** para mostrar el  **Cuadro de diálogo formato y enlace avanzado** con una lista completa de las propiedades de ese control.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-112">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="d9d0f-113">Seleccione la propiedad que desea enlazar y haga clic en la flecha desplegable situada debajo de **enlace**.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-113">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="d9d0f-114">Se muestra una lista de los orígenes de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-114">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="d9d0f-115">Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos que desea.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-115">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="d9d0f-116">Por ejemplo, si va a enlazar a un valor de columna en la tabla de un conjunto de datos, expanda el nombre del conjunto de datos y, después, expanda el nombre de la tabla para mostrar los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-116">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="d9d0f-117">Haga clic en el nombre del elemento al que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-117">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="d9d0f-118">Si está trabajando en el cuadro de diálogo **formato y enlace avanzado** , haga clic en **Aceptar** para volver a la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="d9d0f-118">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="d9d0f-119">Si desea enlazar propiedades adicionales del control, repita los pasos del 3 al 7.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-119">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d9d0f-120">Dado que los controles enlazados simples solo muestran un único elemento de datos, es muy habitual incluir la lógica de navegación en Windows Forms con controles enlazados de forma simple.</span><span class="sxs-lookup"><span data-stu-id="d9d0f-120">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9d0f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9d0f-121">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="d9d0f-122">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9d0f-122">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="d9d0f-123">Enlace de datos y Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9d0f-123">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
