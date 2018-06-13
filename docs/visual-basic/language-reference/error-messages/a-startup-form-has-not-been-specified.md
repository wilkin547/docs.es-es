---
title: No se ha especificado un formulario de inicio
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 699d20e6afb2335336b3652be5907f0dd72299fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586791"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="933e6-102">No se ha especificado un formulario de inicio</span><span class="sxs-lookup"><span data-stu-id="933e6-102">A startup form has not been specified</span></span>
<span data-ttu-id="933e6-103">La aplicación utiliza la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> clase pero no especifica el formulario de inicio.</span><span class="sxs-lookup"><span data-stu-id="933e6-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="933e6-104">Esto puede ocurrir si el **marco de aplicación de habilitar** casilla de verificación está seleccionada en el Diseñador de proyectos, pero la **formulario de inicio** no se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="933e6-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="933e6-105">Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="933e6-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="933e6-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="933e6-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="933e6-107">Especifique un objeto de inicio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="933e6-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="933e6-108">Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="933e6-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="933e6-109">Invalidar el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> método para establecer el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> propiedad en el formulario de inicio.</span><span class="sxs-lookup"><span data-stu-id="933e6-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="933e6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="933e6-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [<span data-ttu-id="933e6-111">Información general sobre el modelo de aplicaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="933e6-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
