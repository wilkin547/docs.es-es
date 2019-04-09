---
title: Filtrar para mostrar un control en el cuadro de diálogo Elegir elementos del cuadro de herramientas
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: d504ace9e5571246ae0e78e165a7ad2bc23fa481
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085303"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="63e22-102">Filtrar para mostrar un control en el cuadro de diálogo Elegir elementos del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="63e22-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="63e22-103">Desarrollar y distribuir controles, es posible que desee esos controles aparezca en el **elegir elementos del cuadro de herramientas** cuadro de diálogo que aparece cuando hace clic en el **cuadro de herramientas** y seleccione  **Elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="63e22-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="63e22-104">Puede habilitar el control aparezca en este cuadro de diálogo mediante el procedimiento de registro AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="63e22-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="63e22-105">Para mostrar el control en el cuadro de diálogo Elegir elementos del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="63e22-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="63e22-106">Instale al ensamblado del control a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="63e22-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="63e22-107">Para obtener más información, vea [Cómo: Instalar un ensamblado en la caché global de ensamblados](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="63e22-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="63e22-108">-o bien-</span><span class="sxs-lookup"><span data-stu-id="63e22-108">-or-</span></span>  
  
-   <span data-ttu-id="63e22-109">Registre el control y los ensamblados en tiempo de diseño asociados mediante el procedimiento de registro AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="63e22-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="63e22-110">AssemblyFoldersEx es una ubicación del registro donde otros proveedores almacenan las rutas de acceso para cada versión de framework que admiten.</span><span class="sxs-lookup"><span data-stu-id="63e22-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="63e22-111">Resolución de tiempo de diseño puede buscar en esta ubicación del registro para buscar los ensamblados de referencia.</span><span class="sxs-lookup"><span data-stu-id="63e22-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="63e22-112">El script de registro puede especificar los controles que desee que aparezca en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="63e22-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="63e22-113">Para obtener más información, consulte [implementar un Control personalizado y ensamblados en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="63e22-113">For more information, see [Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e22-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="63e22-114">See also</span></span>

- [<span data-ttu-id="63e22-115">Elija el cuadro de diálogo de elementos de cuadro de herramientas (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="63e22-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [<span data-ttu-id="63e22-116">Implementación de un Control personalizado y ensamblados en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="63e22-116">Deploying a Custom Control and Design-time Assemblies</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))
- [<span data-ttu-id="63e22-117">Desarrollar controles de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="63e22-117">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="63e22-118">Filtrar para instalar un ensamblado en la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="63e22-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="63e22-119">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="63e22-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
