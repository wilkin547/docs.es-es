---
title: Procedimiento Responder a los cambios de esquema de fuentes en una aplicación de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 4c34a65ed8ddabfb99451e055048502cb7617e4f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715976"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Filtrar Responder a los cambios de esquema de fuentes en una aplicación de Windows Forms
En los sistemas operativos Windows, un usuario puede cambiar la configuración de fuente de todo el sistema para que la fuente predeterminada aparezca mayor o menor. Cambiar esta configuración de fuente es fundamental para los usuarios que son personas con discapacidad visual y requieren un tipo mayor leer el texto en sus pantallas. Puede ajustar la aplicación de Windows Forms para reaccionar a estos cambios aumentando o reduciendo el tamaño del formulario y todo el texto cada vez que cambia el esquema de la fuente. Si desea que el formulario para adaptarse dinámicamente a cambios en los tamaños de fuente, puede agregar código al formulario.  
  
 Normalmente, la fuente predeterminada utilizada por Windows Forms es la fuente devuelta por la <xref:Microsoft.Win32> llamada del espacio de nombres a `GetStockObject(DEFAULT_GUI_FONT)`. La fuente devuelta por esta llamada sólo cambia cuando la resolución de pantalla. Como se muestra en el siguiente procedimiento, el código debe cambiar la fuente predeterminada para <xref:System.Drawing.SystemFonts.IconTitleFont%2A> para responder a cambios en el tamaño de fuente.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Para usar la fuente del escritorio y responder a los cambios de esquema de fuente  
  
1.  Cree el formulario y agregue los controles que desee a él. Para obtener más información, vea [Cómo: Crear una aplicación de Windows Forms desde la línea de comandos](how-to-create-a-windows-forms-application-from-the-command-line.md) y [controles que se utilizan en Windows Forms](./controls/controls-to-use-on-windows-forms.md).  
  
2.  Agregue una referencia a la <xref:Microsoft.Win32> espacio de nombres en el código.  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Agregue el código siguiente al constructor del formulario para enlazar controladores de eventos necesarios así como cambiar la fuente predeterminada utilizada para el formulario.  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Implementar un controlador para el <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> eventos que hace que el formulario escalar automáticamente cuando el <xref:Microsoft.Win32.UserPreferenceCategory.Window> cambios de categoría.  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Por último, implemente un controlador para el <xref:System.Windows.Forms.Form.FormClosing> eventos que separa el <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> controlador de eventos.  
  
     > [!IMPORTANT]
     > Error al incluir este código hará que la aplicación a una pérdida de memoria.  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  Compile y ejecute el código.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>Para cambiar manualmente la combinación de fuentes en Windows XP  
  
1.  Mientras se ejecuta la aplicación de Windows Forms, haga clic en el escritorio de Windows y elija **propiedades** en el menú contextual.  
  
2.  En el **las propiedades de presentación** cuadro de diálogo, haga clic en el **apariencia** ficha.  
  
3.  Desde el **Font Size** lista desplegable, seleccione un nuevo tamaño de fuente.  
  
     Observará que ahora el formulario responde a los cambios de tiempo de ejecución en el esquema de la fuente del escritorio. Cuando el usuario cambia entre **Normal**, **fuentes grandes**, y **fuentes muy grandes**, el formulario cambia la fuente y se escala correctamente.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 El constructor de este ejemplo de código contiene una llamada a `InitializeComponent`, que se define al crear un nuevo proyecto de Windows Forms en Visual Studio. Si va a compilar la aplicación en la línea de comandos, quite esta línea de código.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [Ajuste automático de escala en Windows Forms](automatic-scaling-in-windows-forms.md)
