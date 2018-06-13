---
title: Solución de problemas del control DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 092bbe89bb73a40dee7161f014d40a581b0ddc06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591903"
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>Solución de problemas del control DataRepeater (Visual Studio)
En este tema se enumera los problemas comunes que pueden producirse cuando se trabaja con el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>No se generan eventos de Mouse y teclado DataRepeater  
 Algunos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> no se generan eventos de control, tales como eventos de teclado y mouse (ratón). Esto es intencionado. El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> propio control es un contenedor para <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> objetos y no se puede tener acceso en tiempo de ejecución. El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> no expone eventos en tiempo de diseño. Por lo tanto, al hacer clic en un elemento o presionar una tecla cuando el elemento tiene el foco no provoca un evento.  
  
 La excepción a esto es cuando la <xref:System.Windows.Forms.Control.Padding%2A> propiedad está establecida en un gran valor suficiente para exponer los bordes de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. En este caso, haga clic en el margen expuesto generará los eventos del mouse.  
  
 Para resolver este problema, agregue un <xref:System.Windows.Forms.Panel> el control a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> sección de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar y, a continuación, agregue el resto de los controles en el <xref:System.Windows.Forms.Panel>. A continuación, puede agregar código para el <xref:System.Windows.Forms.Panel> controladores de eventos del control de eventos de teclado y mouse (ratón).  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>DataRepeater se oculta parcialmente detrás del Examinador de enlaces  
 Cuando agrega un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> el control a un formulario y, a continuación, agregar controles enlazados a datos desde el **orígenes de datos** ventana, el <xref:System.Windows.Forms.BindingNavigator> control puede aparecer en la parte superior de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Se trata de una limitación conocida de la **orígenes de datos** ventana y es coherente con el comportamiento de otros controles, como el <xref:System.Windows.Forms.DataGridView> control.  
  
 Puede cualquier movimiento la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> inferior a la <xref:System.Windows.Forms.BindingNavigator> de control en tiempo de diseño o agregue código similar al siguiente en el `Load` controlador de eventos.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>Controles no se muestran correctamente en tiempo de ejecución  
 Algunos de los controles en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control podría no mostrarse según lo previsto en tiempo de ejecución. El proceso utilizado para clonar controles desde el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> no siempre puede determinar todas las propiedades de todos los controles. Por ejemplo, si agrega un independiente <xref:System.Windows.Forms.ListBox> el control a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> de control en tiempo de diseño y rellena su <xref:System.Windows.Forms.ListBox.Items%2A> colección con una lista de cadenas, la <xref:System.Windows.Forms.ListBox> estará vacío en tiempo de ejecución. Esto es porque el proceso de clonación no se puede tener en cuenta el <xref:System.Windows.Forms.ListBox.Items%2A> propiedad.  
  
 Puede solucionar problemas como este mediante la restauración de las propiedades que faltan en la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> evento, que se produce una vez completada la clonación predeterminada. En el ejemplo siguiente se muestra cómo reparar la <xref:System.Windows.Forms.ListBox.Items%2A> colección de un <xref:System.Windows.Forms.ListBox> controlar en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> controlador de eventos.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>El símbolo de selección en el encabezado de elemento es que faltan  
 Al cambiar la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> propiedad del encabezado de elemento en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> (control), algunas opciones de color pueden provocar que el símbolo de selección desaparezca. Cambiar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad también puede provocar que el símbolo de selección desaparezca.  
  
 No se puede cambiar el color y el tamaño del símbolo de selección.  
  
-   Si establece la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible cuando se selecciona un elemento por primera vez.  
  
-   Si establece la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.Black%2A>, el símbolo de selección no estará visible cuando se selecciona un control y el símbolo de lápiz no estará visible cuando un control está en modo de edición.  
  
-   Si el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad está establecida en un valor que es menor que 11, no se mostrarán los símbolos de indicador en el encabezado de elemento.  
  
 Puede proporcionar su propio símbolo de encabezado y la selección de elementos mediante un <xref:System.Windows.Forms.PictureBox> control y supervisión de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> propiedad de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> eventos de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Para obtener más información, consulta <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Cambiar el diseño de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Mostrar los encabezados de los elementos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [Deshabilitar las operaciones de agregar y eliminar elementos DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [Buscar datos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
