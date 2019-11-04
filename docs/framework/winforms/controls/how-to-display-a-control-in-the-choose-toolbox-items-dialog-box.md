---
title: 'Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas'
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: db4b3ac020e967a6a0c291103d825ac71cebda23
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458271"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="d1e05-102">Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="d1e05-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>

<span data-ttu-id="d1e05-103">A medida que desarrolle y distribuya controles, puede que desee que estos controles aparezcan en el cuadro de diálogo **elegir elementos del cuadro de herramientas** de Visual Studio, que se muestra al hacer clic con el botón secundario en el cuadro de **herramientas** y seleccionar **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="d1e05-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box of Visual Studio, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="d1e05-104">Puede habilitar el control para que aparezca en este cuadro de diálogo mediante el procedimiento de registro de AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="d1e05-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>

<span data-ttu-id="d1e05-105">Para mostrar el control en el cuadro de diálogo Elegir elementos del cuadro de herramientas:</span><span class="sxs-lookup"><span data-stu-id="d1e05-105">To display your control in the Choose Toolbox Items dialog box:</span></span>

- <span data-ttu-id="d1e05-106">Instale el ensamblado de control en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d1e05-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="d1e05-107">Para obtener más información, vea [Cómo: Instalar un ensamblado en la memoria caché global de ensamblados](../../app-domains/install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="d1e05-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/install-assembly-into-gac.md).</span></span>

  <span data-ttu-id="d1e05-108">o bien</span><span class="sxs-lookup"><span data-stu-id="d1e05-108">-or-</span></span>

- <span data-ttu-id="d1e05-109">Registre el control y sus ensamblados en tiempo de diseño asociados mediante el procedimiento de registro de AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="d1e05-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="d1e05-110">AssemblyFoldersEx es una ubicación del registro donde los proveedores de terceros almacenan rutas de acceso para cada versión del marco que admiten.</span><span class="sxs-lookup"><span data-stu-id="d1e05-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="d1e05-111">La resolución en tiempo de diseño puede buscar en esta ubicación del registro para buscar ensamblados de referencia.</span><span class="sxs-lookup"><span data-stu-id="d1e05-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="d1e05-112">El script del registro puede especificar los controles que desea que aparezcan en el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d1e05-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1e05-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1e05-113">See also</span></span>

- [<span data-ttu-id="d1e05-114">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d1e05-114">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="d1e05-115">Instalar un ensamblado en la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="d1e05-115">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/install-assembly-into-gac.md)
- [<span data-ttu-id="d1e05-116">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="d1e05-116">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
