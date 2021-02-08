---
description: Más información acerca de cómo enlazar una propiedad de actividad personalizada a un control de diseñador
title: Enlazar una propiedad de actividad personalizada a un control de diseñador
ms.date: 03/30/2017
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
ms.openlocfilehash: 522e3df3028270d42f7654026383c628ec951e8d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787947"
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a><span data-ttu-id="4c3cd-103">Enlazar una propiedad de actividad personalizada a un control de diseñador</span><span class="sxs-lookup"><span data-stu-id="4c3cd-103">Binding a custom activity property to a designer control</span></span>

<span data-ttu-id="4c3cd-104">La operación de enlazar un control de diseñador de cuadro de texto a un argumento de actividad es bastante sencillo; sin embargo, la operación de enlazar un control de diseñador complejo (como un cuadro combinado) a un argumento de actividad puede presentar desafíos.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-104">Binding a text box designer control to an activity argument is fairly straightforward; binding a complex designer control (such as a combo box) to an activity argument may present challenges, however.</span></span> <span data-ttu-id="4c3cd-105">En este tema se analiza la forma de enlazar un argumento de actividad a un control de cuadro combinado en un diseñador de actividad personalizado.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-105">This topic discusses how to bind an activity argument to a combo box control on a custom activity designer.</span></span>

## <a name="creating-the-combo-box-item-converter"></a><span data-ttu-id="4c3cd-106">Crear el convertidor de elemento de cuadro combinado</span><span class="sxs-lookup"><span data-stu-id="4c3cd-106">Creating the combo box item converter</span></span>

1. <span data-ttu-id="4c3cd-107">Cree una nueva solución vacía en Visual Studio denominada CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-107">Create a new empty solution in Visual Studio called CustomProperty.</span></span>

2. <span data-ttu-id="4c3cd-108">Cree una nueva clase denominada ComboBoxItemConverter.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-108">Create a new class called ComboBoxItemConverter.</span></span> <span data-ttu-id="4c3cd-109">Agregue una referencia a System.Windows.Data y haga que la clase derive de <xref:System.Windows.Data.IValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-109">Add a reference to System.Windows.Data, and have the class derive from <xref:System.Windows.Data.IValueConverter>.</span></span> <span data-ttu-id="4c3cd-110">Haga que Visual Studio implemente la interfaz para generar códigos auxiliares para `Convert` y `ConvertBack`.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-110">Have Visual Studio implement the interface to generate stubs for `Convert` and `ConvertBack`.</span></span>

