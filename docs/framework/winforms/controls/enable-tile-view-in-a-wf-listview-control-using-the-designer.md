---
title: Procedimiento para habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040362"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Procedimiento para habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el diseñador
La característica de vista de mosaico <xref:System.Windows.Forms.ListView> del control le permite proporcionar un equilibrio visual entre la información gráfica y de texto. La información de texto que se muestra para un elemento en la vista de mosaico es igual que la información de columna definida para la vista de detalles. La vista de mosaico funciona en combinación con las características de agrupación o de marca <xref:System.Windows.Forms.ListView> de inserción del control.

 La vista de mosaico usa un icono 32 x 32 y varias líneas de texto, tal como se muestra en la siguiente imagen.

 ![Vista en mosaico en un control ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Iconos y texto de la vista de mosaico")

 Las propiedades y los métodos de la vista de mosaico permiten especificar los campos de columna que se van a mostrar para cada elemento y controlar colectivamente el tamaño y la apariencia de todos los elementos de una ventana de vista de mosaico. Para mayor claridad, la primera línea de texto de un mosaico siempre es el nombre del elemento; no se puede cambiar.

 El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ListView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

> [!NOTE]
> La vista de mosaico solo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. En sistemas operativos anteriores, el código relacionado con la vista de mosaico no tiene ningún efecto y el control <xref:System.Windows.Forms.ListView> se muestra en la vista de iconos grandes. Para obtener más información, consulta <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.

## <a name="to-set-tile-view-in-the-designer"></a>Para establecer la vista de mosaico en el diseñador

1. En Visual Studio, seleccione el <xref:System.Windows.Forms.ListView> control en el formulario.

2. En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.ListView.View%2A> propiedad y elija **mosaico**.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Información general del control ListView](listview-control-overview-windows-forms.md)
