---
title: Modo virtual del control DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- virtual data binding [Visual Basic]
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
ms.openlocfilehash: 3988c16746606de9f20f9a66b87539b6cea04758
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700811"
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Modo virtual del control DataRepeater (Visual Studio)
Cuando desea mostrar grandes cantidades de datos tabulares en una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, puede mejorar el rendimiento estableciendo la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> propiedad `True` y administrar explícitamente la interacción del control con su origen de datos. El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control proporciona varios eventos que puede controlar para interactuar con el origen de datos y mostrar los datos según sea necesario en tiempo de ejecución.  
  
## <a name="how-virtual-mode-works"></a>Virtual cómo funciona el modo  
 El escenario más común para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> es enlazar los controles secundarios del control la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> a datos de origen en tiempo de diseño y permitir la <xref:System.Windows.Forms.BindingSource> para pasar datos sentidos según sea necesario. Al utilizar el modo virtual, los controles no están enlazados a un origen de datos y datos se van y vienen en el origen de datos subyacente en tiempo de ejecución.  
  
 Cuando el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> propiedad está establecida en `True`, crear la interfaz de usuario agregando controles desde el **cuadro de herramientas** en lugar de agregar controles enlazados desde el **orígenes de datos** ventana.  
  
 Los eventos se generan según el control a control, y debe agregar código para controlar la visualización de datos. Cuando un nuevo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> se puede desplazar en la vista, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> se genera el evento una vez para cada control y debe proporcionar los valores para cada control en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> controlador de eventos.  
  
 Si los datos en uno de los controles se cambia por el usuario, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> se genera el evento y debe validar los datos y guardarlo en el origen de datos.  
  
 Si el usuario agrega un nuevo elemento, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> provoca el evento. Utilice el controlador de este evento para crear un nuevo registro en el origen de datos. Para evitar cambios no deseados, también debe supervisar el <xref:System.Windows.Forms.Control.KeyDown> evento para cada control y la llamada <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> si el usuario presiona la tecla ESC.  
  
 Si los cambios de origen de datos, puede actualizar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control mediante una llamada a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> métodos. Ambos métodos deben llamarse en orden.  
  
 Por último, debe implementar controladores de eventos para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> evento, que se produce cuando se elimina un elemento y, opcionalmente, para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> eventos, que se producen cuando un usuario elimina un elemento presionando la tecla SUPR.  
  
## <a name="implementing-virtual-mode"></a>Implementar el modo Virtual  
 Estos son los pasos necesarios para implementar el modo virtual.  
  
#### <a name="to-implement-virtual-mode"></a>Para implementar el modo virtual  
  
1.  Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor. Establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> en `True`.  
  
2.  Arrastrar controles desde el **cuadro de herramientas** a la región de la plantilla de elemento (la región superior) de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Necesitará un control para cada campo del origen de datos que desea mostrar.  
  
3.  Implementar un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> eventos para proporcionar valores para cada control. Este evento se desencadena cuando un nuevo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> se puede desplazar en la vista. El código será similar en el ejemplo siguiente, que es para un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Implementar un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> eventos para almacenar los datos. Este evento se desencadena cuando el usuario confirma los cambios en un control secundario de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>. El código será similar en el ejemplo siguiente, que es para un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Implementar un controlador para cada control secundario <xref:System.Windows.Forms.Control.KeyDown> eventos y monitor de la tecla ESC. Llame a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> método para impedir que el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> eventos que se generen. El código será similar en el ejemplo siguiente.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Implementar un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> eventos. Este evento se desencadena cuando el usuario agrega un nuevo elemento a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. El código será similar en el ejemplo siguiente, que es para un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Implementar un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> eventos. Este evento se produce cuando un usuario elimina un elemento existente. El código será similar en el ejemplo siguiente, que es para un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Para la validación de nivel de control, puede implementar controladores para el <xref:System.Windows.Forms.Control.Validating> eventos de los controles secundarios. El código será similar en el ejemplo siguiente.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>
- [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
