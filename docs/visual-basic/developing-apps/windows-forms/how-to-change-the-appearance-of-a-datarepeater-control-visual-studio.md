---
title: "C&#243;mo: Cambiar la apariencia de un control DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, cambiar la apariencia en tiempo de ejecución"
  - "DataRepeater, personalizar"
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# C&#243;mo: Cambiar la apariencia de un control DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede cambiar la apariencia de un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, en tiempo de diseño, estableciendo las propiedades o, en tiempo de ejecución, administrando el evento <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>.  
  
 Las propiedades que establece en tiempo de diseño cuando está seleccionada la sección de plantilla de elementos del control se repetirán para cada <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> en tiempo de ejecución.  Las propiedades relacionadas con la apariencia del propio control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> únicamente estarán visibles en tiempo de ejecución si una parte del contenedor queda descubierto \(por ejemplo, si la propiedad <xref:System.Windows.Forms.Control.Padding%2A> está establecida en un valor grande\).  
  
 En tiempo de ejecución, las propiedades relacionadas con la apariencia se pueden establecer basándose en condiciones.  Por ejemplo, en una aplicación de programación, se puede cambiar el color de fondo de un elemento para advertir a los usuarios del vencimiento de un elemento.  En el controlador de eventos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>, si establece una propiedad en una instrucción condicional, como `If…Then`, también deberá usar una cláusula `Else` para especificar la apariencia en caso de que no se cumpla la condición.  
  
### Para cambiar la apariencia en tiempo de diseño  
  
1.  En el Diseñador de Windows Forms, seleccione la región de plantilla de elementos \(superior\) del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
2.  En la ventana Propiedades, seleccione una propiedad y cambie el valor.  Entre las propiedades comunes que afectan a la apariencia se incluyen <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A> y <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### Para cambiar la apariencia en tiempo de ejecución  
  
1.  En el Editor de código, en la lista desplegable de eventos, haga clic en **DrawItem**.  
  
2.  En el controlador de eventos <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>, agregue código para establecer las propiedades:  
  
     [!code-cs[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPowerPacksDataRepeaterAppearanceCS/VbPowerPacksDataRepeaterAppearance.cs#1)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterAppearance/VbPowerPacksDataRepeaterAppearance.vb#1)]  
  
## Ejemplo  
 Entre las personalizaciones más comunes del control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> están la de mostrar las filas en colores alternos y la de cambiar el color de un campo en función de una condición.  En el ejemplo siguiente se muestra cómo llevar a cabo estas personalizaciones.  En este ejemplo, se supone que tiene un control <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> enlazado a la tabla Products de la base de datos Northwind.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/visualbasic/VbPowerPacksDataRepeaterAlternateBackColor/AlternateBackColor.vb#1)]
 [!code-cs[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/csharp/VbPwrPacksDataRepeaterAltBColorCS/AlternateBackColor.cs#1)]  
  
 Observe que para ambas personalizaciones, debe proporcionar código a fin de establecer las propiedades para ambos lados de la condición.  Si no especifica la condición `Else`, verá resultados inesperados en tiempo de ejecución.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>   
 [Introducción al control DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Solución de problemas del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar los datos enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar controles no enlazados en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Cómo: Mostrar los encabezados de los elementos en un control DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)