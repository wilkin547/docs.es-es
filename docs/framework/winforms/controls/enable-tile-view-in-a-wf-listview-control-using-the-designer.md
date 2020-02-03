---
title: Habilitar la vista en mosaico en el control ListView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745803"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Cómo: Habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el Diseñador
La característica de vista en mosaico del control <xref:System.Windows.Forms.ListView> permite proporcionar un equilibrio visual entre la información gráfica y de texto. La información de texto que se muestra para un elemento en la vista de mosaico es igual que la información de columna definida para la vista de detalles. Las funciones de la vista de mosaico en combinación con las características de agrupación o de marca de inserción del control <xref:System.Windows.Forms.ListView>.

 La vista de mosaico usa un icono 32 x 32 y varias líneas de texto, tal como se muestra en la siguiente imagen.

 ![Vista en mosaico de un control ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Texto e iconos de la vista de mosaico")

 Las propiedades y los métodos de la vista de mosaico permiten especificar los campos de columna que se van a mostrar para cada elemento y controlar colectivamente el tamaño y la apariencia de todos los elementos de una ventana de vista de mosaico. Para mayor claridad, la primera línea de texto de un mosaico siempre es el nombre del elemento; no se puede cambiar.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.ListView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-set-tile-view-in-the-designer"></a>Para establecer la vista de mosaico en el diseñador

1. En Visual Studio, seleccione el control <xref:System.Windows.Forms.ListView> del formulario.

2. En la ventana **propiedades** , seleccione la propiedad <xref:System.Windows.Forms.ListView.View%2A> y elija **mosaico**.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Información general del control ListView](listview-control-overview-windows-forms.md)
