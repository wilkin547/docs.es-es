---
title: "Cómo: Responder a los cambios de las combinaciones de fuentes en una aplicación de Windows Forms"
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
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aac8d56c87ff03b313565a3d04cd3f3cc4e85f72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="9ac5e-102">Cómo: Responder a los cambios de las combinaciones de fuentes en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ac5e-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="9ac5e-103">En los sistemas operativos de Windows, un usuario puede cambiar la configuración de fuente de todo el sistema para que la fuente predeterminada aparezca mayor o menor.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="9ac5e-104">Cambiar esta configuración de fuente es fundamental para personas con discapacidades visuales y requieren un tipo mayor leer el texto en las pantallas.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="9ac5e-105">Puede ajustar la aplicación de formularios Windows Forms para reaccionar a estos cambios aumentando o reduciendo el tamaño del formulario y de todo el texto cada vez que cambia la combinación de fuentes.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="9ac5e-106">Si desea que el formulario para adaptarse dinámicamente a cambios en los tamaños de fuente, puede agregar código al formulario.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="9ac5e-107">Normalmente, la fuente predeterminada utilizada por Windows Forms es la fuente devuelta por la <xref:Microsoft.Win32> llamada de espacio de nombres a `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="9ac5e-108">La fuente devuelta por esta llamada solo cambia cuando la resolución de pantalla.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="9ac5e-109">Como se muestra en el siguiente procedimiento, el código debe cambiar la fuente predeterminada para <xref:System.Drawing.SystemFonts.IconTitleFont%2A> para responder a cambios en el tamaño de fuente.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="9ac5e-110">Para usar la fuente del escritorio y responder a los cambios de esquema de fuentes</span><span class="sxs-lookup"><span data-stu-id="9ac5e-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="9ac5e-111">Crear el formulario y agregarle los controles que desee.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="9ac5e-112">Para obtener más información, consulte [Cómo: crear una aplicación de Windows Forms desde la línea de comandos](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) y [controles que se utilizan en formularios Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9ac5e-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="9ac5e-113">Agregue una referencia a la <xref:Microsoft.Win32> espacio de nombres en el código.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="9ac5e-114">Agregue el código siguiente al constructor del formulario que se va a enlazar controladores de eventos necesarios como cambiar la fuente predeterminada en uso para el formulario.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="9ac5e-115">Implemente un controlador para el <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> evento que hace que el formulario se ajuste automáticamente cuando el <xref:Microsoft.Win32.UserPreferenceCategory.Window> cambios de categoría.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="9ac5e-116">Por último, implemente un controlador para el <xref:System.Windows.Forms.Form.FormClosing> eventos que separa el <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ac5e-117">Si no se incluye este código hará que la aplicación a la pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  <span data-ttu-id="9ac5e-118">Compile y ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="9ac5e-119">Para cambiar manualmente la combinación de fuentes en Windows XP</span><span class="sxs-lookup"><span data-stu-id="9ac5e-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="9ac5e-120">Mientras se ejecuta la aplicación de formularios Windows Forms, haga clic en el escritorio de Windows y elija **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="9ac5e-121">En el **propiedades de presentación** cuadro de diálogo, haga clic en el **apariencia** ficha.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="9ac5e-122">Desde el **el tamaño de fuente** lista desplegable, seleccione un nuevo tamaño de fuente.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="9ac5e-123">Observará que ahora el formulario responde para ejecutar los cambios de tiempo en el esquema de la fuente del escritorio.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-123">You will notice that the form now reacts to run time changes in the desktop font scheme.</span></span> <span data-ttu-id="9ac5e-124">Cuando el usuario cambia entre **Normal**, **fuentes grandes**, y **fuentes muy grandes**, el formulario cambia la fuente y escala correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ac5e-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ac5e-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="9ac5e-126">El constructor de este ejemplo de código contiene una llamada a `InitializeComponent`, que se define cuando se crea un nuevo proyecto de formularios Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="9ac5e-127">Quite esta línea de código si va a compilar la aplicación en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9ac5e-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac5e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ac5e-128">See Also</span></span>  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [<span data-ttu-id="9ac5e-129">Ajuste automático de escala en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ac5e-129">Automatic Scaling in Windows Forms</span></span>](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
