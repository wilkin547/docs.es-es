---
title: Solución de problemas del control DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 7b045e1c45221cbde82c88286da8e698a763d844
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580608"
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>Solución de problemas del control DataRepeater (Visual Studio)
En este tema se enumera los problemas comunes que pueden producirse cuando se trabaja con el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>No se generan eventos de Mouse y teclado DataRepeater  
 Algunos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> no se generan los eventos de control, como eventos de teclado y mouse (ratón). Esto es intencionado. El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> propio control es un contenedor para <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> objetos y no es accesible en tiempo de ejecución. El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> no expone los eventos en tiempo de diseño. Por lo tanto, al hacer clic en un elemento o al presionar una tecla cuando el elemento tiene el foco no provoca un evento.  
  
 La excepción a esto es cuando la <xref:System.Windows.Forms.Control.Padding%2A> propiedad está establecida en un gran valor suficiente para exponer los bordes de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. En este caso, haga clic en el margen expuesto generará eventos del mouse.  
  
 Para resolver este problema, agregue un <xref:System.Windows.Forms.Panel> el control a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> sección de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar y, a continuación, agregue el resto de los controles en el <xref:System.Windows.Forms.Panel>. A continuación, puede agregar código a la <xref:System.Windows.Forms.Panel> controladores de eventos del control de eventos de teclado y mouse (ratón).  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>DataRepeater parcialmente está oculta detrás del Examinador de enlaces  
 Cuando agrega un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> el control a un formulario y, a continuación, agregar controles enlazados a datos desde el **orígenes de datos** ventana, el <xref:System.Windows.Forms.BindingNavigator> control puede aparecer en la parte superior de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Se trata de una limitación conocida de la **orígenes de datos** ventana y es coherente con el comportamiento de otros controles, como el <xref:System.Windows.Forms.DataGridView> control.  
  
 Puede mueva la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> menor que el <xref:System.Windows.Forms.BindingNavigator> control en tiempo de diseño, o agregar código similar al siguiente en el `Load` controlador de eventos.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>No se muestran correctamente los controles en tiempo de ejecución  
 Algunos controles en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control podría no mostrarse según lo previsto en tiempo de ejecución. El proceso utilizado para clonar controles desde el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> no siempre pueden determinar todas las propiedades de todos los controles. Por ejemplo, si agrega una independiente <xref:System.Windows.Forms.ListBox> el control a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control en tiempo de diseño y rellenar sus <xref:System.Windows.Forms.ListBox.Items%2A> colección con una lista de cadenas, la <xref:System.Windows.Forms.ListBox> estará vacío en tiempo de ejecución. Esto es porque el proceso de clonación no se puede tener en cuenta el <xref:System.Windows.Forms.ListBox.Items%2A> propiedad.  
  
 Puede corregir problemas como esto mediante la restauración de las propiedades que faltan en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> evento, que se produce una vez completada la clonación de forma predeterminada. En el ejemplo siguiente se muestra cómo reparar el <xref:System.Windows.Forms.ListBox.Items%2A> colección de un <xref:System.Windows.Forms.ListBox> en controlar la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> controlador de eventos.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>Falta el símbolo de selección en el encabezado del elemento  
 Al cambiar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> propiedad del encabezado del elemento en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, algunas opciones de color pueden causar el símbolo de selección desaparezca. Cambiar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad también puede causar el símbolo de selección desaparezca.  
  
 No se puede cambiar el color y tamaño del símbolo de selección.  
  
-   Si establece la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, el símbolo de selección no estará visible cuando se selecciona por primera vez un elemento.  
  
-   Si establece la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.Black%2A>, el símbolo de selección no estará visible cuando se selecciona un control y el símbolo de lápiz no estará visible cuando un control está en modo de edición.  
  
-   Si el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> propiedad está establecida en un valor que es menor que 11, no se mostrarán los símbolos del indicador en el encabezado del elemento.  
  
 Puede proporcionar su propio símbolo de elemento de encabezado y de selección mediante un <xref:System.Windows.Forms.PictureBox> control y supervisión de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> propiedad de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> eventos de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Para obtener más información, consulta <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## <a name="see-also"></a>Vea también
- [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Cómo: Mostrar los datos enlazados en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [Cómo: Mostrar controles no enlazados en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [Cómo: Cambiar el diseño de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [Cómo: Cambiar la apariencia de un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Cómo: Mostrar encabezados de elemento en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
- [Cómo: Deshabilitar, agregar y eliminar elementos DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)
- [Cómo: Búsqueda de datos en un Control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)
- [Cómo: Crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
