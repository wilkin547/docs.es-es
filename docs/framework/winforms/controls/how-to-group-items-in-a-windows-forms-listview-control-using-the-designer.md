---
title: Procedimiento para agrupar elementos en un control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "69039397"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Procedimiento para agrupar elementos en un control ListView de formularios Windows Forms mediante el diseñador

La característica de agrupación del <xref:System.Windows.Forms.ListView> control permite mostrar conjuntos de elementos relacionados en grupos. Estos grupos se separan en la pantalla por los encabezados de grupo horizontal que contienen los títulos de grupo. Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes mediante la agrupación de elementos por orden alfabético, por fecha o por cualquier otra agrupación lógica. En la imagen siguiente se muestran algunos elementos agrupados:

![Números separados en grupos impares e impares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ListView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

Para habilitar la agrupación, primero debe crear uno o más <xref:System.Windows.Forms.ListViewGroup> objetos en el diseñador o mediante programación. Una vez definido un grupo, puede asignarle elementos.

> [!NOTE]
> <xref:System.Windows.Forms.ListView>los grupos solo están disponibles [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] en cuando la aplicación <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> llama al método. En los sistemas operativos anteriores, cualquier código relacionado con los grupos no tiene ningún efecto y los grupos no aparecerán. Para obtener más información, consulta <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.

## <a name="to-add-or-remove-groups-in-the-designer"></a>Para agregar o quitar grupos en el diseñador

1. En la ventana **propiedades** , haga clic en los![ **puntos suspensivos** (el botón de puntos suspensivos (...) del botón](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio. <xref:System.Windows.Forms.ListView.Groups%2A> ) situado junto a la propiedad.

     Aparece el editor de la **colección ListViewGroup** .

2. Para agregar un grupo, haga clic en el botón **Agregar** . Después, puede establecer las propiedades del nuevo grupo, como las <xref:System.Windows.Forms.ListViewGroup.Header%2A> propiedades y. <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> Para quitar un grupo, selecciónelo y haga clic en el botón **quitar** .

## <a name="to-assign-items-to-groups-in-the-designer"></a>Para asignar elementos a grupos en el diseñador

1. En la ventana **propiedades** , haga clic en los![ **puntos suspensivos** (el botón de puntos suspensivos (...) del botón](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio. <xref:System.Windows.Forms.ListView.Items%2A> ) situado junto a la propiedad.

     Aparece el editor de la **colección ListViewItem** .

2. Para agregar un nuevo elemento, haga clic en el botón **Agregar** . Después, puede establecer las propiedades del nuevo elemento, como las <xref:System.Windows.Forms.ListViewItem.Text%2A> propiedades y. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>

3. Seleccione la <xref:System.Windows.Forms.ListViewItem.Group%2A> propiedad y elija un grupo en la lista desplegable.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView (Control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
