---
title: 'Cómo: Cambiar la apariencia de un control DataRepeater (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
ms.openlocfilehash: 9863d9343ffcecc1e4aae7f6bc16dae39ef76385
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590126"
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a>Cómo: Cambiar la apariencia de un control DataRepeater (Visual Studio)
Puede cambiar la apariencia de un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control en tiempo de diseño estableciendo las propiedades o en tiempo de ejecución controlando el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> eventos.  
  
 Propiedades que establecen en tiempo de diseño cuando se selecciona la sección de la plantilla de elemento del control se repetirá para cada <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> en tiempo de ejecución. Propiedades relacionadas con la apariencia de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> propio control será visible en tiempo de ejecución si solo una parte del contenedor se deja detectado (por ejemplo, si la <xref:System.Windows.Forms.Control.Padding%2A> propiedad está establecida en un valor grande).  
  
 Propiedades relacionadas con la apariencia de en tiempo de ejecución, pueden establecerse según las condiciones. Por ejemplo, en una aplicación de programación, puede cambiar el color de fondo de un elemento para advertir a los usuarios cuando un elemento está vencido. En el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> controlador de eventos, si se establece una propiedad en una instrucción condicional como `If…Then`, también debe usar un `Else` cláusula para especificar la apariencia cuando no se cumple la condición.  
  
### <a name="to-change-the-appearance-at-design-time"></a>Para cambiar la apariencia en tiempo de diseño  
  
1.  En el Diseñador de Windows Forms, seleccione la región de plantilla (superior) del elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.  
  
2.  En la ventana Propiedades, seleccione una propiedad y cambie el valor. Propiedades comunes que afectan a la apariencia incluyen <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, y <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### <a name="to-change-the-appearance-at-run-time"></a>Para cambiar la apariencia en tiempo de ejecución  
  
1.  En el Editor de código, en la lista desplegable de eventos, haga clic en **DrawItem**.  
  
2.  En el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> controlador de eventos, agregue código para establecer las propiedades:  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 Algunas personalizaciones comunes para la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control incluyen mostrar las filas en colores alternos y cambiar el color de un campo en función de una condición. En el ejemplo siguiente se muestra cómo realizar estas personalizaciones. En este ejemplo se da por supuesto que tiene un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control que está enlazado a la tabla Products de la base de datos Northwind.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 Tenga en cuenta que en ambas de estas personalizaciones, debe proporcionar código para establecer las propiedades de ambos lados de la condición. Si no se especifica la `Else` condición, verá resultados inesperados en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Mostrar los encabezados de los elementos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
