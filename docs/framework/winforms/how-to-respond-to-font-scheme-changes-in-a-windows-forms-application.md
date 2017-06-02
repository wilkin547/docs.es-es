---
title: "How to: Respond to Font Scheme Changes in a Windows Forms Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, font scheme changes"
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Respond to Font Scheme Changes in a Windows Forms Application
En los sistemas operativos Windows, el usuario puede cambiar la configuración de fuente de todo el sistema para que la fuente predeterminada aparezca más grande o más pequeña.  Cambiar esta configuración de fuente es imprescindible para aquellos usuarios visualmente discapacitados y que requieren un tipo mayor para leer los textos en la pantalla.  Se puede ajustar la aplicación de Windows Forms para que responda a estos cambios aumentando o disminuyendo el tamaño del formulario y de todo el texto cuando cambie las combinaciones de fuentes.  Si desea que el formulario se adapte dinámicamente a los cambios de fuentes, agregue código al formulario.  
  
 Normalmente, la fuente predeterminada utilizada por los formularios Windows Forms es la fuente devuelta por la llamada del espacio de nombres <xref:Microsoft.Win32> a `GetStockObject(DEFAULT_GUI_FONT)`.  La fuente que devuelve esta llamada sólo cambia cuando cambia la resolución de la pantalla.  Como se muestra en el procedimiento siguiente, el código debe cambiar la fuente predeterminada a <xref:System.Drawing.SystemFonts.IconTitleFont%2A> para responder a los cambios del tamaño de la fuente.  
  
### Para utilizar la fuente del escritorio y responder a los cambios de la combinación de fuentes  
  
1.  Cree el formulario y agregue los controles que desea.  Para obtener más información, vea [How to: Create a Windows Forms Application from the Command Line](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) y [Controles que se utilizan en formularios Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
2.  Agregue al código una referencia al espacio de nombres <xref:Microsoft.Win32>.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Agregue el código siguiente al constructor del formulario para enlazar los controladores de eventos necesarios, y cambiar la fuente predeterminada utilizada en el formulario.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Implemente un controlador para el evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> que  hace que el formulario se ajuste automáticamente cuando cambia la categoría <xref:Microsoft.Win32.UserPreferenceCategory>.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Por último, implemente un controlador para el evento <xref:System.Windows.Forms.Form.FormClosing> que  desasocia el controlador de eventos <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.  
  
> [!IMPORTANT]
>  Si no se incluye ese código, la aplicación perderá memoria.  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  Compile y ejecute el código.  
  
### Para cambiar manualmente la combinación de fuentes en Windows XP  
  
1.  Mientras está ejecutándose la aplicación de Windows Forms, haga clic con el botón secundario del mouse en el escritorio Windows y elija **Propiedades** en el menú contextual.  
  
2.  En el cuadro de diálogo **Mostrar propiedades**, haga clic en la ficha **Apariencia**.  
  
3.  En el cuadro de lista desplegable **Tamaño de fuente**, seleccione un nuevo tamaño de la fuente.  
  
     Observará que ahora el formulario responde a los cambios en tiempo de ejecución en la combinación de fuentes de escritorio.  Cuando el usuario cambia entre **Normal**, **Fuentes grandes** y **Fuentes extragrandes**, el formulario cambia la fuente y las escalas correctamente.  
  
## Ejemplo  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 El constructor de este ejemplo de código contiene una llamada a `InitializeComponent`, que se define cuando se crea un nuevo proyecto de formularios Windows Forms en Visual Studio.  Quite esta línea de código si está compilando la aplicación en la línea de comandos.  
  
## Vea también  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>   
 [Automatic Scaling in Windows Forms](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)