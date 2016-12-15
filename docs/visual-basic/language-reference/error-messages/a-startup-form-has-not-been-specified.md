---
title: "No se ha especificado un formulario de inicio | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrAppModel_NoStartupForm"
dev_langs: 
  - "VB"
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se ha especificado un formulario de inicio
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La aplicación utiliza la clase <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> pero no especifica el formulario de inicio.  
  
 Esto se puede producir si la casilla **Habilitar marco de trabajo de la aplicación** se activa en el diseñador del proyecto, pero no se especifica el **Formulario de inicio**.  Para obtener más información, vea [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
### Para corregir este error  
  
1.  Especifique un objeto de inicio para la aplicación.  
  
     Para obtener más información, vea [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
2.  Reemplace el método <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> para establecer la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> en el formulario de inicio.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>   
 [Información general sobre el modelo de aplicaciones de Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)