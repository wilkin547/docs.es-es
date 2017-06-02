---
title: "Efectos de modificar la apariencia de un formulario base | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "formularios base"
  - "herencia, formularios"
  - "formularios heredados, modificaciones en el formulario base"
  - "formularios primarios"
  - "Windows Forms, apariencia de los formularios base"
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Efectos de modificar la apariencia de un formulario base
Durante el desarrollo de una aplicación, a menudo puede resultar necesario cambiar la apariencia del formulario base del que están heredando los demás formularios del proyecto \(o de otros proyectos\).  
  
 En tiempo de diseño, los cambios de apariencia del formulario base \(ya sea la configuración de sus propiedades o la adición o substracción de controles\) se reflejan en los formularios heredados cuando se compila el proyecto que contiene el formulario base.  No es suficiente guardar simplemente los cambios en el formulario base.  Para compilar un proyecto, elija **Compilar** en el menú **Compilar**.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Las modificaciones efectuadas en el formulario base no afectan a los formularios heredados cuya instancia ya se ha creado.  
  
## Vea también  
 [base](../Topic/base%20\(C%23%20Reference\).md)   
 [Cómo: Heredar formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)   
 [Herencia visual de formularios Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)