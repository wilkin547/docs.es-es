---
title: "C&#243;mo: Deshabilitar botones en una columna de botones del control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "botones, deshabilitar en columnas de botones"
  - "cuadrículas de datos, deshabilitar botones"
  - "DataGridView (control) [Windows Forms], deshabilitar celdas de botones"
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Deshabilitar botones en una columna de botones del control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> incluye la clase <xref:System.Windows.Forms.DataGridViewButtonCell> para mostrar celdas con una interfaz de usuario \(IU\) como un botón.  Sin embargo, <xref:System.Windows.Forms.DataGridViewButtonCell> no proporciona una manera de deshabilitar el aspecto del botón mostrado por la celda.  
  
 En el ejemplo de código siguiente, se muestra cómo personalizar la clase <xref:System.Windows.Forms.DataGridViewButtonCell> para mostrar botones que pueden aparecer deshabilitados.  En el ejemplo se define un nuevo tipo de celda, `DataGridViewDisableButtonCell`, que deriva de <xref:System.Windows.Forms.DataGridViewButtonCell>.  Este tipo de celda proporciona una nueva propiedad `Enabled`, que puede establecerse en `false` para dibujar un botón deshabilitado en la celda.  El ejemplo también define un nuevo tipo de columna, `DataGridViewDisableButtonColumn`, que muestra objetos `DataGridViewDisableButtonCell`.  Para demostrar este nuevo tipo de celda y de columna, el valor actual de cada <xref:System.Windows.Forms.DataGridViewCheckBoxCell> en el elemento primario <xref:System.Windows.Forms.DataGridView> determina si la propiedad `Enabled` de la `DataGridViewDisableButtonCell` en la misma fila es `true` o `false`.  
  
> [!NOTE]
>  Al derivar de <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> y agregar nuevas propiedades a la clase derivada, asegúrese de invalidar el método `Clone` para copiar las nuevas propiedades durante las operaciones de clonación.  También debe llamar al método `Clone` de la clase base para copiar las propiedades de la clase base a la nueva celda o columna.  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing, System.Windows.Forms y System.Windows.Forms.VisualStyles.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Arquitectura del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [Tipos de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)