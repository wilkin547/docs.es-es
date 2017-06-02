---
title: "C&#243;mo: Heredar de una clase de control | Microsoft Docs"
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
  - "Control (clase), heredar"
  - "controles personalizados [Windows Forms], crear"
  - "controles personalizados [Windows Forms], herencia"
  - "herencia, controles personalizados de Windows Forms"
  - "OnPaint (método) [Windows Forms]"
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Heredar de una clase de control
Si desea crear un control completamente personalizado para utilizarlo en un Windows Form, la clase desde la que deberá heredar es <xref:System.Windows.Forms.Control>.  Aunque heredar de la clase <xref:System.Windows.Forms.Control> requiere más planificación e implementación, también le proporciona una gama más amplia de opciones.  Al heredar de <xref:System.Windows.Forms.Control>, se hereda la funcionalidad más básica que hace funcionar los controles.  La funcionalidad inherente a la clase <xref:System.Windows.Forms.Control> se ocupa de los datos proporcionados por el usuario por medio del teclado y del mouse, define los límites y el tamaño del control, proporciona un controlador de ventanas y ofrece control de mensajes y seguridad.  No incorpora ninguna representación, que en este caso es la representación real de la interfaz gráfica del control, ni ninguna otra funcionalidad específica de interacción con el usuario.  El creador debe proporcionar todos estos elementos por medio de código personalizado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear un control personalizado  
  
1.  Cree un nuevo proyecto de tipo **Aplicación para Windows** o **Biblioteca de controles de Windows**.  
  
2.  En el menú **Proyecto**, elija **Agregar clase**.  
  
3.  En el cuadro de diálogo **Agregar nuevo elemento**, haga clic en **Control personalizado**.  
  
     Se agregará un nuevo control personalizado al proyecto.  
  
4.  Presione F7 para abrir el **Editor de código** para el control personalizado.  
  
5.  Busque el método <xref:System.Windows.Forms.Control.OnPaint%2A>, que estará vacío a excepción de una llamada al método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base.  
  
6.  Modifique el código a fin de incorporar la representación personalizada que desee para el control.  
  
     Para obtener información sobre cómo escribir código para representar gráficos para los controles, vea [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
7.  Implemente los métodos, propiedades o eventos personalizados que vaya a incorporar el control.  
  
8.  Guarde y pruebe el control.  
  
## Vea también  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Cómo: Heredar de una clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [Cómo: Heredar de controles de formularios Windows Forms existentes](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [Cómo: Crear controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Solucionar problemas de controladores de eventos heredados en Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [Desarrollar controles de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)