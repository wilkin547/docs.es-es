---
title: Responder a los cambios en el esquema de fuentes en una aplicación Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739227"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Cómo: Responder a los cambios de las combinaciones de fuentes en una aplicación de Windows Forms
En los sistemas operativos de Windows, un usuario puede cambiar la configuración de fuentes para todo el sistema para que la fuente predeterminada aparezca más grande o más pequeña. Cambiar estos valores de fuente es fundamental para los usuarios que tienen discapacidades visuales y requieren un tipo mayor para leer el texto de las pantallas. Puede ajustar la aplicación Windows Forms para reaccionar a estos cambios aumentando o reduciendo el tamaño del formulario y todo el texto que contenga cada vez que cambie la combinación de fuentes. Si desea que el formulario contenga los cambios en los tamaños de fuente dinámicamente, puede agregar código al formulario.  
  
 Normalmente, la fuente predeterminada usada por Windows Forms es la fuente devuelta por la llamada del espacio de nombres <xref:Microsoft.Win32> a `GetStockObject(DEFAULT_GUI_FONT)`. La fuente devuelta por esta llamada solo cambia cuando cambia la resolución de pantalla. Como se muestra en el siguiente procedimiento, el código debe cambiar la fuente predeterminada a <xref:System.Drawing.SystemFonts.IconTitleFont%2A> para responder a los cambios en el tamaño de fuente.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Para usar la fuente de escritorio y responder a los cambios de la combinación de fuentes  
  
1. Cree el formulario y agregue los controles que desee. Para obtener más información, consulte [Cómo: crear una aplicación Windows Forms desde la línea de comandos](how-to-create-a-windows-forms-application-from-the-command-line.md) y [controles que se usarán en Windows Forms](./controls/controls-to-use-on-windows-forms.md).  
  
2. Agregue una referencia al espacio de nombres <xref:Microsoft.Win32> al código.  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. Agregue el código siguiente al constructor del formulario para enlazar los controladores de eventos necesarios y para cambiar la fuente predeterminada en uso para el formulario.  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. Implemente un controlador para el evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> que hace que el formulario se escale automáticamente cuando cambie la categoría <xref:Microsoft.Win32.UserPreferenceCategory.Window>.  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. Por último, implemente un controlador para el evento <xref:System.Windows.Forms.Form.FormClosing> que desasocie el controlador de eventos <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.  
  
     > [!IMPORTANT]
     > Si no se incluye este código, la aplicación perderá memoria.  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. Compile y ejecute el código.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>Para cambiar manualmente la combinación de fuentes en Windows XP  
  
1. Mientras se ejecuta la aplicación Windows Forms, haga clic con el botón secundario en el escritorio de Windows y elija **propiedades** en el menú contextual.  
  
2. En el cuadro de diálogo **propiedades de pantalla** , haga clic en la pestaña **apariencia** .  
  
3. En el cuadro de lista desplegable **tamaño de fuente** , seleccione un nuevo tamaño de fuente.  
  
     Observará que el formulario ahora reacciona a los cambios en tiempo de ejecución en el esquema de fuentes del escritorio. Cuando el usuario cambia entre fuentes **normales**, **grandes**y **fuentes extra grandes**, el formulario cambia la fuente y se escala correctamente.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 El constructor de este ejemplo de código contiene una llamada a `InitializeComponent`, que se define al crear un nuevo proyecto de Windows Forms en Visual Studio. Quite esta línea de código si va a compilar la aplicación en la línea de comandos.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [Ajuste automático de escala en Windows Forms](automatic-scaling-in-windows-forms.md)
