---
title: Responder a los cambios en el esquema de fuentes en una aplicación Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739227"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="d3ae6-102">Cómo: Responder a los cambios de las combinaciones de fuentes en una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3ae6-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="d3ae6-103">En los sistemas operativos de Windows, un usuario puede cambiar la configuración de fuentes para todo el sistema para que la fuente predeterminada aparezca más grande o más pequeña.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="d3ae6-104">Cambiar estos valores de fuente es fundamental para los usuarios que tienen discapacidades visuales y requieren un tipo mayor para leer el texto de las pantallas.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="d3ae6-105">Puede ajustar la aplicación Windows Forms para reaccionar a estos cambios aumentando o reduciendo el tamaño del formulario y todo el texto que contenga cada vez que cambie la combinación de fuentes.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="d3ae6-106">Si desea que el formulario contenga los cambios en los tamaños de fuente dinámicamente, puede agregar código al formulario.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="d3ae6-107">Normalmente, la fuente predeterminada usada por Windows Forms es la fuente devuelta por la llamada del espacio de nombres <xref:Microsoft.Win32> a `GetStockObject(DEFAULT_GUI_FONT)`.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="d3ae6-108">La fuente devuelta por esta llamada solo cambia cuando cambia la resolución de pantalla.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="d3ae6-109">Como se muestra en el siguiente procedimiento, el código debe cambiar la fuente predeterminada a <xref:System.Drawing.SystemFonts.IconTitleFont%2A> para responder a los cambios en el tamaño de fuente.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="d3ae6-110">Para usar la fuente de escritorio y responder a los cambios de la combinación de fuentes</span><span class="sxs-lookup"><span data-stu-id="d3ae6-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1. <span data-ttu-id="d3ae6-111">Cree el formulario y agregue los controles que desee.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="d3ae6-112">Para obtener más información, consulte [Cómo: crear una aplicación Windows Forms desde la línea de comandos](how-to-create-a-windows-forms-application-from-the-command-line.md) y [controles que se usarán en Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d3ae6-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="d3ae6-113">Agregue una referencia al espacio de nombres <xref:Microsoft.Win32> al código.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="d3ae6-114">Agregue el código siguiente al constructor del formulario para enlazar los controladores de eventos necesarios y para cambiar la fuente predeterminada en uso para el formulario.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="d3ae6-115">Implemente un controlador para el evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> que hace que el formulario se escale automáticamente cuando cambie la categoría <xref:Microsoft.Win32.UserPreferenceCategory.Window>.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. <span data-ttu-id="d3ae6-116">Por último, implemente un controlador para el evento <xref:System.Windows.Forms.Form.FormClosing> que desasocie el controlador de eventos <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="d3ae6-117">Si no se incluye este código, la aplicación perderá memoria.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. <span data-ttu-id="d3ae6-118">Compile y ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="d3ae6-119">Para cambiar manualmente la combinación de fuentes en Windows XP</span><span class="sxs-lookup"><span data-stu-id="d3ae6-119">To manually change the font scheme in Windows XP</span></span>  
  
1. <span data-ttu-id="d3ae6-120">Mientras se ejecuta la aplicación Windows Forms, haga clic con el botón secundario en el escritorio de Windows y elija **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="d3ae6-121">En el cuadro de diálogo **propiedades de pantalla** , haga clic en la pestaña **apariencia** .</span><span class="sxs-lookup"><span data-stu-id="d3ae6-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3. <span data-ttu-id="d3ae6-122">En el cuadro de lista desplegable **tamaño de fuente** , seleccione un nuevo tamaño de fuente.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="d3ae6-123">Observará que el formulario ahora reacciona a los cambios en tiempo de ejecución en el esquema de fuentes del escritorio.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="d3ae6-124">Cuando el usuario cambia entre fuentes **normales**, **grandes**y **fuentes extra grandes**, el formulario cambia la fuente y se escala correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3ae6-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3ae6-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="d3ae6-126">El constructor de este ejemplo de código contiene una llamada a `InitializeComponent`, que se define al crear un nuevo proyecto de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-126">The constructor in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="d3ae6-127">Quite esta línea de código si va a compilar la aplicación en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d3ae6-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ae6-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3ae6-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="d3ae6-129">Ajuste automático de escala en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3ae6-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
