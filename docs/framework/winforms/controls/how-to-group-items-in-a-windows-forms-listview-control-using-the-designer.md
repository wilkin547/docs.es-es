---
title: Agrupar elementos en el control ListView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 935d8d75517e1028e686ca229f6ada656f58b01e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736681"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Cómo: Agrupar elementos en un control ListView de formularios Windows Forms mediante el Diseñador

La característica de agrupación del control <xref:System.Windows.Forms.ListView> permite mostrar conjuntos de elementos relacionados en grupos. Estos grupos se separan en la pantalla por los encabezados de grupo horizontal que contienen los títulos de grupo. Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes mediante la agrupación alfabética de elementos, por fecha o cualquier otra agrupación lógica. En la imagen siguiente se muestran algunos elementos agrupados:

![Números separados en grupos impares e impares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.ListView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

Para habilitar la agrupación, primero debe crear uno o más objetos <xref:System.Windows.Forms.ListViewGroup> en el diseñador o mediante programación. Una vez definido un grupo, puede asignarle elementos.

## <a name="to-add-or-remove-groups-in-the-designer"></a>Para agregar o quitar grupos en el diseñador

1. En la ventana **propiedades** , haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad <xref:System.Windows.Forms.ListView.Groups%2A>.

     Aparece el editor de la **colección ListViewGroup** .

2. Para agregar un grupo, haga clic en el botón **Agregar** . Después, puede establecer las propiedades del nuevo grupo, como las propiedades <xref:System.Windows.Forms.ListViewGroup.Header%2A> y <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>. Para quitar un grupo, selecciónelo y haga clic en el botón **quitar** .

## <a name="to-assign-items-to-groups-in-the-designer"></a>Para asignar elementos a grupos en el diseñador

1. En la ventana **propiedades** , haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.

     Aparece el editor de la **colección ListViewItem** .

2. Para agregar un nuevo elemento, haga clic en el botón **Agregar** . Después, puede establecer las propiedades del nuevo elemento, como las propiedades <xref:System.Windows.Forms.ListViewItem.Text%2A> y <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.

3. Seleccione la propiedad <xref:System.Windows.Forms.ListViewItem.Group%2A> y elija un grupo de la lista desplegable.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView (control)](listview-control-windows-forms.md)
- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
