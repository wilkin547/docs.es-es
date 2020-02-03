---
title: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon
ms.date: 03/30/2017
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
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746249"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="f15fa-102">Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f15fa-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>

<span data-ttu-id="f15fa-103">El componente <xref:System.Windows.Forms.NotifyIcon> de Windows Forms muestra un solo icono en el área de notificación de estado de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="f15fa-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="f15fa-104">Para mostrar varios iconos en el área de estado, debe tener varios componentes <xref:System.Windows.Forms.NotifyIcon> en el formulario.</span><span class="sxs-lookup"><span data-stu-id="f15fa-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="f15fa-105">Para establecer el icono mostrado para un control, use la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="f15fa-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="f15fa-106">También puede escribir código en el controlador de eventos <xref:System.Windows.Forms.NotifyIcon.DoubleClick> para que algo ocurra cuando el usuario hace doble clic en el icono.</span><span class="sxs-lookup"><span data-stu-id="f15fa-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="f15fa-107">Por ejemplo, puede hacer que aparezca un cuadro de diálogo para que el usuario configure el proceso en segundo plano representado por el icono.</span><span class="sxs-lookup"><span data-stu-id="f15fa-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>

> [!NOTE]
> <span data-ttu-id="f15fa-108">El componente de <xref:System.Windows.Forms.NotifyIcon> se usa solo con fines informativos, para alertar a los usuarios de que se ha producido una acción o un evento o que ha habido un cambio en el estado de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="f15fa-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="f15fa-109">Debe usar menús, barras de herramientas y otros elementos de la interfaz de usuario para la interacción estándar con las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f15fa-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>

### <a name="to-set-the-icon"></a><span data-ttu-id="f15fa-110">Para establecer el icono</span><span class="sxs-lookup"><span data-stu-id="f15fa-110">To set the icon</span></span>

1. <span data-ttu-id="f15fa-111">Asigne un valor a la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="f15fa-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="f15fa-112">El valor debe ser de tipo `System.Drawing.Icon` y se puede cargar desde un archivo. ico.</span><span class="sxs-lookup"><span data-stu-id="f15fa-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="f15fa-113">Puede especificar el archivo de icono en el código o haciendo clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) del ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A> en la ventana **propiedades** y, a continuación, seleccionando el archivo en el cuadro de diálogo **abrir** que aparece.</span><span class="sxs-lookup"><span data-stu-id="f15fa-113">You can specify the icon file in code or by clicking the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>

2. <span data-ttu-id="f15fa-114">Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="f15fa-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>

3. <span data-ttu-id="f15fa-115">Establezca la propiedad <xref:System.Windows.Forms.NotifyIcon.Text%2A> en una cadena de información sobre herramientas adecuada.</span><span class="sxs-lookup"><span data-stu-id="f15fa-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>

     <span data-ttu-id="f15fa-116">En el ejemplo de código siguiente, la ruta de acceso establecida para la ubicación del icono es la carpeta **Mis documentos** .</span><span class="sxs-lookup"><span data-stu-id="f15fa-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="f15fa-117">Esta ubicación se usa porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="f15fa-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="f15fa-118">La elección de esta ubicación también permite a los usuarios con niveles de acceso mínimos del sistema ejecutar la aplicación de forma segura.</span><span class="sxs-lookup"><span data-stu-id="f15fa-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="f15fa-119">En el ejemplo siguiente se requiere un formulario con un control <xref:System.Windows.Forms.NotifyIcon> ya agregado.</span><span class="sxs-lookup"><span data-stu-id="f15fa-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="f15fa-120">También requiere un archivo de icono denominado `Icon.ico`.</span><span class="sxs-lookup"><span data-stu-id="f15fa-120">It also requires an icon file named `Icon.ico`.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f15fa-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f15fa-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="f15fa-122">Asociar un menú contextual con un componente NotifyIcon de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f15fa-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="f15fa-123">NotifyIcon (componente)</span><span class="sxs-lookup"><span data-stu-id="f15fa-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="f15fa-124">Información general sobre el componente NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="f15fa-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
