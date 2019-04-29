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
ms.openlocfilehash: b7aba4935756fc218a1fadaa1dd9f20a5bc3034f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778851"
---
# <a name="how-to-validate-application-settings"></a><span data-ttu-id="02424-102">Procedimiento para validar la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="02424-102">How to: Validate Application Settings</span></span>
<span data-ttu-id="02424-103">En este tema se muestra cómo validar la configuración de la aplicación antes de conservarla.</span><span class="sxs-lookup"><span data-stu-id="02424-103">This topic demonstrates how to validate application settings before they are persisted.</span></span>  
  
 <span data-ttu-id="02424-104">Como la configuración de la aplicación está fuertemente tipada, tiene cierta confianza en que los usuarios no puedan asignar los datos de un tipo incorrecto a una configuración especificada.</span><span class="sxs-lookup"><span data-stu-id="02424-104">Because application settings are strongly typed, you have some confidence that users cannot assign data of an incorrect type to a given setting.</span></span> <span data-ttu-id="02424-105">Sin embargo, aún es posible que un usuario intente asignar un valor a una configuración que se encuentre fuera de los límites aceptables (por ejemplo, proporcionar una fecha de nacimiento perteneciente al futuro).</span><span class="sxs-lookup"><span data-stu-id="02424-105">However, a user still may attempt to assign a value to a setting that falls outside of acceptable bounds—for example, supplying a birth date that occurs in the future.</span></span> <span data-ttu-id="02424-106"><xref:System.Configuration.ApplicationSettingsBase>, la clase primaria de todas las clases de configuración de la aplicación, expone cuatro eventos para habilitar la comprobación de esos límites.</span><span class="sxs-lookup"><span data-stu-id="02424-106"><xref:System.Configuration.ApplicationSettingsBase>, the parent class of all application settings classes, exposes four events to enable such bounds checking.</span></span> <span data-ttu-id="02424-107">Al controlarse estos eventos, se incluye todo el código de validación en una sola ubicación, en lugar de dispersarse por todo el proyecto.</span><span class="sxs-lookup"><span data-stu-id="02424-107">Handling these events puts all of your validation code in a single location, rather than scattering it throughout your project.</span></span>  
  
 <span data-ttu-id="02424-108">El evento que use depende de cuándo es necesario validar la configuración, como se describe en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="02424-108">The event you use depends upon when you need to validate your settings, as described in the following table.</span></span>  
  
|<span data-ttu-id="02424-109">evento</span><span class="sxs-lookup"><span data-stu-id="02424-109">Event</span></span>|<span data-ttu-id="02424-110">Repetición y uso</span><span class="sxs-lookup"><span data-stu-id="02424-110">Occurrence and use</span></span>|  
|-----------|------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|<span data-ttu-id="02424-111">Se produce después de la carga inicial de un grupo de propiedades de configuración.</span><span class="sxs-lookup"><span data-stu-id="02424-111">Occurs after the initial loading of a settings property group.</span></span><br /><br /> <span data-ttu-id="02424-112">Use este evento para validar los valores iniciales de todo el grupo de propiedades antes de que se utilicen dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02424-112">Use this event to validate initial values for the entire property group before they are used within the application.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|<span data-ttu-id="02424-113">Se produce antes de cambiarse el valor de una sola propiedad de configuración.</span><span class="sxs-lookup"><span data-stu-id="02424-113">Occurs before the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="02424-114">Use este evento para validar una sola propiedad antes de que se cambie.</span><span class="sxs-lookup"><span data-stu-id="02424-114">Use this event to validate a single property before it is changed.</span></span> <span data-ttu-id="02424-115">Puede proporcionar comentarios inmediatos a los usuarios relacionados con sus acciones y opciones.</span><span class="sxs-lookup"><span data-stu-id="02424-115">It can provide immediate feedback to users regarding their actions and choices.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|<span data-ttu-id="02424-116">Se produce después de cambiarse el valor de una sola propiedad de configuración.</span><span class="sxs-lookup"><span data-stu-id="02424-116">Occurs after the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="02424-117">Use este evento para validar una sola propiedad tras cambiarse.</span><span class="sxs-lookup"><span data-stu-id="02424-117">Use this event to validate a single property after it is changed.</span></span> <span data-ttu-id="02424-118">Este evento no suele utilizarse para la validación a menos que sea necesario un proceso de validación prolongado y asincrónico.</span><span class="sxs-lookup"><span data-stu-id="02424-118">This event is rarely used for validation unless a lengthy, asynchronous validation process is required.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|<span data-ttu-id="02424-119">Se produce antes de almacenarse el grupo de propiedades de configuración.</span><span class="sxs-lookup"><span data-stu-id="02424-119">Occurs before the settings property group is stored.</span></span><br /><br /> <span data-ttu-id="02424-120">Use este evento para validar los valores de todo el grupo de propiedades antes de que se conserven en el disco.</span><span class="sxs-lookup"><span data-stu-id="02424-120">Use this event to validate values for the entire property group before they are persisted to disk.</span></span>|  
  
 <span data-ttu-id="02424-121">Normalmente, no utilizará todos estos eventos dentro de la misma aplicación con fines de validación.</span><span class="sxs-lookup"><span data-stu-id="02424-121">Typically, you will not use all of these events within the same application for validation purposes.</span></span> <span data-ttu-id="02424-122">Por ejemplo, a menudo es posible cumplir todos los requisitos de validación controlando solo el <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> eventos.</span><span class="sxs-lookup"><span data-stu-id="02424-122">For example, it is often possible to fulfill all validation requirements by handling only the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
 <span data-ttu-id="02424-123">Un controlador de eventos suele realizar una de las siguientes acciones al detectar un valor no válido:</span><span class="sxs-lookup"><span data-stu-id="02424-123">An event handler generally performs one of the following actions when it detects an invalid value:</span></span>  
  
