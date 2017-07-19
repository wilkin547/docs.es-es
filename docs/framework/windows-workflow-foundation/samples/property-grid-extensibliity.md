---
title: "Extensibilidad de la cuadr&#237;cula de propiedades | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Extensibilidad de la cuadr&#237;cula de propiedades
Un desarrollador puede personalizar la cuadrícula de propiedad que se muestra cuando una actividad determinada se selecciona dentro del diseñador.Esto se puede hacer para crear una experiencia de edición enriquecida.En este ejemplo se muestra cómo llevarlo a cabo.  
  
## Demostraciones  
 Extensibilidad de la cuadrícula de propiedad del diseñador de flujo de trabajo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`  
  
## Análisis  
 Para ampliar la cuadrícula de propiedad, un desarrollador dispone de opciones para personalizar el aspecto alineado de un editor de cuadrícula de propiedad o para proporcionar un cuadro de diálogo que aparece para una superficie de edición más avanzada.En este ejemplo se muestran dos editores diferentes; un editor alineado y un editor de cuadro de diálogo.  
  
## Editor alineado  
 En el ejemplo del editor alineado se muestra lo siguiente:  
  
-   Crea un tipo que deriva de <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.  
  
-   En el constructor, el valor <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> se establece con una plantilla de datos de [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)].Se puede enlazar a una plantilla XAML, pero en este ejemplo, se utiliza código para inicializar el enlace de datos.  
  
-   La plantilla de datos tiene un contexto de datos de <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> del elemento presentado en la cuadrícula de propiedad.Observe en el siguiente código \(de CustomInlineEditor.cs\) que este contexto enlaza a la propiedad `Value`.  
  
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
  
## Editor de cuadros de diálogo  
 En el ejemplo del editor de cuadros de diálogo se muestra lo siguiente:  
  
1.  Crea un tipo que deriva de <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.  
  
2.  Establece el valor <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> en el constructor con una plantilla de datos de [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)].Se puede crear en XAML, pero en este ejemplo se crea en código.  
  
3.  La plantilla de datos tiene un contexto de datos de <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> del elemento presentado en la cuadrícula de propiedad.En el siguiente código, a continuación se enlaza a la propiedad `Value`.Es importante incluir también una clase <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> para proporcionar el botón que muestra el cuadro de diálogo en FilePickerEditor.cs.  
  
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
  
4.  Invalida el método <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A> en el tipo de diseñador para administrar la presentación del cuadro de diálogo.En este ejemplo, se muestra un objeto <xref:System.Windows.Forms.FileDialog> básico.  
  
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
  
## Para configurar, compilar y ejecutar el ejemplo  
  
1.  Compile la solución y, a continuación, abra Workflow1.xaml.  
  
2.  Arrastre **SimpleCodeActivity** del cuadro de herramientas al lienzo del diseñador.  
  
3.  Haga clic en **SimpleCodeActivity** y a continuación, abra la cuadrícula de propiedad donde hay un control deslizante y un control de selección de archivo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`