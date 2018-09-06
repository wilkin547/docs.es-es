---
title: Extensibilidad de la cuadrícula de propiedades
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: b7c3e3dbc3ccd95fc12dffd40927b3e2bbbc8226
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779304"
---
# <a name="property-grid-extensibliity"></a>Extensibilidad de la cuadrícula de propiedades
Un desarrollador puede personalizar la cuadrícula de propiedad que se muestra cuando una actividad determinada se selecciona dentro del diseñador. Esto se puede hacer para crear una experiencia de edición enriquecida. En este ejemplo se muestra cómo llevarlo a cabo.  
  
## <a name="demonstrates"></a>Demostraciones  
 Extensibilidad de la cuadrícula de propiedad del diseñador de flujo de trabajo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`  
  
## <a name="discussion"></a>Explicación  
 Para ampliar la cuadrícula de propiedad, un desarrollador dispone de opciones para personalizar el aspecto alineado de un editor de cuadrícula de propiedad o para proporcionar un cuadro de diálogo que aparece para una superficie de edición más avanzada. En este ejemplo se muestran dos editores diferentes; un editor alineado y un editor de cuadro de diálogo.  
  
## <a name="inline-editor"></a>Editor alineado  
 En el ejemplo del editor alineado se muestra lo siguiente:  
  
-   Crea un tipo que deriva de <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.  
  
-   En el constructor, el <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> valor se establece con una plantilla de datos de Windows Presentation Foundation (WPF). Se puede enlazar a una plantilla XAML, pero en este ejemplo, se utiliza código para inicializar el enlace de datos.  
  
-   La plantilla de datos tiene un contexto de datos de <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> del elemento presentado en la cuadrícula de propiedad. Observe en el siguiente código (de CustomInlineEditor.cs) que este contexto enlaza a la propiedad `Value`.  
  
    ```csharp  
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));  
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));  
    Binding sliderBinding = new Binding("Value");  
    sliderBinding.Mode = BindingMode.TwoWay;  
    slider.SetValue(Slider.MinimumProperty, 0.0);  
    slider.SetValue(Slider.MaximumProperty, 100.0);  
    slider.SetValue(Slider.ValueProperty, sliderBinding);  
    stack.AppendChild(slider);  
    ```  
  
-   Dado que la actividad y el diseñador se encuentran en el mismo ensamblado, el registro de los atributos del diseñador de actividad se realiza en el constructor estático de la propia actividad, tal como se muestra en el siguiente ejemplo de SimpleCodeActivity.cs.  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="dialog-editor"></a>Editor de cuadros de diálogo  
 En el ejemplo del editor de cuadros de diálogo se muestra lo siguiente:  
  
1.  Crea un tipo que deriva de <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.  
  
2.  Establece el valor <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> en el constructor con una plantilla de datos de [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]. Se puede crear en XAML, pero en este ejemplo se crea en código.  
  
3.  La plantilla de datos tiene un contexto de datos de <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> del elemento presentado en la cuadrícula de propiedad. En el siguiente código, a continuación se enlaza a la propiedad `Value`. Es importante incluir también una clase <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> para proporcionar el botón que muestra el cuadro de diálogo en FilePickerEditor.cs.  
  
    ```  
    this.InlineEditorTemplate = new DataTemplate();  
  
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));  
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);  
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));  
    Binding labelBinding = new Binding("Value");  
    label.SetValue(Label.ContentProperty, labelBinding);  
    label.SetValue(Label.MaxWidthProperty, 90.0);  
  
    stack.AppendChild(label);  
  
    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));  
  
    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);  
  
    stack.AppendChild(editModeSwitch);  
  
    this.InlineEditorTemplate.VisualTree = stack;  
    ```  
  
4.  Invalida el <!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>--> `Microsoft.Windows.Design.PropertyEditing.ShowDialog` método en el tipo de diseñador para controlar la presentación del cuadro de diálogo. En este ejemplo, se muestra un objeto <xref:System.Windows.Forms.FileDialog> básico.  
  
    ```  
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)  
    {  
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();  
        if (ofd.ShowDialog() == true)  
        {  
            propertyValue.Value = ofd.FileName;  
        }  
    }  
    ```  
  
5.  Dado que la actividad y el diseñador se encuentran en el mismo ensamblado, el registro de los atributos del diseñador de actividad se realiza en el constructor estático de la propia actividad, tal como se muestra en el siguiente ejemplo de SimpleCodeActivity.cs.  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Compile la solución y, a continuación, abra Workflow1.xaml.  
  
2.  Arrastre un **SimpleCodeActivity** desde el cuadro de herramientas al lienzo del diseñador.  
  
3.  Haga clic en el **SimpleCodeActivity** y, a continuación, abra la cuadrícula de propiedades donde hay un control deslizante y un archivo de control de selección.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