- <span data-ttu-id="02424-124">Proporciona automáticamente un valor conocido como correcto, como el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="02424-124">Automatically supplies a value known to be correct, such as the default value.</span></span>  
  
- <span data-ttu-id="02424-125">Vuelve a consultar al usuario del código de servidor para obtener información.</span><span class="sxs-lookup"><span data-stu-id="02424-125">Re-queries the user of server code for information.</span></span>  
  
- <span data-ttu-id="02424-126">Para los eventos generados antes de sus acciones asociadas, como <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> y <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, usa el <xref:System.ComponentModel.CancelEventArgs> argumento para cancelar la operación.</span><span class="sxs-lookup"><span data-stu-id="02424-126">For events raised before their associated actions, such as <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> and <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, uses the <xref:System.ComponentModel.CancelEventArgs> argument to cancel the operation.</span></span>  
  
 <span data-ttu-id="02424-127">Para más información sobre el control de eventos, consulte [Información general sobre controladores de eventos](../event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="02424-127">For more information about event handling, see [Event Handlers Overview](../event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="02424-128">Los procedimientos siguientes muestran cómo probar una fecha de nacimiento válida mediante el <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> o <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> eventos.</span><span class="sxs-lookup"><span data-stu-id="02424-128">The following procedures show how to test for a valid birth date using either the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> or the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span> <span data-ttu-id="02424-129">Los procedimientos se han escrito partiendo de la base de que ya ha creado la configuración de la aplicación; en este ejemplo, realizaremos una comprobación de los límites en un valor de configuración denominado `DateOfBirth`.</span><span class="sxs-lookup"><span data-stu-id="02424-129">The procedures were written under the assumption that you have already created your application settings; in this example, we will perform bounds checking on a setting named `DateOfBirth`.</span></span> <span data-ttu-id="02424-130">Para obtener más información sobre la creación de configuración, vea [Cómo: Crear configuración de la aplicación](how-to-create-application-settings.md).</span><span class="sxs-lookup"><span data-stu-id="02424-130">For more information about creating settings, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>  
  
### <a name="to-obtain-the-application-settings-object"></a><span data-ttu-id="02424-131">Para obtener el objeto de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="02424-131">To obtain the application settings object</span></span>  
  
- <span data-ttu-id="02424-132">Obtenga una referencia al objeto de configuración de la aplicación (la instancia del contenedor) completando uno de los siguientes elementos con viñetas:</span><span class="sxs-lookup"><span data-stu-id="02424-132">Obtain a reference to the application settings object (the wrapper instance) by completing one of the following bulleted items:</span></span>  
  
    - <span data-ttu-id="02424-133">Si ha creado la configuración con el cuadro de diálogo Visual Studio Application Settings (Configuración de la aplicación de Visual Studio) en el **Editor de propiedades**, puede recuperar el objeto de configuración predeterminado generado para su lenguaje a través de la siguiente expresión.</span><span class="sxs-lookup"><span data-stu-id="02424-133">If you created your settings using the Visual Studio Application Settings dialog box in the **Property Editor**, you can retrieve the default settings object generated for your language through the following expression.</span></span>  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         <span data-ttu-id="02424-134">-o bien-</span><span class="sxs-lookup"><span data-stu-id="02424-134">-or-</span></span>  
  
    - <span data-ttu-id="02424-135">Si es desarrollador de Visual Basic y ha creado la configuración de la aplicación mediante el Diseñador de proyectos, puede recuperar la configuración con [My.Settings (Objeto)](~/docs/visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="02424-135">If you are a Visual Basic developer and you created your application settings using the Project Designer, you can retrieve your settings by using the [My.Settings Object](~/docs/visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
         <span data-ttu-id="02424-136">-o bien-</span><span class="sxs-lookup"><span data-stu-id="02424-136">-or-</span></span>  
  
    - <span data-ttu-id="02424-137">Si ha creado la configuración mediante la derivación de <xref:System.Configuration.ApplicationSettingsBase> directamente, deberá crear manualmente una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="02424-137">If you created your settings by deriving from <xref:System.Configuration.ApplicationSettingsBase> directly, you need to instantiate your class manually.</span></span>  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 <span data-ttu-id="02424-138">Los siguientes procedimientos se han escrito partiendo de la base de que el objeto de configuración de la aplicación se ha obtenido completando el último elemento con viñetas de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="02424-138">The following procedures were written under the assumption that the application settings object was obtained by completing the last bulleted item in this procedure.</span></span>  
  
### <a name="to-validate-application-settings-when-a-setting-is-changing"></a><span data-ttu-id="02424-139">Para validar la configuración de la aplicación al cambiar un valor de configuración</span><span class="sxs-lookup"><span data-stu-id="02424-139">To validate Application Settings when a setting is changing</span></span>  
  
1. <span data-ttu-id="02424-140">Si es un C# developer, en el formulario o un control `Load` evento, agregue un controlador de eventos para el <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> eventos.</span><span class="sxs-lookup"><span data-stu-id="02424-140">If you are a C# developer, in your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
     <span data-ttu-id="02424-141">-o bien-</span><span class="sxs-lookup"><span data-stu-id="02424-141">-or-</span></span>  
  
     <span data-ttu-id="02424-142">Si es desarrollador de Visual Basic, debe declarar la variable `Settings` mediante la palabra clave `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="02424-142">If you are a Visual Basic developer, you should declare the `Settings` variable using the `WithEvents` keyword.</span></span>  
  
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
  
2. <span data-ttu-id="02424-143">Defina el controlador de eventos y escriba el código dentro de él para realizar una comprobación de los límites en la fecha de nacimiento.</span><span class="sxs-lookup"><span data-stu-id="02424-143">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
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
  
### <a name="to-validate-application-settings-when-a-save-occurs"></a><span data-ttu-id="02424-144">Para validar la configuración de la aplicación al guardar</span><span class="sxs-lookup"><span data-stu-id="02424-144">To validate Application Settings when a Save occurs</span></span>  
  
1. <span data-ttu-id="02424-145">En el formulario o un control `Load` evento, agregue un controlador de eventos para el <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> eventos.</span><span class="sxs-lookup"><span data-stu-id="02424-145">In your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span>  
  
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
  
2. <span data-ttu-id="02424-146">Defina el controlador de eventos y escriba el código dentro de él para realizar una comprobación de los límites en la fecha de nacimiento.</span><span class="sxs-lookup"><span data-stu-id="02424-146">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02424-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="02424-147">See also</span></span>

- [<span data-ttu-id="02424-148">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02424-148">Creating Event Handlers in Windows Forms</span></span>](../creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="02424-149">Cómo: Crear configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="02424-149">How to: Create Application Settings</span></span>](how-to-create-application-settings.md)
