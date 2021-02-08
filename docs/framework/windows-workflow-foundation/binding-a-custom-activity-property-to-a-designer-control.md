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
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a>Enlazar una propiedad de actividad personalizada a un control de diseñador

La operación de enlazar un control de diseñador de cuadro de texto a un argumento de actividad es bastante sencillo; sin embargo, la operación de enlazar un control de diseñador complejo (como un cuadro combinado) a un argumento de actividad puede presentar desafíos. En este tema se analiza la forma de enlazar un argumento de actividad a un control de cuadro combinado en un diseñador de actividad personalizado.

## <a name="creating-the-combo-box-item-converter"></a>Crear el convertidor de elemento de cuadro combinado

1. Cree una nueva solución vacía en Visual Studio denominada CustomProperty.

2. Cree una nueva clase denominada ComboBoxItemConverter. Agregue una referencia a System.Windows.Data y haga que la clase derive de <xref:System.Windows.Data.IValueConverter>. Haga que Visual Studio implemente la interfaz para generar códigos auxiliares para `Convert` y `ConvertBack`.

3. Agregue el siguiente código al método `Convert`. Este código convierte el <xref:System.Activities.InArgument%601> de tipo <xref:System.String> de la actividad en el valor que se va a colocar en el diseñador.

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

     La expresión del fragmento de código anterior también se pueden crear mediante <xref:Microsoft.CSharp.Activities.CSharpValue%601> en lugar de <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.

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

4. Agregue el siguiente código al método `ConvertBack`. Este código vuelve a convertir el elemento de cuadro combinado de entrada en un <xref:System.Activities.InArgument%601>.

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(vbArgument);
                return inArgument;
    ```

     La expresión del fragmento de código anterior también se pueden crear mediante <xref:Microsoft.CSharp.Activities.CSharpValue%601> en lugar de <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(csArgument);
                return inArgument;
    ```

## <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a>Agregar ComboBoxItemConverter al diseñador personalizado de una actividad

1. Agregue un nuevo elemento al proyecto. En el cuadro de diálogo Nuevo elemento, seleccione el nodo de flujo de trabajo y seleccione Diseñador de actividad como tipo del nuevo elemento. Asigne al elemento el nombre CustomPropertyDesigner.

2. Agregue un cuadro combinado al nuevo diseñador. En la propiedad Items, agregue un par de elementos al cuadro combinado, con valores de "Item1" y "Item2" para Content.

3. Modifique el XAML del cuadro combinado para agregar el nuevo convertidor de elemento como el convertidor de elemento que se va a utilizar para el cuadro combinado. El convertidor se agrega como un recurso en el segmento ActivityDesigner.Resources y especifica el convertidor en el atributo Converter para <xref:System.Windows.Controls.ComboBox>. Observe que el espacio de nombres del proyecto se especifica en los atributos de espacios de nombres para el diseñador de actividad; si el diseñador se va a utilizar en un proyecto diferente, será necesario cambiar este espacio de nombres.

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

4. Cree un nuevo elemento de tipo <xref:System.Activities.CodeActivity>. El código predeterminado creado por el IDE para la actividad será suficiente en este ejemplo.

5. Agregue el atributo siguiente a la definición de clase:

    ```csharp
    [Designer(typeof(CustomPropertyDesigner))]
    ```

     Esta línea asocia el nuevo diseñador a la nueva clase.

 La nueva actividad debe estar asociada ahora al diseñador. Para probar la nueva actividad, agréguela a un flujo de trabajo y establezca el cuadro combinado en los dos valores. La ventana Propiedades debe actualizarse para reflejar el valor de cuadro combinado.
