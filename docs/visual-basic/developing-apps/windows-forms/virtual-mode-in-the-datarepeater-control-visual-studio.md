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
ms.openlocfilehash: 7aa462f670c95f2d5996cf04b676bf09e9ec62b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Modo virtual del control DataRepeater (Visual Studio)
Cuando desee mostrar grandes cantidades de datos tabulares en una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> (control), puede mejorar el rendimiento estableciendo la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> propiedad `True` y administrar de forma explícita la interacción del control con su origen de datos. El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control proporciona varios eventos que puede controlar para interactuar con el origen de datos y mostrar los datos según sea necesario en tiempo de ejecución.  
  
## <a name="how-virtual-mode-works"></a>Virtual cómo funciona el modo  
 El escenario más común para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control consiste en enlazar los controles secundarios de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> a datos de origen en tiempo de diseño y permitir que el <xref:System.Windows.Forms.BindingSource> para pasar datos y hacia atrás según sea necesario. Cuando se utiliza el modo virtual, los controles no se enlazan a un origen de datos y datos se pasan y hacia atrás en el origen de datos subyacente en tiempo de ejecución.  
  
 Cuando el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> propiedad está establecida en `True`, cree la interfaz de usuario agregando controles desde el **cuadro de herramientas** en lugar de agregar controles enlazados desde el **orígenes de datos** ventana.  
  
 Se generan eventos en forma de control a control, y debe agregar código para controlar la visualización de datos. Cuando una nueva <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> se desplaza en la vista, la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> evento se desencadena una vez para cada control y debe proporcionar los valores de cada control en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> controlador de eventos.  
  
 Si se modifican datos en uno de los controles por el usuario, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> se genera el evento y debe validar los datos y guardarlo en el origen de datos.  
  
 Si el usuario agrega un nuevo elemento, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> evento se desencadena. Utilice el controlador de este evento para crear un nuevo registro en el origen de datos. Para evitar cambios no deseados, también debe supervisar el <xref:System.Windows.Forms.Control.KeyDown> eventos para cada control y llame al método <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> si el usuario presiona la tecla ESC.  
  
 Si los datos de origen cambia, puede actualizar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control mediante una llamada a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> métodos. Deben llamar a ambos métodos en orden.  
  
 Por último, debe implementar controladores de eventos para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> evento, que se produce cuando se elimina un elemento y, opcionalmente, para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> eventos, que se producen cuando un usuario elimina un elemento presionando la tecla SUPR.  
  
## <a name="implementing-virtual-mode"></a>Implementar el modo Virtual  
 Siguientes son los pasos necesarios para implementar el modo virtual.  
  
#### <a name="to-implement-virtual-mode"></a>Para implementar el modo virtual  
  
1.  Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor. Establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> en `True`.  
  
2.  Arrastre los controles desde el **cuadro de herramientas** a la región de plantilla de elemento (la región superior) de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. Necesitará un control para cada campo en el origen de datos que desea mostrar.  
  
3.  Implemente un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> eventos para proporcionar valores para cada control. Este evento se desencadena cuando una nueva <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> desplazar en la vista. El código parecerán al ejemplo siguiente, que es un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Implemente un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> eventos para almacenar los datos. Este evento se desencadena cuando el usuario confirma los cambios en un control secundario de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>. El código parecerán al ejemplo siguiente, que es un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Implemente un controlador para cada control secundario <xref:System.Windows.Forms.Control.KeyDown> eventos y monitor de la tecla ESC. Llame a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> método para evitar la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> eventos que se produzca. El código parecerán al ejemplo siguiente.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Implemente un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> eventos. Este evento se desencadena cuando el usuario agrega un nuevo elemento a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control. El código parecerán al ejemplo siguiente, que es un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Implemente un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> eventos. Este evento se produce cuando un usuario elimina un elemento existente. El código parecerán al ejemplo siguiente, que es un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Para la validación de nivel de control, puede implementar controladores para la <xref:System.Windows.Forms.Control.Validating> eventos de los controles secundarios. El código parecerán al ejemplo siguiente.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
