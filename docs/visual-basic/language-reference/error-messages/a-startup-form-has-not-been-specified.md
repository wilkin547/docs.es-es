---
description: 'Más información acerca de: no se ha especificado un formulario de inicio'
title: No se ha especificado un formulario de inicio
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 4b00890f07121ef55ce49978842010cc54aba29b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797190"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="4b2c3-103">No se ha especificado un formulario de inicio</span><span class="sxs-lookup"><span data-stu-id="4b2c3-103">A startup form has not been specified</span></span>

<span data-ttu-id="4b2c3-104">La aplicación usa la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> clase pero no especifica el formulario de inicio.</span><span class="sxs-lookup"><span data-stu-id="4b2c3-104">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="4b2c3-105">Esto puede ocurrir si la casilla **Habilitar marco de aplicación** está activada en el diseñador de proyectos, pero no se ha especificado el **formulario de inicio** .</span><span class="sxs-lookup"><span data-stu-id="4b2c3-105">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="4b2c3-106">Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4b2c3-106">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b2c3-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4b2c3-107">To correct this error</span></span>  
  
1. <span data-ttu-id="4b2c3-108">Especifique un objeto de inicio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b2c3-108">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="4b2c3-109">Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4b2c3-109">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2. <span data-ttu-id="4b2c3-110">Invalide el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> método para establecer la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> propiedad en el formulario de inicio.</span><span class="sxs-lookup"><span data-stu-id="4b2c3-110">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2c3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b2c3-111">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="4b2c3-112">Información general sobre el modelo de aplicaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b2c3-112">Overview of the Visual Basic Application Model</span></span>](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
