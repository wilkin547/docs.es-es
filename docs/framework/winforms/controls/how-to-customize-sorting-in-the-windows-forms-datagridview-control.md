---
title: "C&#243;mo: Personalizar la ordenaci&#243;n en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, personalizar orden"
  - "DataGridView (control) [Windows Forms], ordenar"
  - "ordenar, DataGridView (control)"
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Personalizar la ordenaci&#243;n en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> proporciona ordenación automática pero, dependiendo de sus necesidades, puede que necesite personalizar las operaciones de ordenación.  Por ejemplo, puede usar la ordenación mediante programación para crear una interfaz de usuario alternativa.  También puede controlar el evento <xref:System.Windows.Forms.DataGridView.SortCompare> o llamar a la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> para disfrutar de más opciones de ordenación, como la ordenación de varias columnas.  
  
 Los ejemplos de código siguientes muestran estos tres enfoques de la ordenación personalizada.  Para obtener más información, consulte [Modos de ordenación de columnas del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md).  
  
## Ordenación mediante programación  
 En el ejemplo de código siguiente se muestra una ordenación mediante programación usando las propiedades <xref:System.Windows.Forms.DataGridView.SortOrder%2A> y <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> para determinar la dirección de la ordenación, y la propiedad <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> para establecer manualmente el glifo de ordenación.  La sobrecarga `Sort(DataGridViewColumn,ListSortDirection)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> se usa para ordenar los datos de una sola columna.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## Ordenación personalizada mediante el evento SortCompare  
 En el ejemplo de código siguiente se muestra la ordenación personalizada mediante un controlador de eventos <xref:System.Windows.Forms.DataGridView.SortCompare>.  Se ordena la <xref:System.Windows.Forms.DataGridViewColumn> seleccionada y, si hay valores duplicados en la columna, se usa el identificador de columna para determinar el orden final.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## Ordenación personalizada mediante la interfaz IComparer  
 En el ejemplo de código siguiente se muestra la ordenación personalizada mediante la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A>, que toma una implementación de la interfaz <xref:System.Collections.IComparer> para realizar una ordenación de varias columnas.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## Compilar el código  
 Para estos ejemplos se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar estos ejemplos desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Ordenar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Modos de ordenación de columnas del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)