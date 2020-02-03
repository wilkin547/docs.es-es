---
title: Enlazar controles al componente BindingSource mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 35b3fb7b9884f07dd6e2aef311a01d3090c44227
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744392"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="6b5c8-102">Cómo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="6b5c8-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="6b5c8-103">Después de haber agregado controles al formulario y determinado la interfaz de usuario de la aplicación, puede enlazar los controles a un origen de datos, de modo que, en tiempo de ejecución, los usuarios puedan modificar y guardar los datos relacionados con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>

 <span data-ttu-id="6b5c8-104">Enlazar un control o una serie de controles en Windows Forms se consigue más fácilmente mediante el control <xref:System.Windows.Forms.BindingSource> como un puente entre los controles del formulario y el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>

 <span data-ttu-id="6b5c8-105">Uno o varios controles de un formulario se pueden enlazar a datos; en el procedimiento siguiente, se enlaza un control <xref:System.Windows.Forms.TextBox> a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>

 <span data-ttu-id="6b5c8-106">Para completar el procedimiento, se supone que se enlazará a un origen de datos derivado de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="6b5c8-107">Para obtener más información sobre cómo crear orígenes de datos de otros almacenes de datos, vea [agregar nuevos orígenes](/visualstudio/data-tools/add-new-data-sources)de datos.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>

## <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="6b5c8-108">Para enlazar un control en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="6b5c8-108">To bind a control at design time</span></span>

1. <span data-ttu-id="6b5c8-109">Arrastre un control <xref:System.Windows.Forms.TextBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-109">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>

2. <span data-ttu-id="6b5c8-110">En la ventana **propiedades** :</span><span class="sxs-lookup"><span data-stu-id="6b5c8-110">In the **Properties** window:</span></span>

    1. <span data-ttu-id="6b5c8-111">Expanda el nodo **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="6b5c8-111">Expand the **(DataBindings)** node.</span></span>

    2. <span data-ttu-id="6b5c8-112">Haga clic en la flecha situada junto a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-112">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

         <span data-ttu-id="6b5c8-113">Se abre el editor de tipos de interfaz de usuario de **DataSource** .</span><span class="sxs-lookup"><span data-stu-id="6b5c8-113">The **DataSource** UI type editor opens.</span></span>

         <span data-ttu-id="6b5c8-114">Si previamente se ha configurado un origen de datos para el proyecto o formulario, aparecerá.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-114">If a data source has previously been configured for the project or form, it will appear.</span></span>

3. <span data-ttu-id="6b5c8-115">Haga clic en **Agregar origen de datos del proyecto** para conectar con los datos y crear un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-115">Click **Add Project Data Source** to connect to data and create a data source.</span></span>

4. <span data-ttu-id="6b5c8-116">En la página principal del **Asistente para la configuración de orígenes de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-116">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>

5. <span data-ttu-id="6b5c8-117">En la página **elegir un tipo de origen de datos** , seleccione **base**de datos.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-117">On the **Choose a Data Source Type** page, select **Database**.</span></span>

6. <span data-ttu-id="6b5c8-118">En la página **elegir la conexión de datos** , seleccione una conexión de datos de la lista de conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-118">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="6b5c8-119">Si la conexión de datos deseada no está disponible, seleccione **nueva conexión** para crear una nueva conexión de datos.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-119">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>

7. <span data-ttu-id="6b5c8-120">Seleccione **sí, guardar la conexión** para guardar la cadena de conexión en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-120">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>

8. <span data-ttu-id="6b5c8-121">Seleccione los objetos de base de datos que va a traer a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-121">Select the database objects to bring into your application.</span></span> <span data-ttu-id="6b5c8-122">En este caso, seleccione un campo de una tabla que le gustaría que mostrara el <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-122">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>

9. <span data-ttu-id="6b5c8-123">Reemplace el nombre del conjunto de datos predeterminado, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-123">Replace the default dataset name if you want.</span></span>

10. <span data-ttu-id="6b5c8-124">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="6b5c8-124">Click **Finish**.</span></span>

11. <span data-ttu-id="6b5c8-125">En la ventana **propiedades** , haga clic de nuevo en la flecha situada junto a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-125">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="6b5c8-126">En el editor de tipos de interfaz de usuario de **DataSource** , seleccione el nombre del campo al que se va a enlazar el <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-126">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>

     <span data-ttu-id="6b5c8-127">El editor de tipos de interfaz de usuario del **origen** de datos se cierra y el conjunto de datos, <xref:System.Windows.Forms.BindingSource> y el adaptador de tabla específicos de esa conexión de datos se agregan al formulario.</span><span class="sxs-lookup"><span data-stu-id="6b5c8-127">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b5c8-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b5c8-128">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="6b5c8-129">Agregar nuevos orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="6b5c8-129">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="6b5c8-130">[Ventana orígenes de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="6b5c8-130">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
