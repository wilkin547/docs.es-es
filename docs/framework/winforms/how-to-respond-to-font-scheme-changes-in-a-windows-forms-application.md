---
title: "Cómo: Responder a los cambios de las combinaciones de fuentes en una aplicación de Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b2e53df114c491e99e13940ae47a4119bd8da46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Cómo: Responder a los cambios de las combinaciones de fuentes en una aplicación de Windows Forms
En los sistemas operativos de Windows, un usuario puede cambiar la configuración de fuente de todo el sistema para que la fuente predeterminada aparezca mayor o menor. Cambiar esta configuración de fuente es fundamental para personas con discapacidades visuales y requieren un tipo mayor leer el texto en las pantallas. Puede ajustar la aplicación de formularios Windows Forms para reaccionar a estos cambios aumentando o reduciendo el tamaño del formulario y de todo el texto cada vez que cambia la combinación de fuentes. Si desea que el formulario para adaptarse dinámicamente a cambios en los tamaños de fuente, puede agregar código al formulario.  
  
 Normalmente, la fuente predeterminada utilizada por Windows Forms es la fuente devuelta por la <xref:Microsoft.Win32> llamada de espacio de nombres a `GetStockObject(DEFAULT_GUI_FONT)`. La fuente devuelta por esta llamada solo cambia cuando la resolución de pantalla. Como se muestra en el siguiente procedimiento, el código debe cambiar la fuente predeterminada para <xref:System.Drawing.SystemFonts.IconTitleFont%2A> para responder a cambios en el tamaño de fuente.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Para usar la fuente del escritorio y responder a los cambios de esquema de fuentes  
  
1.  Crear el formulario y agregarle los controles que desee. Para obtener más información, consulte [Cómo: crear una aplicación de Windows Forms desde la línea de comandos](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) y [controles que se utilizan en formularios Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
2.  Agregue una referencia a la <xref:Microsoft.Win32> espacio de nombres en el código.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Agregue el código siguiente al constructor del formulario que se va a enlazar controladores de eventos necesarios como cambiar la fuente predeterminada en uso para el formulario.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Implemente un controlador para el <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> evento que hace que el formulario se ajuste automáticamente cuando el <xref:Microsoft.Win32.UserPreferenceCategory.Window> cambios de categoría.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Por último, implemente un controlador para el <xref:System.Windows.Forms.Form.FormClosing> eventos que separa el <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> controlador de eventos.  
  
> [!IMPORTANT]
>  Si no se incluye este código hará que la aplicación a la pérdida de memoria.  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  Compile y ejecute el código.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>Para cambiar manualmente la combinación de fuentes en Windows XP  
  
1.  Mientras se ejecuta la aplicación de formularios Windows Forms, haga clic en el escritorio de Windows y elija **propiedades** en el menú contextual.  
  
2.  En el **propiedades de presentación** cuadro de diálogo, haga clic en el **apariencia** ficha.  
  
3.  Desde el **el tamaño de fuente** lista desplegable, seleccione un nuevo tamaño de fuente.  
  
     Observará que ahora el formulario responde para ejecutar los cambios de tiempo en el esquema de la fuente del escritorio. Cuando el usuario cambia entre **Normal**, **fuentes grandes**, y **fuentes muy grandes**, el formulario cambia la fuente y escala correctamente.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 El constructor de este ejemplo de código contiene una llamada a `InitializeComponent`, que se define cuando se crea un nuevo proyecto de formularios Windows Forms en Visual Studio. Quite esta línea de código si va a compilar la aplicación en la línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [Ajuste automático de escala en Windows Forms](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
