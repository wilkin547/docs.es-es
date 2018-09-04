---
title: Efectos de modificar la apariencia de un formulario base
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: adaf9224fd340c6ea4342e2591806a7c877e83ff
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43533900"
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a><span data-ttu-id="fe2f4-102">Efectos de modificar la apariencia de un formulario base</span><span class="sxs-lookup"><span data-stu-id="fe2f4-102">Effects of Modifying a Base Form&#39;s Appearance</span></span>
<span data-ttu-id="fe2f4-103">Durante el desarrollo de aplicaciones, a menudo tendrá que cambiar la apariencia del formulario base del que se heredan los demás formularios del proyecto (o de otros proyectos).</span><span class="sxs-lookup"><span data-stu-id="fe2f4-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="fe2f4-104">En tiempo de diseño, los cambios efectuados a la apariencia del formulario base (ya sea la configuración de propiedades o la suma y resta de controles) se reflejan en los formularios heredados al compilar el proyecto que contiene el formulario base.</span><span class="sxs-lookup"><span data-stu-id="fe2f4-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="fe2f4-105">No basta con guardar simplemente los cambios en el formulario base.</span><span class="sxs-lookup"><span data-stu-id="fe2f4-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="fe2f4-106">Para compilar un proyecto, elija **Compilar** en el menú **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="fe2f4-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe2f4-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="fe2f4-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fe2f4-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="fe2f4-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fe2f4-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="fe2f4-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
 <span data-ttu-id="fe2f4-110">Las modificaciones realizadas en el formulario base en tiempo de ejecución no tienen ningún efecto en los formularios heredados cuya instancia ya se ha creado.</span><span class="sxs-lookup"><span data-stu-id="fe2f4-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe2f4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe2f4-111">See Also</span></span>  
 [<span data-ttu-id="fe2f4-112">base</span><span class="sxs-lookup"><span data-stu-id="fe2f4-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="fe2f4-113">Cómo: Heredar formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe2f4-113">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="fe2f4-114">Herencia visual de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe2f4-114">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