3. <span data-ttu-id="4c3cd-111">Agregue el siguiente código al método `Convert`.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-111">Add the following code to the `Convert` method.</span></span> <span data-ttu-id="4c3cd-112">Este código convierte el <xref:System.Activities.InArgument%601> de tipo <xref:System.String> de la actividad en el valor que se va a colocar en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-112">This code converts the activity's <xref:System.Activities.InArgument%601> of type <xref:System.String> to the value to be placed in the designer.</span></span>

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            VisualBasicValue<string> vbexpression = expression as VisualBasicValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (vbexpression != null)
            {
                return vbexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

     <span data-ttu-id="4c3cd-113">La expresión del fragmento de código anterior también se pueden crear mediante <xref:Microsoft.CSharp.Activities.CSharpValue%601> en lugar de <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-113">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            CSharpValue<string> csexpression = expression as CSharpValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (csexpression != null)
            {
                return csexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

4. <span data-ttu-id="4c3cd-114">Agregue el siguiente código al método `ConvertBack`.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-114">Add the following code to the `ConvertBack` method.</span></span> <span data-ttu-id="4c3cd-115">Este código vuelve a convertir el elemento de cuadro combinado de entrada en un <xref:System.Activities.InArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-115">This code converts the incoming combo box item back to an <xref:System.Activities.InArgument%601>.</span></span>

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(vbArgument);
                return inArgument;
    ```

     <span data-ttu-id="4c3cd-116">La expresión del fragmento de código anterior también se pueden crear mediante <xref:Microsoft.CSharp.Activities.CSharpValue%601> en lugar de <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-116">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(csArgument);
                return inArgument;
    ```

## <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a><span data-ttu-id="4c3cd-117">Agregar ComboBoxItemConverter al diseñador personalizado de una actividad</span><span class="sxs-lookup"><span data-stu-id="4c3cd-117">Adding the ComboBoxItemConverter to the custom designer of an activity</span></span>

1. <span data-ttu-id="4c3cd-118">Agregue un nuevo elemento al proyecto.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-118">Add a new item to the project.</span></span> <span data-ttu-id="4c3cd-119">En el cuadro de diálogo Nuevo elemento, seleccione el nodo de flujo de trabajo y seleccione Diseñador de actividad como tipo del nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-119">In the New Item dialog, select the Workflow node and select Activity Designer as the type of the new item.</span></span> <span data-ttu-id="4c3cd-120">Asigne al elemento el nombre CustomPropertyDesigner.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-120">Name the item CustomPropertyDesigner.</span></span>

2. <span data-ttu-id="4c3cd-121">Agregue un cuadro combinado al nuevo diseñador.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-121">Add a Combo Box to the new designer.</span></span> <span data-ttu-id="4c3cd-122">En la propiedad Items, agregue un par de elementos al cuadro combinado, con valores de "Item1" y "Item2" para Content.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-122">In the Items property, add a couple of items to the combo box, with Content values of "Item1" and 'Item2".</span></span>

3. <span data-ttu-id="4c3cd-123">Modifique el XAML del cuadro combinado para agregar el nuevo convertidor de elemento como el convertidor de elemento que se va a utilizar para el cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-123">Modify the XAML of the combo box to add the new item converter as the item converter to be used for the combo box.</span></span> <span data-ttu-id="4c3cd-124">El convertidor se agrega como un recurso en el segmento ActivityDesigner.Resources y especifica el convertidor en el atributo Converter para <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-124">The converter is added as a resource in the ActivityDesigner.Resources segment, and specifies the converter in the Converter attribute for the <xref:System.Windows.Controls.ComboBox>.</span></span> <span data-ttu-id="4c3cd-125">Observe que el espacio de nombres del proyecto se especifica en los atributos de espacios de nombres para el diseñador de actividad; si el diseñador se va a utilizar en un proyecto diferente, será necesario cambiar este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-125">Note that the namespace of the project is specified in the namespaces attributes for the activity designer; if the designer is to be used in a different project, this namespace will need to be changed.</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class="CustomProperty.CustomPropertyDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:c="clr-namespace:CustomProperty"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">

        <sap:ActivityDesigner.Resources>
            <ResourceDictionary>
                <c:ComboBoxItemConverter x:Key="comboBoxItemConverter"/>
            </ResourceDictionary>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ComboBox SelectedValue="{Binding Path=ModelItem.Text, Mode=TwoWay, Converter={StaticResource comboBoxItemConverter}}"  Height="23" HorizontalAlignment="Left" Margin="132,5,0,0" Name="comboBox1" VerticalAlignment="Top" Width="120" ItemsSource="{Binding}">
                <ComboBoxItem>item1</ComboBoxItem>
                <ComboBoxItem>item2</ComboBoxItem>
            </ComboBox>
        </Grid>
    </sap:ActivityDesigner>
    ```

4. <span data-ttu-id="4c3cd-126">Cree un nuevo elemento de tipo <xref:System.Activities.CodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-126">Create a new item of type <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="4c3cd-127">El código predeterminado creado por el IDE para la actividad será suficiente en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-127">The default code created by the IDE for the activity will be sufficient for this example.</span></span>

5. <span data-ttu-id="4c3cd-128">Agregue el atributo siguiente a la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="4c3cd-128">Add the following attribute to the class definition:</span></span>

    ```csharp
    [Designer(typeof(CustomPropertyDesigner))]
    ```

     <span data-ttu-id="4c3cd-129">Esta línea asocia el nuevo diseñador a la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-129">This line associates the new designer with the new class.</span></span>

 <span data-ttu-id="4c3cd-130">La nueva actividad debe estar asociada ahora al diseñador.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-130">The new activity should now be associated with the designer.</span></span> <span data-ttu-id="4c3cd-131">Para probar la nueva actividad, agréguela a un flujo de trabajo y establezca el cuadro combinado en los dos valores.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-131">To test the new activity, add it to a workflow, and set the combo box to the two values.</span></span> <span data-ttu-id="4c3cd-132">La ventana Propiedades debe actualizarse para reflejar el valor de cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="4c3cd-132">The properties window should update to reflect the combo box value.</span></span>
