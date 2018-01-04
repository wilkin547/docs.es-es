---
title: "Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1323ffbd59a14d19d1161e0718fad083bcc37a89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="ec72a-102">Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ec72a-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="ec72a-103">Desarrollar y distribuir controles, puede que desee esos controles aparezcan en el **elegir elementos del cuadro de herramientas** cuadro de diálogo que aparece cuando hace clic en el **cuadro de herramientas** y seleccione  **Elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="ec72a-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="ec72a-104">Puede habilitar el control aparezca en este cuadro de diálogo mediante el procedimiento de registro de AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="ec72a-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="ec72a-105">Para mostrar el control en el cuadro de diálogo Elegir elementos del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ec72a-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="ec72a-106">Instale al ensamblado de control en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ec72a-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="ec72a-107">Para obtener más información, vea [Cómo: instalar un ensamblado en la caché Global de ensamblados](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="ec72a-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="ec72a-108">O bien</span><span class="sxs-lookup"><span data-stu-id="ec72a-108">-or-</span></span>  
  
-   <span data-ttu-id="ec72a-109">Registre el control y los ensamblados en tiempo de diseño asociados mediante el procedimiento de registro de AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="ec72a-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="ec72a-110">AssemblyFoldersEx es una ubicación del registro donde otros proveedores almacenan las rutas de acceso para cada versión de .NET framework admiten.</span><span class="sxs-lookup"><span data-stu-id="ec72a-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="ec72a-111">La resolución en tiempo de diseño puede buscar en esta ubicación del registro para encontrar los ensamblados de referencia.</span><span class="sxs-lookup"><span data-stu-id="ec72a-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="ec72a-112">El script de registro puede especificar los controles que desea que aparezcan en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="ec72a-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="ec72a-113">Para obtener más información, consulte [implementar un Control personalizado y ensamblados en tiempo de diseño (Visual Studio 2013)](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span><span class="sxs-lookup"><span data-stu-id="ec72a-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec72a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec72a-114">See Also</span></span>  
 [<span data-ttu-id="ec72a-115">Elegir elementos del cuadro de herramientas (Cuadro de diálogo): Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ec72a-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="ec72a-116">Implementar un Control personalizado y ensamblados en tiempo de diseño (Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="ec72a-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [<span data-ttu-id="ec72a-117">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ec72a-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="ec72a-118">Instalar un ensamblado en la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="ec72a-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [<span data-ttu-id="ec72a-119">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="ec72a-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
