---
title: "Cómo: Agregar controles ActiveX a formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9328400917208dde9f81b493fbf26c6080dc9c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="5bf24-102">Cómo: Agregar controles ActiveX a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bf24-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="5bf24-103">Aunque el Diseñador de Windows Forms está optimizado para hospedar controles de formularios Windows Forms, también puede colocar controles ActiveX en formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5bf24-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5bf24-104">Existen limitaciones de rendimiento de Windows Forms cuando se agregan controles ActiveX a ellos.</span><span class="sxs-lookup"><span data-stu-id="5bf24-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="5bf24-105">Antes de agregar controles ActiveX a un formulario, debe agregarlos al cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="5bf24-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="5bf24-106">Para obtener más información, consulte [componentes COM, cuadro de diálogo Personalizar cuadro de herramientas](http://msdn.microsoft.com/en-us/171333f3-f207-4e02-bbdc-17862556212c).</span><span class="sxs-lookup"><span data-stu-id="5bf24-106">For more information, see [COM Components, Customize Toolbox Dialog Box](http://msdn.microsoft.com/en-us/171333f3-f207-4e02-bbdc-17862556212c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bf24-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="5bf24-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5bf24-108">Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="5bf24-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5bf24-109">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5bf24-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="5bf24-110">Para agregar un control ActiveX a su formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bf24-110">To add an ActiveX control to your Windows Form</span></span>  
  
-   <span data-ttu-id="5bf24-111">Haga doble clic en el control en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="5bf24-111">Double-click the control on the Toolbox.</span></span>  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]<span data-ttu-id="5bf24-112">Agrega todas las referencias al control en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5bf24-112"> adds all references to the control in your project.</span></span> <span data-ttu-id="5bf24-113">Para obtener más información sobre los aspectos que debe tener en cuenta al utilizar controles ActiveX en formularios Windows Forms, vea [consideraciones al alojar un ActiveX Control en un formulario Windows Forms](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="5bf24-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bf24-114">El importador de controles de ActiveX de Windows Forms (AxImp.exe) crea argumentos de evento de un tipo diferente de lo esperado en las importaciones de bibliotecas de vínculos dinámicos de ActiveX.</span><span class="sxs-lookup"><span data-stu-id="5bf24-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="5bf24-115">Los argumentos creados por AxImp.exe son similares a lo siguiente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` se espera.</span><span class="sxs-lookup"><span data-stu-id="5bf24-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="5bf24-116">Tenga en cuenta que este irregularidades evita que el código funciona con normalidad.</span><span class="sxs-lookup"><span data-stu-id="5bf24-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="5bf24-117">Para obtener más información, consulte [importador de controles ActiveX de Windows Forms (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="5bf24-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf24-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bf24-118">See Also</span></span>  
 [<span data-ttu-id="5bf24-119">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bf24-119">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="5bf24-120">Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas</span><span class="sxs-lookup"><span data-stu-id="5bf24-120">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="5bf24-121">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bf24-121">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="5bf24-122">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bf24-122">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="5bf24-123">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="5bf24-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="5bf24-124">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bf24-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="5bf24-125">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="5bf24-125">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
