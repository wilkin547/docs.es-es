---
title: "Modo virtual del control DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater"
  - "DataRepeater, modo virtual"
  - "enlace de datos virtual"
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Modo virtual del control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Si desea mostrar grandes volúmenes de datos en formato de tabla en un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, puede mejorar el rendimiento estableciendo la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> en `True` y controlando de forma explícita la interacción del control con su origen de datos.  El control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> proporciona varios eventos que permiten controlar la interacción con el origen de datos y mostrar los datos según sea necesario en tiempo de ejecución.  
  
## Cómo funciona el modo virtual  
 El escenario más común para el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> es enlazar en tiempo de diseño los controles secundarios de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> a un origen de datos y permitir que <xref:System.Windows.Forms.BindingSource> intercambie datos en ambos sentidos según sea necesario.  Cuando se utiliza el modo virtual, los controles no se enlazan a un origen de datos, por lo que los datos se intercambian en ambos sentidos con el origen de datos subyacente.  
  
 Cuando la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> se establece en `True`, se crea la interfaz de usuario agregando controles del **Cuadro de herramientas** en lugar de agregar los controles enlazados en la ventana **Orígenes de datos**.  
  
 Los eventos se provocan individualmente para cada control y es preciso agregar código para controlar la presentación de los datos.  Cuando un nuevo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> se desplaza y queda visible, el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> se provoca una vez por cada control; debe proporcionar los valores correspondientes a cada control en el controlador de eventos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>.  
  
 Si el usuario cambia los datos de uno de los controles, se provoca el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>, en cuyo caso deberá validar los datos y guardarlos en el origen de datos.  
  
 Si el usuario agrega un nuevo elemento, se provoca el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>.  Utilice el controlador de este evento para crear un nuevo registro en el origen de datos.  Para evitar los cambios imprevistos, también debe supervisar el evento <xref:System.Windows.Forms.Control.KeyDown> de cada control y llamar al método <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> si el usuario presiona la tecla ESC.  
  
 Si el origen de datos cambia, puede actualizar el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> mediante una llamada a los métodos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetTemplateItem%2A> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetTemplateItem%2A>.  Se debe llamar a ambos métodos por orden.  
  
 Por último, debe implementar los controladores del evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>, que se provoca cuando se elimina un elemento y, opcionalmente, para los eventos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems>, que se provocan cada vez que un usuario elimina un elemento presionando la tecla SUPR.  
  
## Implementar el modo virtual  
 A continuación se muestran los pasos necesarios para implementar el modo virtual.  
  
#### Para implementar el modo virtual  
  
1.  Arrastre un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> desde la ficha **Visual Basic PowerPacks** del **Cuadro de herramientas** hasta un control de formulario o un control contenedor.  Establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> en `True`.  
  
2.  Arrastre los controles desde el **Cuadro de herramientas** hasta la región de la plantilla de elemento \(la región superior\) del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Necesitará un control para cada campo del origen de datos que desee mostrar.  
  
3.  Implemente un controlador para que el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> proporcione valores para cada control.  Se provoca este evento cuando un nuevo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> se desplaza y queda visible.  El código será similar al siguiente ejemplo, que se aplica a un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Implemente un controlador para que el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> almacene los datos.  Se provoca este evento cuando el usuario confirma los cambios y los escribe en un control secundario de <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  El código será similar al siguiente ejemplo, que se aplica a un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Implemente un controlador para el evento <xref:System.Windows.Forms.Control.KeyDown> de cada control secundario y supervise la tecla ESC.  Llame al método <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> para evitar que se provoque el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>.  El código tendrá un aspecto similar al ejemplo siguiente.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Implemente un controlador para el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>.  Se provoca este evento cuando el usuario agrega un nuevo elemento al control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  El código será similar al siguiente ejemplo, que se aplica a un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Implemente un controlador para el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>.  Este evento se produce cuando un usuario elimina un elemento existente.  El código será similar al siguiente ejemplo, que se aplica a un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Para efectuar una validación de nivel de control, puede implementar controladores para los eventos <xref:System.Windows.Forms.Control.Validating> de los controles secundarios.  El código tendrá un aspecto similar al ejemplo siguiente.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-cs[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)