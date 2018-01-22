---
title: "Cómo: Organizar controles con las líneas de ajuste y la cuadrícula en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 166ccba959bd9facb8e24d580d47577a0c8746a8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="c1c01-102">Cómo: Organizar controles con las líneas de ajuste y la cuadrícula en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1c01-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="c1c01-103">Uso de las características de diseño de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], puede dirigir con precisión donde se colocan los controles en un formulario.</span><span class="sxs-lookup"><span data-stu-id="c1c01-103">Using the layout features of [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="c1c01-104">Controles agregada a un formulario o se desplaza en un formulario se pueden alinear automáticamente a las filas y columnas de cuadrícula del Diseñador de Windows Forms, o puede alinear controles mediante la característica de las guías de alineación.</span><span class="sxs-lookup"><span data-stu-id="c1c01-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1c01-105">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="c1c01-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c1c01-106">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="c1c01-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c1c01-107">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c1c01-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="c1c01-108">Para ajustar todos los controles a la cuadrícula</span><span class="sxs-lookup"><span data-stu-id="c1c01-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="c1c01-109">Seleccione el **SnapToGrid** modo de diseño en el Diseñador de Windows Forms **opciones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c1c01-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="c1c01-110">Para obtener más información, consulte [General, el Diseñador de Windows Forms, el cuadro de diálogo Opciones](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span><span class="sxs-lookup"><span data-stu-id="c1c01-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span></span> <span data-ttu-id="c1c01-111">Todos los controles ahora se alinearán a lo largo de los puntos de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="c1c01-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="c1c01-112">Puede ajustar controles individuales a la cuadrícula bloqueando en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c1c01-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="c1c01-113">Sin embargo, mientras estén bloqueados, no no se pueden mover ni cambiar de tamaño.</span><span class="sxs-lookup"><span data-stu-id="c1c01-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="c1c01-114">Para obtener más información acerca de los controles de bloqueos, vea [Cómo: bloquear controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c1c01-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="c1c01-115">Para alinear controles mediante las guías de alineación</span><span class="sxs-lookup"><span data-stu-id="c1c01-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="c1c01-116">Seleccione el **las guías de alineación** modo de diseño en el Diseñador de Windows Forms **opciones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c1c01-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="c1c01-117">Para obtener más información, consulte [Tutorial: organizar controles en Windows Forms usando las guías de alineación](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="c1c01-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="c1c01-118">Ahora puede usar las líneas de ajuste para alinear y organizar los controles del formulario.</span><span class="sxs-lookup"><span data-stu-id="c1c01-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c01-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1c01-119">See Also</span></span>  
 [<span data-ttu-id="c1c01-120">General, Diseñador de Windows Forms, cuadro de diálogo Opciones</span><span class="sxs-lookup"><span data-stu-id="c1c01-120">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="c1c01-121">Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="c1c01-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="c1c01-122">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1c01-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="c1c01-123">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1c01-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="c1c01-124">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1c01-124">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="c1c01-125">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="c1c01-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="c1c01-126">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1c01-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="c1c01-127">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="c1c01-127">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
