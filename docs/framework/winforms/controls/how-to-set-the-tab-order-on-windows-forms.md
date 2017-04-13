---
title: "C&#243;mo: Establecer el orden de tabulaci&#243;n en formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TabStop"
  - "TabIndex"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], establecer el orden de tabulación"
  - "orden de tabulación, controles de formularios Windows Forms"
  - "controles de Windows Forms, establecer el orden de tabulación"
  - "Windows Forms, establecer el orden de tabulación"
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Establecer el orden de tabulaci&#243;n en formularios Windows Forms
El orden de tabulación es el orden en el que el usuario mueve el foco de un control a otro al presionar la tecla TABULADOR.  Cada formulario tiene su propio orden de tabulación.  De forma predeterminada, el orden de tabulación es el mismo que el orden en el que se crearon los controles.  La numeración del orden de tabulación empieza por cero.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para establecer el orden de tabulación de un control  
  
1.  En el menú **Ver**, haga clic en **Orden de tabulación**.  
  
     Esto activa el modo de selección del orden de tabulación en el formulario.  En la esquina superior izquierda de cada control aparecerá un número \(que representa la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A>\).  
  
2.  Haga clic secuencialmente en los controles para establecer el orden de tabulación que desee.  
  
    > [!NOTE]
    >  La posición de un control dentro del orden de tabulación puede establecerse en cualquier valor mayor o igual que 0.  Cuando hay duplicados, se evalúa el orden Z de los dos controles y el control de la parte superior se pone en primer lugar.  El orden z es la disposición visual en capas de los controles en un formulario a lo largo del eje z del formulario \(profundidad\).  El orden z determina qué controles se encuentran por delante de otros controles. Para obtener más información acerca del orden z, vea [Disponer objetos en capas en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
3.  Cuando termine, haga clic de nuevo en **Orden de tabulación** en el menú **Ver** para abandonar el modo de orden de tabulación.  
  
    > [!NOTE]
    >  Los controles que no pueden tener el foco, así como los deshabilitados e invisibles, no tienen propiedad <xref:System.Windows.Forms.Control.TabIndex%2A> y no se incluyen en el orden de tabulación.  Cuando el usuario presiona la tecla TABULADOR, estos controles se omiten.  
  
 También es posible establecer el orden de tabulación en la ventana Propiedades mediante la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A>.  La propiedad <xref:System.Windows.Forms.Control.TabIndex%2A> de un control determina su posición dentro del orden de tabulación.  De forma predeterminada, para el primer control que se dibuja el valor de <xref:System.Windows.Forms.Control.TabIndex%2A> es 0; para el segundo, el valor de <xref:System.Windows.Forms.Control.TabIndex%2A> es 1 y así sucesivamente.  
  
 Además, de forma predeterminada, los controles <xref:System.Windows.Forms.GroupBox> tienen su propio valor <xref:System.Windows.Forms.Control.TabIndex%2A>, que es un número entero.  Un control <xref:System.Windows.Forms.GroupBox> no puede tener por sí mismo el foco en tiempo de ejecución.  De ese modo, cada control incluido en un objeto <xref:System.Windows.Forms.GroupBox> tiene su propio valor <xref:System.Windows.Forms.Control.TabIndex%2A> decimal, que comienza por ,0.  Naturalmente, conforme aumente el valor <xref:System.Windows.Forms.Control.TabIndex%2A> de un control <xref:System.Windows.Forms.GroupBox>, los controles que contiene se irán incrementando en consecuencia.  Si cambia el valor de <xref:System.Windows.Forms.Control.TabIndex%2A> de 5 a 6, el valor de <xref:System.Windows.Forms.Control.TabIndex%2A> del primer control de su grupos cambia automáticamente a 6.0, etc.  
  
 Finalmente, es posible omitir cualquier control del formulario en el orden de tabulación.  Habitualmente, al presionar sucesivamente la tecla TABULADOR en tiempo de ejecución, se selecciona cada control en el orden de tabulación.  Al desactivar la propiedad <xref:System.Windows.Forms.Control.TabStop%2A>, es posible hacer que un control se pase por alto en el orden de tabulación del formulario.  
  
#### Para quitar un control del orden de tabulación  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.TabStop%2A> del control en `false` en la ventana Propiedades.  
  
     Un control cuya propiedad <xref:System.Windows.Forms.Control.TabStop%2A> se haya establecido en `false` seguirá manteniendo su posición en el orden de tabulación, incluso aunque se omita al recorrer los controles con la tecla TABULADOR.  
  
    > [!NOTE]
    >  Un grupo de botones de radio tiene una única tabulación en tiempo de ejecución.  El botón seleccionado \(es decir, el botón cuya propiedad <xref:System.Windows.Forms.RadioButton.Checked%2A> está establecida en `true`\) tiene su propiedad <xref:System.Windows.Forms.Control.TabStop%2A> establecida automáticamente en `true`, mientras que los demás botones tienen su propiedad <xref:System.Windows.Forms.Control.TabStop%2A> establecida en `false`.  Para obtener más información sobre agrupar controles <xref:System.Windows.Forms.RadioButton>, vea [Agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)