---
title: "C&#243;mo: Delimitar controles en formularios Windows Forms | Microsoft Docs"
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
  - "Anchor (propiedad), habilitar formularios de tamaño ajustable"
  - "controles [Windows Forms], delimitar"
  - "controles [Windows Forms], colocar"
  - "formularios, cambiar el tamaño"
  - "cambiar el tamaño de los formularios"
  - "resolución de pantalla y presentación de controles"
  - "controles de Windows Forms, resoluciones de pantalla"
  - "controles de Windows Forms, tamaño"
  - "Windows Forms, cambiar el tamaño"
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Delimitar controles en formularios Windows Forms
Si está diseñando un formulario cuyo tamaño pueda cambiar el usuario en tiempo de ejecución, es recomendable que los controles del formulario ajusten correctamente su tamaño y su ubicación.  Para cambiar dinámicamente el tamaño de los controles con el formulario, puede utilizar la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> de los controles de formularios Windows Forms.  La propiedad <xref:System.Windows.Forms.Control.Anchor%2A> define una posición de delimitación para el control.  Cuando se delimita un control en un formulario y se cambia el tamaño del formulario, el control conserva la distancia entre el control y las posiciones de delimitación.  Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> delimitado en los bordes izquierdo, derecho e inferior del formulario, al cambiar el tamaño del formulario, el control <xref:System.Windows.Forms.TextBox> cambia su tamaño horizontalmente, de modo que conserve la misma distancia desde los lados derecho e izquierdo del formulario.  Además, el control se ubica verticalmente de forma que se encuentre siempre a la misma distancia del borde inferior del formulario.  Si un control no está delimitado y el tamaño del formulario cambia, la posición del control relativa a los bordes del formulario cambia.  
  
 La propiedad <xref:System.Windows.Forms.Control.Anchor%2A> interactúa con la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.  Para obtener más información, consulte [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para delimitar un control en un formulario  
  
1.  Seleccione el control que desee delimitar.  
  
    > [!NOTE]
    >  Se pueden delimitar varios controles simultáneamente haciendo clic en cada uno de los controles con la tecla CTRL presionada y siguiendo el resto del procedimiento.  
  
2.  En la ventana **Propiedades**, haga clic en la flecha que se encuentra a la derecha de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.  
  
     Aparecerá un editor que muestra una cruz.  
  
3.  Para establecer una delimitación, haga clic en la sección superior, izquierda, derecha o inferior de la cruz.  
  
     De forma predeterminada, los controles se delimitan arriba y a la izquierda.  
  
4.  Para borrar un lado delimitado del control, haga clic en el brazo correspondiente de la cruz.  
  
5.  Para cerrar el editor de propiedades <xref:System.Windows.Forms.Control.Anchor%2A>, haga clic de nuevo en el nombre de propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.  
  
 Cuando se muestre el formulario en tiempo de ejecución, el tamaño del control cambiará para permanecer ubicado a la misma distancia del borde del formulario.  La distancia desde el borde delimitado permanece siempre igual a la distancia definida cuando se ubicó el control en el Diseñador de Windows Forms.  
  
> [!NOTE]
>  Ciertos controles, tales como el control <xref:System.Windows.Forms.ComboBox>, tienen el alto limitado.  Al delimitar el control a la parte inferior de su formulario o contenedor no es posible forzarlo para que supere su límite de alto.  
  
 Los controles heredados deben estar protegidos \(`Protected`\) para que se puedan delimitar.  Para cambiar el nivel de acceso de un control, establezca su propiedad `Modifiers` en la ventana **Propiedades**.  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Cómo: Acoplar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Tutorial: Organizar controles en Windows Forms mediante FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Tutorial: Diseñar controles de formularios Windows Forms con relleno, márgenes y la propiedad AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)