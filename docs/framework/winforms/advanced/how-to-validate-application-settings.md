---
title: Procedimiento para validar la configuración de la aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
ms.openlocfilehash: e10bad5f746ae8777b9a7d4a65173b8abdeef00f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64636954"
---
# <a name="how-to-validate-application-settings"></a>Procedimiento para validar la configuración de la aplicación
En este tema se muestra cómo validar la configuración de la aplicación antes de conservarla.  
  
 Como la configuración de la aplicación está fuertemente tipada, tiene cierta confianza en que los usuarios no puedan asignar los datos de un tipo incorrecto a una configuración especificada. Sin embargo, aún es posible que un usuario intente asignar un valor a una configuración que se encuentre fuera de los límites aceptables (por ejemplo, proporcionar una fecha de nacimiento perteneciente al futuro). <xref:System.Configuration.ApplicationSettingsBase>, la clase primaria de todas las clases de configuración de la aplicación, expone cuatro eventos para habilitar la comprobación de esos límites. Al controlarse estos eventos, se incluye todo el código de validación en una sola ubicación, en lugar de dispersarse por todo el proyecto.  
  
 El evento que use depende de cuándo es necesario validar la configuración, como se describe en la siguiente tabla.  
  
|evento|Repetición y uso|  
|-----------|------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|Se produce después de la carga inicial de un grupo de propiedades de configuración.<br /><br /> Use este evento para validar los valores iniciales de todo el grupo de propiedades antes de que se utilicen dentro de la aplicación.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|Se produce antes de cambiarse el valor de una sola propiedad de configuración.<br /><br /> Use este evento para validar una sola propiedad antes de que se cambie. Puede proporcionar comentarios inmediatos a los usuarios relacionados con sus acciones y opciones.|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|Se produce después de cambiarse el valor de una sola propiedad de configuración.<br /><br /> Use este evento para validar una sola propiedad tras cambiarse. Este evento no suele utilizarse para la validación a menos que sea necesario un proceso de validación prolongado y asincrónico.|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|Se produce antes de almacenarse el grupo de propiedades de configuración.<br /><br /> Use este evento para validar los valores de todo el grupo de propiedades antes de que se conserven en el disco.|  
  
 Normalmente, no utilizará todos estos eventos dentro de la misma aplicación con fines de validación. Por ejemplo, a menudo es posible cumplir todos los requisitos de validación controlando solo el <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> eventos.  
  
 Un controlador de eventos suele realizar una de las siguientes acciones al detectar un valor no válido:  
  
- Proporciona automáticamente un valor conocido como correcto, como el valor predeterminado.  
  
- Vuelve a consultar al usuario del código de servidor para obtener información.  
  
- Para los eventos generados antes de sus acciones asociadas, como <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> y <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, usa el <xref:System.ComponentModel.CancelEventArgs> argumento para cancelar la operación.  
  
 Para más información sobre el control de eventos, consulte [Información general sobre controladores de eventos](../event-handlers-overview-windows-forms.md).  
  
 Los procedimientos siguientes muestran cómo probar una fecha de nacimiento válida mediante el <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> o <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> eventos. Los procedimientos se han escrito partiendo de la base de que ya ha creado la configuración de la aplicación; en este ejemplo, realizaremos una comprobación de los límites en un valor de configuración denominado `DateOfBirth`. Para obtener más información sobre la creación de configuración, vea [Cómo: Crear configuración de la aplicación](how-to-create-application-settings.md).  
  
### <a name="to-obtain-the-application-settings-object"></a>Para obtener el objeto de configuración de la aplicación  
  
- Obtenga una referencia al objeto de configuración de la aplicación (la instancia del contenedor) completando uno de los siguientes elementos con viñetas:  
  
    - Si ha creado la configuración con el cuadro de diálogo Visual Studio Application Settings (Configuración de la aplicación de Visual Studio) en el **Editor de propiedades**, puede recuperar el objeto de configuración predeterminado generado para su lenguaje a través de la siguiente expresión.  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         -o bien-  
  
    - Si es desarrollador de Visual Basic y ha creado la configuración de la aplicación mediante el Diseñador de proyectos, puede recuperar la configuración con [My.Settings (Objeto)](~/docs/visual-basic/language-reference/objects/my-settings-object.md).  
  
         -o bien-  
  
    - Si ha creado la configuración mediante la derivación de <xref:System.Configuration.ApplicationSettingsBase> directamente, deberá crear manualmente una instancia de la clase.  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 Los siguientes procedimientos se han escrito partiendo de la base de que el objeto de configuración de la aplicación se ha obtenido completando el último elemento con viñetas de este procedimiento.  
  
### <a name="to-validate-application-settings-when-a-setting-is-changing"></a>Para validar la configuración de la aplicación al cambiar un valor de configuración  
  
1. Si es un C# developer, en el formulario o un control `Load` evento, agregue un controlador de eventos para el <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> eventos.  
  
     -o bien-  
  
     Si es desarrollador de Visual Basic, debe declarar la variable `Settings` mediante la palabra clave `WithEvents`.  
  
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
  
2. Defina el controlador de eventos y escriba el código dentro de él para realizar una comprobación de los límites en la fecha de nacimiento.  
  
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
  
### <a name="to-validate-application-settings-when-a-save-occurs"></a>Para validar la configuración de la aplicación al guardar  
  
1. En el formulario o un control `Load` evento, agregue un controlador de eventos para el <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> eventos.  
  
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
  
2. Defina el controlador de eventos y escriba el código dentro de él para realizar una comprobación de los límites en la fecha de nacimiento.  
  
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
  
## <a name="see-also"></a>Vea también

- [Crear controladores de eventos en Windows Forms](../creating-event-handlers-in-windows-forms.md)
- [Cómo: Crear configuración de la aplicación](how-to-create-application-settings.md)
