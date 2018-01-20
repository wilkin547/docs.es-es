---
title: "Cómo: Agrupar elementos en un control ListView de formularios Windows Forms mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5e86ecdad66c9e58d691b18126c1fbf782e3130
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Cómo: Agrupar elementos en un control ListView de formularios Windows Forms mediante el Diseñador
La característica de agrupación de la <xref:System.Windows.Forms.ListView> control le permite mostrar conjuntos de elementos relacionados en grupos. Estos grupos se separan en la pantalla por encabezados de grupo horizontales que contienen los títulos de grupo. Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación sea más fácil de listas grandes mediante la agrupación de elementos por orden alfabético, por fecha, o por cualquier otra agrupación lógica. La siguiente imagen muestra algunos elementos agrupados.  
  
 ![Grupos ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.ListView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
 Para habilitar la agrupación, primero debe crear uno o varios <xref:System.Windows.Forms.ListViewGroup> objetos en el diseñador o mediante programación. Una vez que se ha definido un grupo, puede asignar elementos a él.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>grupos solo están disponibles en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama el <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> método. En sistemas operativos anteriores, cualquier código relacionado con grupos no tiene ningún efecto y los grupos no aparecerán. Para obtener más información, consulta <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a>Para agregar o quitar grupos en el diseñador  
  
1.  En el **propiedades** ventana, haga clic en el **puntos suspensivos** (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) situado junto a el <xref:System.Windows.Forms.ListView.Groups%2A> propiedad.  
  
     El **Editor de la colección ListViewGroup** aparece.  
  
2.  Para agregar un grupo, haga clic en el **agregar** botón. A continuación, puede establecer propiedades del nuevo grupo, como la <xref:System.Windows.Forms.ListViewGroup.Header%2A> y <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> propiedades. Para quitar un grupo, selecciónelo y haga clic en el **quitar** botón.  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a>Para asignar elementos a grupos en el diseñador  
  
1.  En el **propiedades** ventana, haga clic en el **puntos suspensivos** (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) situado junto a el <xref:System.Windows.Forms.ListView.Items%2A> propiedad.  
  
     El **Editor de la colección de ListViewItem** aparece.  
  
2.  Para agregar un nuevo elemento, haga clic en el **agregar** botón. A continuación, puede establecer propiedades del nuevo elemento, como el <xref:System.Windows.Forms.ListViewItem.Text%2A> y <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> propiedades.  
  
3.  Seleccione el <xref:System.Windows.Forms.ListViewItem.Group%2A> propiedad y elija un grupo en la lista desplegable.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [ListView (Control)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Características de Windows XP y controles de Windows Forms](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
