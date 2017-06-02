---
title: "C&#243;mo: Mostrar botones de opci&#243;n en un control MenuStrip (Windows Forms) | Microsoft Docs"
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
  - "mostrar botones de opción, MenuStrip [Windows Forms]"
  - "MenuStrip [Windows Forms], mostrar botones de opción"
  - "botones de opción [Windows Forms], mostrar en MenuStrip"
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Mostrar botones de opci&#243;n en un control MenuStrip (Windows Forms)
Los botones de opción, también denominados botones de radio, son similares a las casillas, salvo que los usuarios sólo pueden seleccionarlos de uno en uno.  Aunque, de forma predeterminada, la clase <xref:System.Windows.Forms.ToolStripMenuItem> no proporciona el comportamiento de botón de opción, proporciona el comportamiento de casilla, que se puede personalizar para implementar el comportamiento de botón de opción para los elementos de menú en un control <xref:System.Windows.Forms.MenuStrip>.  
  
 Cuando la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> de un elemento de menú es `true`, los usuarios pueden hacer clic en el elemento para alternar la presentación de una marca de verificación.  La propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> indica el estado actual del elemento.  Para implementar el comportamiento de botón de opción básico, debe garantizar que, cuando se seleccione un elemento, se establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> del elemento anteriormente seleccionado en `false`.  
  
 Los procedimientos siguientes describen cómo implementar este comportamiento y la funcionalidad adicional de una clase que hereda de la clase <xref:System.Windows.Forms.ToolStripMenuItem>.  La clase `ToolStripRadioButtonMenuItem` reemplaza miembros como <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar la apariencia y el comportamiento de selección de los botones de opción.  Además, esta clase reemplaza la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> para que las opciones de un submenú se deshabiliten a menos que se seleccione el elemento primario.  
  
### Para implementar el comportamiento de selección de botón de opción  
  
1.  Inicialice la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> en `true` para habilitar la selección de elementos.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Reemplace el método <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> para anular la selección del elemento anteriormente seleccionado cuando se seleccione un nuevo elemento.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Reemplace el método <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> para garantizar que al hacer clic en un elemento ya seleccionado, no se anulará la selección.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### Para modificar la apariencia de los elementos de botón de opción  
  
1.  Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para reemplazar la marca de verificación predeterminada por un botón de opción usando la clase <xref:System.Windows.Forms.RadioButtonRenderer>.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Reemplace los métodos <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> para realizar un seguimiento del estado del mouse y garantizar que el método <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> pinta el estado del botón de opción correcto.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### Para deshabilitar las opciones de un submenú cuando no se selecciona el elemento primario  
  
1.  Reemplace la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> para que el elemento se deshabilite cuando tenga un elemento primario con la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> establecida en `true` y la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> establecida en `false`.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Reemplace el método <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> para suscribirse al evento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> del elemento primario.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  En el controlador del evento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> del elemento primario, invalide el elemento para actualizar la pantalla con el nuevo estado habilitado.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## Ejemplo  
 En el ejemplo de código siguiente se proporciona la clase `ToolStripRadioButtonMenuItem` completa, así como las clases <xref:System.Windows.Forms.Form> y `Program` para mostrar el comportamiento del botón de opción.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RadioButtonRenderer>   
 [MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [Cómo: Implementar un control ToolStripRenderer personalizado](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)