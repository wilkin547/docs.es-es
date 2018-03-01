---
title: "Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d795df8e8b514345632491fd6afdd618c2f18ec2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="bb4f2-102">Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb4f2-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="bb4f2-103">Los formularios de Windows <xref:System.Windows.Forms.NotifyIcon> componente muestra un único icono en el área de notificación de estado de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="bb4f2-104">Para mostrar múltiples iconos en el área de estado, debe tener varios <xref:System.Windows.Forms.NotifyIcon> componentes en el formulario.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="bb4f2-105">Para establecer el icono que se muestra para un control, utilice la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="bb4f2-106">También puede escribir código en el <xref:System.Windows.Forms.NotifyIcon.DoubleClick> controlador de eventos para que algo se produce cuando el usuario hace doble clic en el icono.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="bb4f2-107">Por ejemplo, podría realizar un cuadro de diálogo aparece para que el usuario configurar el proceso en segundo plano representado por el icono.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb4f2-108">El <xref:System.Windows.Forms.NotifyIcon> componente se utiliza solo, con fines de notificación para avisar a los usuarios que se ha producido una acción o un evento o se ha producido un cambio en el estado de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="bb4f2-109">Debe usar los menús, barras de herramientas y otros elementos de interfaz de usuario para la interacción estándar con las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="bb4f2-110">Para establecer el icono</span><span class="sxs-lookup"><span data-stu-id="bb4f2-110">To set the icon</span></span>  
  
1.  <span data-ttu-id="bb4f2-111">Asignar un valor a la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="bb4f2-112">El valor debe ser de tipo `System.Drawing.Icon` y se pueda cargar desde un archivo .ico.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="bb4f2-113">Puede especificar el archivo de icono en el código o haciendo clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.NotifyIcon.Icon%2A> propiedad en el  **Propiedades** ventana y, a continuación, seleccione el archivo en el **abiertos** cuadro de diálogo que aparece.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2.  <span data-ttu-id="bb4f2-114">Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="bb4f2-115">Establecer el <xref:System.Windows.Forms.NotifyIcon.Text%2A> propiedad a una cadena adecuada de la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="bb4f2-116">En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación del icono es la **Mis documentos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="bb4f2-117">Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos ejecutan el sistema operativo Windows incluirá esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="bb4f2-118">Al elegir esta ubicación también permite a los usuarios con niveles de acceso de sistema mínimos ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="bb4f2-119">En el ejemplo siguiente, se requiere un formulario con un <xref:System.Windows.Forms.NotifyIcon> control ya se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="bb4f2-120">También requiere un archivo de icono denominado `Icon.ico`.</span><span class="sxs-lookup"><span data-stu-id="bb4f2-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bb4f2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb4f2-121">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="bb4f2-122">Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb4f2-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [<span data-ttu-id="bb4f2-123">NotifyIcon (componente)</span><span class="sxs-lookup"><span data-stu-id="bb4f2-123">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="bb4f2-124">Información general sobre el componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="bb4f2-124">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
