---
title: 'Cómo: Buscar datos en un control DataRepeater (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 689990ee125c85c3151a4e965b619fde068d220e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588059"
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a>Cómo: Buscar datos en un control DataRepeater (Visual Studio)
Cuando se usa un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control que contiene el número de registros, puede que desee que los usuarios busquen un registro específico. En lugar de buscar los datos en el propio control, puede implementar una búsqueda consultando subyacente <xref:System.Windows.Forms.BindingSource>. Si se encuentra el elemento, a continuación, puede usar el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> propiedad para seleccionar el elemento y desplazar en la vista.  
  
### <a name="to-implement-search"></a>Para implementar la búsqueda  
  
1.  Arrastre un control <xref:System.Windows.Forms.TextBox> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
2.  En la ventana Propiedades, cambie la propiedad **Name** a **SearchTextBox**.  
  
3.  Arrastre un control <xref:System.Windows.Forms.Button> desde el **Cuadro de herramientas** hasta el formulario que contenga el control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .  
  
4.  En la ventana Propiedades, cambie la propiedad **Name** a **SearchButton**. Cambie la propiedad **Text** a **Search**.  
  
5.  Haga doble clic en el control <xref:System.Windows.Forms.Button> para abrir el Editor de código y agregue el código siguiente al controlador de eventos `SearchButton_Click` .  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     Reemplace *ProductsBindingSource* con el nombre de la <xref:System.Windows.Forms.BindingSource> para su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>y reemplace *ProductID* con el nombre del campo que se va a buscar.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Cambiar la apariencia de un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
