---
title: "Dibujo y representaci&#243;n personalizados de controles | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], dibujar"
  - "controles personalizados [Windows Forms], representar"
  - "OnPaint (método)"
  - "controles de usuario [Windows Forms], dibujar"
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Dibujo y representaci&#243;n personalizados de controles
La representación personalizada de controles es una de las muchas tareas complicadas que facilita .NET Framework.  Cuando cree un control personalizado, dispondrá de muchas opciones relacionadas con la apariencia gráfica del control.  Si crea un control que hereda de `Control`, deberá proporcionar código que permita al control crear su representación gráfica.  Si crea un control de usuario mediante la herencia de `UserControl` o hereda de uno de los controles de formularios Windows Forms, puede reemplazar la representación gráfica estándar y proporcionar un código de gráficos propio.  Si desea proporcionar una representación gráfica para los controles constituyentes del `UserControl` que está creando, las opciones estarán mas limitadas, aunque dispondrá aún de una amplia gama de posibilidades para controles y aplicaciones.  
  
## En esta sección  
 [Representar un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 Muestra cómo programar la lógica que muestra un control.  
  
 [Controles dibujados por el usuario](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 Proporciona información general acerca de los pasos necesarios para escribir y reemplazar código de representación para el control.  
  
 [Controles constituyentes](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 Describe cómo implementar código de representación personalizado para los controles constituyentes de los controles de usuario y los formularios.  
  
 [Cómo: Hacer un control no visible en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 Muestra cómo utilizar la propiedad <xref:System.Windows.Forms.Control.Visible%2A> para ocultar y mostrar un control.  
  
 [Cómo: Proporcionar un fondo transparente a un control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 Muestra cómo utilizar el método <xref:System.Windows.Forms.Control.SetStyle%2A> para crear un color de fondo que sea opaco, transparente o parcialmente transparente.  
  
 [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 Muestra cómo representar controles utilizando los estilos visuales en sistemas operativos que los admiten.  
  
## Referencia  
 <xref:System.Windows.Forms.Control>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.UserControl>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Describe este método.  
  
## Secciones relacionadas  
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 Presenta la funcionalidad de gráficos [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] desde la perspectiva de Visual Studio y proporciona vínculos a información adicional.  
  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 Describe los tipos de controles personalizados que puede crear.