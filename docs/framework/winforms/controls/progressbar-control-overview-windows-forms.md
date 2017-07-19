---
title: "Informaci&#243;n general sobre ProgressBar (Control, formularios Windows Forms) | Microsoft Docs"
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
  - "ProgressBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles de progreso, acerca de los controles de progreso"
  - "ProgressBar (control) [Windows Forms], acerca del control ProgressBar"
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Informaci&#243;n general sobre ProgressBar (Control, formularios Windows Forms)
> [!IMPORTANT]
>  Aunque el control <xref:System.Windows.Forms.ToolStripProgressBar> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ProgressBar>, este control <xref:System.Windows.Forms.ProgressBar> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 El control <xref:System.Windows.Forms.ProgressBar> de formularios Windows Forms indica el progreso de un proceso, mediante la presentación de un número adecuado de rectángulos dispuestos en una barra horizontal.  Cuando se completa el proceso, la barra se llena.  Las barras de progreso suelen utilizarse para dar al usuario una idea de cuánto deberá esperar hasta que se complete un proceso como, por ejemplo, la carga de un archivo grande.  
  
> [!NOTE]
>  El control <xref:System.Windows.Forms.ProgressBar> sólo se puede orientar horizontalmente en el formulario.  
  
## Propiedades y métodos principales  
 Las propiedades principales del control <xref:System.Windows.Forms.ProgressBar> son <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A>.  Las propiedades <xref:System.Windows.Forms.ProgressBar.Minimum%2A> y <xref:System.Windows.Forms.ProgressBar.Maximum%2A> establecen los valores mínimo y máximo que puede mostrar la barra de progreso.  La propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> representa el progreso realizado para completar la operación.  Puesto que la barra mostrada en el control se compone de bloques, el valor que muestra el control <xref:System.Windows.Forms.ProgressBar> sólo se aproxima al valor actual de la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>.  En función del tamaño del control <xref:System.Windows.Forms.ProgressBar>, la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> determina cuándo se muestra el siguiente bloque.  
  
 El modo más común de actualizar el valor de progreso actual es escribir código para definir la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>.  En el ejemplo de la carga de un archivo grande, podría establecer el máximo en el tamaño del archivo en kilobytes.  Por ejemplo, si la propiedad <xref:System.Windows.Forms.ProgressBar.Maximum%2A> se establece en 100, la propiedad <xref:System.Windows.Forms.ProgressBar.Minimum%2A> se establece en 10 y la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> se establece en 50, se mostrarán 5 rectángulos.  Este valor es la mitad del número que se puede mostrar.  
  
 Sin embargo, hay otros modos de modificar el valor que muestra el control <xref:System.Windows.Forms.ProgressBar>, aparte de establecer la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> directamente.  La propiedad <xref:System.Windows.Forms.ProgressBar.Step%2A> se puede utilizar para especificar un valor con el que incrementar la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>.  Así, al llamar al método <xref:System.Windows.Forms.ProgressBar.PerformStep%2A>, se incrementará el valor.  Para variar el valor del incremento, puede utilizar el método <xref:System.Windows.Forms.ProgressBar.Increment%2A> y especificar un valor con el que incrementar la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A>.  
  
 Otro control que informa gráficamente al usuario acerca de una acción actual es el control <xref:System.Windows.Forms.StatusBar>.  
  
> [!IMPORTANT]
>  Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>, y les agregan funcionalidad; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan para obtener la compatibilidad con versiones anteriores y para su uso futuro, si se desea.  
  
## Vea también  
 <xref:System.Windows.Forms.ProgressBar>   
 [ProgressBar](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)