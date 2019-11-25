---
title: No se ha especificado un formulario de inicio
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 301f249e6222c929d2c513964ecbb21df5fbc47f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976195"
---
# <a name="a-startup-form-has-not-been-specified"></a>No se ha especificado un formulario de inicio

La aplicación usa la clase <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> pero no especifica el formulario de inicio.  
  
 Esto puede ocurrir si la casilla **Habilitar marco de aplicación** está activada en el diseñador de proyectos, pero no se ha especificado el **formulario de inicio** . Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Especifique un objeto de inicio para la aplicación.  
  
     Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2. Invalide el método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> para establecer la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> en el formulario de inicio.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Información general sobre el modelo de aplicaciones de Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
