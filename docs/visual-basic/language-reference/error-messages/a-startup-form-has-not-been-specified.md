---
title: No se ha especificado un formulario de inicio
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: f05358f76829768d8ff5c4ac85b5134f35254126
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627218"
---
# <a name="a-startup-form-has-not-been-specified"></a>No se ha especificado un formulario de inicio
La aplicación usa el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> clase pero no especifica el formulario de inicio.  
  
 Esto puede ocurrir si el **Habilitar marco de trabajo de aplicación** casilla de verificación está seleccionada en el Diseñador de proyectos, pero la **formulario de inicio** no se especifica. Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Especifique un objeto de inicio para la aplicación.  
  
     Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2.  Invalidar el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> método para establecer el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> propiedad en el formulario de inicio.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Información general sobre el modelo de aplicaciones de Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
