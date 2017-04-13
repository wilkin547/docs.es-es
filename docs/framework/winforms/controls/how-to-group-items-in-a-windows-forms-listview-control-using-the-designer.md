---
title: "C&#243;mo: Agrupar elementos en un control ListView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "agrupar"
  - "grupos, de controles de Windows Forms"
  - "ListView (control) [Windows Forms], agrupar elementos"
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Agrupar elementos en un control ListView de formularios Windows Forms mediante el Dise&#241;ador
La característica de agrupación del control <xref:System.Windows.Forms.ListView> le permite mostrar conjuntos relacionados de elementos en grupos.  Estos grupos se separan en la pantalla por encabezados de grupo horizontales que contienen los títulos de grupo.  Puede utilizar grupos de elementos <xref:System.Windows.Forms.ListView> para hacer que la navegación por listas de gran tamaño sea más fácil agrupando alfabéticamente los elementos, por fecha, o por cualquier otra agrupación lógica.  La imagen siguiente muestra algunos elementos agrupados.  
  
 ![Grupos ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.ListView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
 Para habilitar la agrupación, debe crear en primer lugar uno o más objetos <xref:System.Windows.Forms.ListViewGroup> ya sea en el diseñador o mediante programación.  Cuando se ha definido un grupo, puede asignar los elementos a éste.  
  
> [!NOTE]
>  Los grupos <xref:System.Windows.Forms.ListView> sólo están disponibles en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  En sistemas operativos anteriores, cualquier código relacionado con grupos no tiene ningún efecto y no aparecerán los grupos.  Para obtener más información, vea <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>.  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar o quitar grupos en el diseñador  
  
1.  En la ventana **Propiedades**, haga clic en el botón de **puntos suspensivos** \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) que se encuentra junto a la propiedad <xref:System.Windows.Forms.ListView.Groups%2A>.  
  
     Aparecerá el **Editor de la colección ListViewGroup**.  
  
2.  Para agregar un grupo, haga clic en el botón **Agregar**.  A continuación, puede establecer las propiedades del nuevo grupo, como las propiedades <xref:System.Windows.Forms.ListViewGroup.Header%2A> y <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>.  Para quitar un grupo, selecciónelo y haga clic en el botón **Quitar**.  
  
### Para asignar elementos a grupos en el diseñador  
  
1.  En la ventana **Propiedades**, haga clic en el botón de **puntos suspensivos** \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) que se encuentra junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.  
  
     Aparecerá el **Editor de la colección de ListViewItem**.  
  
2.  Para agregar un nuevo elemento, haga clic en el botón **Agregar**.  A continuación puede establecer las propiedades del nuevo elemento, como las propiedades <xref:System.Windows.Forms.ListViewItem.Text%2A> y <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.  
  
3.  Seleccione la propiedad <xref:System.Windows.Forms.ListViewItem.Group%2A> y elija un grupo de la lista desplegable.  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.Groups%2A>   
 <xref:System.Windows.Forms.ListViewGroup>   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Características de Windows XP y controles de formularios Windows Forms](http://msdn.microsoft.com/es-es/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)