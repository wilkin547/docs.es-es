---
title: "How to: Validate Application Settings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "validating application settings"
  - "application settings, Windows Forms"
  - "application settings, validating"
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# How to: Validate Application Settings
Este tema muestra cómo validar la configuración de la aplicación antes de guardarse.  
  
 Dado que la configuración de la aplicación está fuertemente tipada, puede confiar en que los usuarios no puedan asignar datos de un tipo incorrecto a una configuración determinada.  Sin embargo, un usuario podría intentar asignar un valor a un valor de configuración que se encuentre fuera de los límites aceptados, por ejemplo, proporcionar una fecha de nacimiento que se produzca en el futuro.  <xref:System.Configuration.ApplicationSettingsBase>, la clase primaria de todas las clases de configuración de la aplicación, expone cuatro eventos para habilitar la comprobación de estos límites.  Al controlar estos eventos se incluye todo el código de la validación en una ubicación única, en lugar de esparcirlo a lo largo del proyecto.  
  
 El evento que utilice depende del momento en que necesite validar la configuración, tal como se describe en la siguiente tabla.  
  
|Evento|Uso y frecuencia|  
|------------|----------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|Se produce después de la carga inicial de un grupo de propiedades de configuración.<br /><br /> Utilice este evento para validar los valores iniciales del grupo de propiedades completo antes de utilizarse dentro de la aplicación.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|Se produce antes de cambiar el valor de una propiedad de configuración única.<br /><br /> Utilice este evento para validar una propiedad única antes de modificarla.  Puede proporcionar comentarios inmediatos a los usuarios en relación con sus acciones y opciones.|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|Se produce después de cambiar el valor de una propiedad de configuración única.<br /><br /> Utilice este evento para validar una propiedad única después de modificarla.  Este evento raramente se utiliza para la validación a menos que se requiera un proceso de validación largo y asincrónico.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|Se produce antes de almacenar el grupo de propiedades de configuración.<br /><br /> Utilice este evento para validar los valores del grupo de propiedades completo antes de guardarlos en el disco.|  
  
 Normalmente, no utilizará todos estos eventos dentro de la misma aplicación con fines de validación.  Por ejemplo, a menudo es posible cumplir todos los requisitos de validación controlando sólo el evento <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>.  
  
 Un controlador de eventos generalmente realiza una de las acciones siguientes cuando detecta un valor no válido:  
  
-   Automáticamente proporciona un valor conocido como correcto, como el valor predeterminado.  
  
-   Vuelve a solicitar información al usuario del código del servidor.  
  
-   Para los eventos producidos antes de sus acciones asociadas, como <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> y <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, utiliza el argumento <xref:System.ComponentModel.CancelEventArgs> para cancelar la operación.  
  
 Para obtener más información sobre el control de eventos, vea [Event Handlers Overview](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 Los procedimientos siguientes muestran cómo probar con una fecha de nacimiento válida utilizando <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> o el evento <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>.  Los procedimientos se han escrito teniendo en cuenta que ya ha creado la configuración de la aplicación; en este ejemplo, se comprobarán los límites de un valor de configuración denominado  `DateOfBirth`.  Para obtener más información acerca de la creación de valores de configuración, vea [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
### Para obtener el objeto de configuración de la aplicación  
  
-   Obtenga una referencia al objeto \(la instancia del contenedor\) de configuración de la aplicación finalizando uno de los siguientes puntos:  
  
    -   Si ha creado un valor de configuración utilizando el cuadro de diálogo Configuración de la aplicación de Visual Studio del **Editor de propiedades**, puede recuperar el objeto de configuración de aplicación generado para su lenguaje mediante la expresión siguiente.  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         O bien  
  
    -   Si es desarrollador de Visual Basic y ha creado la configuración de la aplicación mediante el Diseñador de proyectos, puede recuperar los valores de configuración utilizando [My.Settings \(Objeto\)](../../../../ocs/visual-basic/language-reference/objects/my-settings-object.md).  
  
         O bien  
  
    -   Si ha creado los valores de configuración derivándolos directamente de <xref:System.Configuration.ApplicationSettingsBase>, necesita crear manualmente instancias de su clase.  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 Los procedimientos siguientes se escribieron suponiendo que el objeto de configuración de la aplicación se obtuvo finalizando el último punto de este procedimiento.  
  
### Para validar la configuración de la aplicación cuando se está modificando un valor de configuración  
  
1.  Si es desarrollador de C\#, en el formulario o el evento  `Load`  del control, agregue un controlador de eventos para el evento <xref:System.Configuration.ApplicationSettingsBase.SettingChanging>.  
  
     O bien  
  
     Si es desarrollador de Visual Basic, debería declarar la variable `Settings` mediante la palabra clave `WithEvents`.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingChanging += new SettingChangingEventHandler(MyCustomSettings_SettingChanging);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(sender as Object, e as EventArgs)  
        AddHandler settings.SettingChanging, AddressOf MyCustomSettings_SettingChanging  
    End Sub   
    ```  
  
2.  Defina el controlador de eventos y escriba el código dentro de él para realizar la comprobación de los límites de la fecha de nacimiento.  
  
    ```csharp  
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)  
    {  
        if (e.SettingName.Equals("DateOfBirth")) {  
            Date newDate = (Date)e.NewValue;  
            If (newDate > Date.Now) {  
                e.Cancel = true;  
                // Inform the user.  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingChanging(sender as Object, e as SettingChangingEventArgs) Handles Settings.SettingChanging  
        If (e.SettingName.Equals("DateOfBirth")) Then  
            Dim NewDate as Date = CType(e.NewValue, Date)  
            If (NewDate > Date.Now) Then  
                e.Cancel = True  
                ' Inform the user.  
            End If  
        End If  
    End Sub  
    ```  
  
### Para validar la configuración de la aplicación cuando se almacena  
  
1.  Agregue un controlador de eventos para el evento <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> en el formulario o el evento  `Load`  del control.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingsSaving += new SettingsSavingEventHandler(MyCustomSettings_SettingsSaving);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(Sender as Object, e as EventArgs)  
        AddHandler settings.SettingsSaving, AddressOf MyCustomSettings_SettingsSaving  
    End Sub  
    ```  
  
2.  Defina el controlador de eventos y escriba el código dentro de él para realizar la comprobación de los límites de la fecha de nacimiento.  
  
    ```csharp  
    private void MyCustomSettings_SettingsSaving(Object sender, SettingsSavingEventArgs e)  
    {  
        if (this["DateOfBirth"] > Date.Now) {  
            e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingsSaving(Sender as Object, e as SettingsSavingEventArgs)  
        If (Me["DateOfBirth"] > Date.Now) Then  
            e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## Vea también  
 [Creating Event Handlers in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)