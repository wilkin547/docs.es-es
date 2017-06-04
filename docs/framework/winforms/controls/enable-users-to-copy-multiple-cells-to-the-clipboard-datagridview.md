---
title: "C&#243;mo: Permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, copiar en el Portapapeles"
  - "Portapapeles, copiar varias celdas"
  - "cuadrículas de datos, copiar varias celdas"
  - "DataGridView (control) [Windows Forms], copiar varias celdas"
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms
Cuando se habilita la copia de celdas, los datos de su control <xref:System.Windows.Forms.DataGridView> son más fácilmente accesibles para otras aplicaciones mediante el <xref:System.Windows.Forms.Clipboard>.  Los valores de las celdas seleccionadas se convierten en cadenas y se agregan al Portapapeles como valores de texto delimitados por tabulaciones para pegarlos en aplicaciones como el Bloc de notas y Excel, y como una tabla con formato HTML para pegarlos en aplicaciones como Word.  
  
 Puede configurar la copia de celdas para copiar solo valores de celda, para incluir el texto de encabezado de filas y columnas en los datos del Portapapeles, o para incluir el texto de encabezado solo cuando los usuarios seleccionan filas o columnas completas.  
  
 Según el modo de selección, los usuarios pueden seleccionar varios grupos de celdas desconectados.  Cuando el usuario copia las celdas en el Portapapeles, no se copian las filas y columnas que no tienen celdas seleccionadas.  Todas las demás filas o columnas se convierten en filas y columnas de la tabla de datos que se copia en el Portapapeles.  Las celdas no seleccionadas en estas filas o columnas se copian como marcadores de posición en blanco en el Portapapeles.  
  
### Para habilitar la copia de celdas  
  
-   Establecer la propiedad <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=fullName>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## Ejemplo  
 En el ejemplo de código completo siguiente se muestra cómo se copian las celdas en el Portapapeles.  Este ejemplo incluye un botón que copia las celdas seleccionadas en el Portapapeles usando el método <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=fullName> y muestra el contenido del Portapapeles en un cuadro de texto.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## Compilar el código  
 Este código requiere:  
  
-   Referencias a los ensamblados N:System y N:System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>   
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>   
 [Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)