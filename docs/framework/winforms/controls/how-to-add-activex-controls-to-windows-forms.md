---
title: Agregar controles ActiveX a formularios
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 920c1111a5703352a4b624068e3d5ceae9892591
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746849"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="b6c82-102">Cómo: Agregar controles ActiveX a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b6c82-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="b6c82-103">Aunque el Diseñador de Windows Forms de Visual Studio está optimizado para hospedar controles de Windows Forms, también puede colocar controles ActiveX en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b6c82-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="b6c82-104">Existen limitaciones de rendimiento para Windows Forms cuando se agregan controles ActiveX a ellos.</span><span class="sxs-lookup"><span data-stu-id="b6c82-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="b6c82-105">Antes de agregar controles ActiveX al formulario, debe agregarlos al cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="b6c82-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="b6c82-106">Para obtener más información, vea [componentes com, cuadro de diálogo Personalizar cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b6c82-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="b6c82-107">Agregar un control ActiveX a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b6c82-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="b6c82-108">Para agregar un control ActiveX a Windows Forms, haga doble clic en el control en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="b6c82-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="b6c82-109">Visual Studio agrega todas las referencias al control en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6c82-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="b6c82-110">Para obtener más información sobre los aspectos que se deben tener en cuenta al utilizar controles ActiveX en Windows Forms, vea [consideraciones al hospedar un control ActiveX en Windows Forms](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="b6c82-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b6c82-111">El Windows Forms importador de controles ActiveX (AxImp. exe) crea argumentos de evento de un tipo diferente del esperado al importar las bibliotecas de vínculos dinámicos de ActiveX.</span><span class="sxs-lookup"><span data-stu-id="b6c82-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="b6c82-112">Los argumentos creados por AxImp. exe son similares a los siguientes: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando se espera `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`.</span><span class="sxs-lookup"><span data-stu-id="b6c82-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="b6c82-113">Tenga en cuenta que esta irregularidad no impide que el código funcione con normalidad.</span><span class="sxs-lookup"><span data-stu-id="b6c82-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="b6c82-114">Para obtener más información, vea [Windows Forms el importador de controles ActiveX (Aximp. exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="b6c82-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6c82-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6c82-115">See also</span></span>

- [<span data-ttu-id="b6c82-116">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b6c82-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="b6c82-117">[Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b6c82-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="b6c82-118">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b6c82-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="b6c82-119">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="b6c82-119">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="b6c82-120">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b6c82-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="b6c82-121">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="b6c82-121">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
