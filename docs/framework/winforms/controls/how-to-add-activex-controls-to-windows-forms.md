---
title: Procedimiento para agregar controles ActiveX a formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 780411949c543a2178de5e7c531bd2202703f27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011159"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="7bbd7-102">Procedimiento para agregar controles ActiveX a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bbd7-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="7bbd7-103">Aunque el Diseñador de Windows Forms está optimizado para hospedar controles de Windows Forms, también puede colocar controles ActiveX en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7bbd7-104">Existen limitaciones de rendimiento de Windows Forms cuando se agregan controles ActiveX a ellos.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="7bbd7-105">Antes de agregar controles ActiveX a un formulario, debe agregarlos al cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="7bbd7-106">Para obtener más información, consulte [componentes COM, Personalizar cuadro de diálogo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7bbd7-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bbd7-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7bbd7-108">Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="7bbd7-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7bbd7-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="7bbd7-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="7bbd7-110">Para agregar un control ActiveX a un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="7bbd7-110">To add an ActiveX control to your Windows Form</span></span>  
  
- <span data-ttu-id="7bbd7-111">Haga doble clic en el control en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-111">Double-click the control on the Toolbox.</span></span>  
  
     <span data-ttu-id="7bbd7-112">Visual Studio agrega todas las referencias al control en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-112">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="7bbd7-113">Para obtener más información acerca de las cosas a tener en cuenta al usar controles ActiveX en Windows Forms, consulte [consideraciones al hospedar un ActiveX Control en un formulario de Windows](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd7-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7bbd7-114">El importador de controles de ActiveX de Windows Forms (AxImp.exe) crea argumentos de evento de un tipo diferente del esperado en las importaciones de bibliotecas de vínculos dinámicos de ActiveX.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="7bbd7-115">Los argumentos creados por AxImp.exe son similares a lo siguiente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` se espera.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="7bbd7-116">Tenga en cuenta que este irregularidad no evita que código funciona con normalidad.</span><span class="sxs-lookup"><span data-stu-id="7bbd7-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="7bbd7-117">Para obtener más información, consulte [importador de controles ActiveX de Windows Forms (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd7-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bbd7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bbd7-118">See also</span></span>

- [<span data-ttu-id="7bbd7-119">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bbd7-119">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="7bbd7-120">[Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7bbd7-120">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="7bbd7-121">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bbd7-121">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="7bbd7-122">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bbd7-122">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="7bbd7-123">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="7bbd7-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="7bbd7-124">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bbd7-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="7bbd7-125">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="7bbd7-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
