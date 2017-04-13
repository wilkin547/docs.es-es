---
title: "C&#243;mo: Heredar de una clase UserControl | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles compuestos, crear"
  - "herencia, controles personalizados de Windows Forms"
  - "controles de usuario [Windows Forms], crear"
  - "UserControl (clase), heredar"
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Heredar de una clase UserControl
Para combinar la funcionalidad de uno o más controles de formularios Windows Forms con código personalizado, puede crear un *control de usuario*.  Los controles de usuario combinan el desarrollo rápido de controles con la funcionalidad de los controles estándar de formularios Windows Forms y la versatilidad de las propiedades y métodos personalizados.  Cuando cree un control de usuario, se le presentará un diseñador visible en el que puede colocar controles estándar de formularios Windows Forms.  Estos controles conservan toda su funcionalidad inherente, así como el aspecto y comportamiento de los controles estándar.  Sin embargo, cuando estos controles se incorporan al control de usuario, dejan de estar disponibles a través del código.  El control de usuario realiza su propia representación y controla también toda la funcionalidad básica asociada a los controles.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear un control de usuario  
  
1.  Cree un nuevo proyecto de tipo **Biblioteca de controles de Windows**.  
  
     Se creará un nuevo proyecto con un control de usuario en blanco.  
  
2.  Arrastre controles al diseñador desde la ficha **Windows Forms** del **Cuadro de herramientas**.  
  
3.  Coloque y diseñe estos controles tal y como desee que aparezcan en el control de usuario final.  Si desea permitir a los programadores el acceso a los controles constituyentes, deberá declararlos como públicos o exponer las propiedades del control constituyente de forma selectiva.  Para obtener información detallada, vea [Cómo: Exponer propiedades de controles constituyentes](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).  
  
4.  Implemente los métodos o propiedades personalizados que vaya a incorporar el control.  
  
5.  Presione F5 para compilar el proyecto y ejecutar el control en el **UserControl Test Container**.  Para obtener más información, vea [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
## Vea también  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Cómo: Heredar de una clase de control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [Cómo: Heredar de controles de formularios Windows Forms existentes](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [Cómo: Crear controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Solucionar problemas de controladores de eventos heredados en Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)