---
title: Modo virtual del control DataRepeater (Visual Studio) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- virtual data binding
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 85f7e250c57a507e891eb30756c0550098cce9e0
ms.lasthandoff: 03/13/2017

---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Modo virtual del control DataRepeater (Visual Studio)
Si desea mostrar grandes cantidades de datos tabulares en una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control, puede mejorar el rendimiento estableciendo la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>propiedad `True` y administrar explícitamente la interacción del control con su origen de datos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control proporciona varios eventos que puede controlar para interactuar con el origen de datos y mostrar los datos según sea necesario en tiempo de ejecución.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="how-virtual-mode-works"></a>Virtual cómo funciona el modo  
 El escenario más común para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>es enlazar los controles secundarios del control de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>a datos de origen en tiempo de diseño y permitir la <xref:System.Windows.Forms.BindingSource>para pasar datos sentidos según sea necesario.</xref:System.Windows.Forms.BindingSource> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Al utilizar el modo virtual, los controles no se enlazan a un origen de datos y datos se pasan hacia delante y hacia atrás en el origen de datos subyacente en tiempo de ejecución.  
  
 Cuando el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>propiedad está establecida en `True`, se crea la interfaz de usuario agregando controles desde el **cuadro de herramientas** en lugar de agregar controles enlazados de la **orígenes de datos** ventana.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>  
  
 Se generan eventos en forma de control a control, y debe agregar código para controlar la presentación de datos. Cuando un nuevo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>se desplaza en la vista, la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>evento se desencadena una vez para cada control y proporcione los valores de cada control en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>controlador de eventos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>  
  
 Si se modifican datos en uno de los controles por el usuario, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>se genera el evento y debe validar los datos y guardarlo en el origen de datos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>  
  
 Si el usuario agrega un nuevo elemento, el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>evento se desencadena.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> Utilice el controlador de este evento para crear un nuevo registro en el origen de datos. Para evitar cambios no deseados, también debe supervisar el <xref:System.Windows.Forms.Control.KeyDown>eventos para cada control y llamar a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>Si el usuario presiona la tecla ESC.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> </xref:System.Windows.Forms.Control.KeyDown>  
  
 Si los datos de origen cambia, puede actualizar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control llamando a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>métodos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Deben llamar a ambos métodos en orden.  
  
 Por último, debe implementar los controladores de eventos para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>evento, que se produce cuando se elimina un elemento y, opcionalmente, para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems>y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems>eventos que se producen cuando un usuario elimina un elemento presionando la tecla SUPR.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>  
  
## <a name="implementing-virtual-mode"></a>Implementar el modo Virtual  
 Siguientes son los pasos necesarios para implementar el modo virtual.  
  
#### <a name="to-implement-virtual-mode"></a>Para implementar el modo virtual  
  
1.  Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control desde el **Visual Basic PowerPacks** ficha en el **cuadro de herramientas** a un control de formulario o contenedor.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Establecer el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>propiedad `True`.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>  
  
2.  Arrastre controles desde el **herramientas** a la región de plantilla de elementos (la región superior) de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Necesitará un control para cada campo del origen de datos que desea mostrar.  
  
3.  Implemente un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>eventos para proporcionar valores para cada control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> Este evento se desencadena cuando un nuevo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>se desplaza en la vista.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> El código será similar a la del ejemplo siguiente, que es para un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode n.º&1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Implemente un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>eventos para almacenar los datos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> Este evento se desencadena cuando el usuario confirma los cambios en un control secundario del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> El código será similar a la del ejemplo siguiente, que es para un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&#2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Implemente un controlador para cada control secundario <xref:System.Windows.Forms.Control.KeyDown>eventos y monitor de la tecla ESC.</xref:System.Windows.Forms.Control.KeyDown> Llame a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>método para impedir que el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>que se produzca el evento.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> El código será similar en el siguiente ejemplo.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Implemente un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>eventos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> Este evento se desencadena cuando el usuario agrega un elemento nuevo en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>control.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> El código será similar a la del ejemplo siguiente, que es para un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode Nº&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&#4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Implemente un controlador para el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>eventos.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> Este evento se produce cuando un usuario elimina un elemento existente. El código será similar a la del ejemplo siguiente, que es para un origen de datos denominado `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Para la validación de nivel de control, puede implementar controladores para el <xref:System.Windows.Forms.Control.Validating>eventos de los controles secundarios.</xref:System.Windows.Forms.Control.Validating> El código será similar en el siguiente ejemplo.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&6;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&6;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
