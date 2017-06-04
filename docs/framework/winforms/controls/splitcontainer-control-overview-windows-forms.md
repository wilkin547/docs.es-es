---
title: "Informaci&#243;n general sobre SplitContainer (Control, formularios Windows Forms) | Microsoft Docs"
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
  - "SplitContainer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "SplitContainer (control) [Windows Forms], acerca del control SplitContainer"
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre SplitContainer (Control, formularios Windows Forms)
El control <xref:System.Windows.Forms.SplitContainer> de formularios Windows Forms se puede considerar como un elemento compuesto: se trata de dos paneles separados por una barra movible.  Cuando el puntero del mouse está encima de la barra, cambia de forma para indicar que la barra es movible.  
  
> [!IMPORTANT]
>  En el **Cuadro de herramientas**, el control <xref:System.Windows.Forms.SplitContainer> reemplaza al control <xref:System.Windows.Forms.Splitter> que había en la versión anterior de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  El control <xref:System.Windows.Forms.SplitContainer> es mucho más conveniente que el control <xref:System.Windows.Forms.Splitter>.  La clase <xref:System.Windows.Forms.Splitter> se incluye todavía en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para ofrecer compatibilidad con las aplicaciones existentes, pero recomendamos encarecidamente utilizar el control <xref:System.Windows.Forms.SplitContainer> para los proyectos nuevos.  
  
 Con el control <xref:System.Windows.Forms.SplitContainer>, puede crear interfaces de usuario complejas; con frecuencia, una selección en un panel determina qué objetos se muestran en el otro panel.  Esta organización es muy eficaz para mostrar y explorar información.  Disponer de dos paneles permite agregar información en las áreas y la barra o "divisor" facilita al usuario la tarea de cambiar el tamaño de los paneles.  
  
 Además, es posible anidar más de un control <xref:System.Windows.Forms.SplitContainer>, de modo que el segundo control <xref:System.Windows.Forms.SplitContainer> esté orientado en sentido horizontal y cree un panel arriba y otro abajo.  
  
 Tenga en cuenta que el control <xref:System.Windows.Forms.SplitContainer> es accesible desde el teclado de manera predeterminada; los usuarios pueden presionar las teclas de dirección para mover el divisor si la propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> se establece en `false`.  
  
 La propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A> del control <xref:System.Windows.Forms.SplitContainer> determina la dirección del divisor, no del control propiamente dicho.  Por lo tanto, cuando esta propiedad se establece en <xref:System.Windows.Forms.Orientation>, el divisor va de arriba a abajo y crea un panel a la izquierda y uno a la derecha.  
  
 Tenga en cuenta también que el valor de la propiedad <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> varía en función del valor de la propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A>.  Para obtener más información, vea la propiedad <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A>.  
  
 También puede restringir el tamaño y el movimiento del control <xref:System.Windows.Forms.SplitContainer>.  La propiedad <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> determina cuál de los paneles seguirá siendo del mismo tamaño después de cambiar el tamaño del control <xref:System.Windows.Forms.SplitContainer>, y la propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> determina si el divisor es movible desde el teclado o el mouse.  
  
> [!NOTE]
>  Aunque la propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> se establezca en `true`, el divisor se puede desplazar mediante programación; por ejemplo, utilizando la propiedad <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>.  
  
 Por último, cada panel del control <xref:System.Windows.Forms.SplitContainer> tiene propiedades que permiten determinar su tamaño individual.  
  
## Propiedades, métodos y eventos de uso frecuente  
  
|Name|Descripción|  
|----------|-----------------|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina cuál de los paneles seguirá siendo del mismo tamaño después de cambiar el tamaño del control <xref:System.Windows.Forms.SplitContainer>.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina si el divisor se puede desplazar mediante el teclado o el mouse.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Determina si el divisor se colocará en sentido vertical u horizontal.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distancia en píxeles, contando desde el borde izquierdo o superior, hasta la barra de división movible.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distancia mínima, en píxeles, que el usuario puede trasladar el divisor.|  
|Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Determina el grosor, en píxeles, del divisor.|  
|Evento <xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Se produce cuando el divisor se está moviendo.|  
|Evento <xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Se produce cuando el divisor se ha movido.|  
  
## Vea también  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer \(Control\)](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)   
 [SplitContainer Control Sample](http://msdn.microsoft.com/es-es/9015fad0-7108-4d85-a83a-a72d038c4f65)