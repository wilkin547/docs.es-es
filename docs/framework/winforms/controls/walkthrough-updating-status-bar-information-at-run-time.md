---
title: 'Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: 670746a1b964a85bc5136d976d831c6848466797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930983"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a>Tutorial: Actualizar la información de la barra de estado en tiempo de ejecución
> [!IMPORTANT]
> Los <xref:System.Windows.Forms.StatusStrip> controles <xref:System.Windows.Forms.ToolStripStatusLabel> y reemplazan y agregan funcionalidad <xref:System.Windows.Forms.StatusBar> a <xref:System.Windows.Forms.StatusBarPanel> los controles y; sin <xref:System.Windows.Forms.StatusBar> embargo <xref:System.Windows.Forms.StatusBarPanel> , los controles y se conservan por compatibilidad con versiones anteriores y uso futuro, si Elija.  
  
 Con frecuencia, un programa llamará para que actualice el contenido de los paneles de la barra de estado dinámicamente en tiempo de ejecución, en función de los cambios de estado de la aplicación u otra interacción del usuario. Se trata de una manera habitual de indicar a los usuarios que teclas tales como Bloq Mayús, Bloq Num o BLOQ DESPL están habilitadas o para proporcionar la fecha o un reloj como referencia cómoda.  
  
 En el ejemplo siguiente, utilizará una instancia de la <xref:System.Windows.Forms.StatusBarPanel> clase para hospedar un reloj.  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a>Para preparar la barra de estado para la actualización  
  
1. Cree un nuevo formulario Windows Forms.  
  
2. Agregue un control <xref:System.Windows.Forms.StatusBar> al formulario. Para obtener más detalles, vea [Cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
3. Agregue un panel de barra de estado <xref:System.Windows.Forms.StatusBar> al control. Para obtener más detalles, vea [Cómo: Agregue paneles a un control](how-to-add-panels-to-a-statusbar-control.md)StatusBar.  
  
4. Para el <xref:System.Windows.Forms.StatusBar> control que ha agregado al formulario, establezca la <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> propiedad en `true`.  
  
5. Agregue un componente <xref:System.Windows.Forms.Timer> de Windows Forms al formulario.  
  
    > [!NOTE]
    > El componente <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> de Windows Forms está diseñado para un entorno de Windows Forms. Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
6. Establezca la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `true`.  
  
7. Establezca la <xref:System.Windows.Forms.Timer.Interval%2A> propiedad <xref:System.Windows.Forms.Timer> de en 30000.  
  
    > [!NOTE]
    > La <xref:System.Windows.Forms.Timer.Interval%2A> propiedad<xref:System.Windows.Forms.Timer> del componente se establece en 30 segundos (30.000 milisegundos) para asegurarse de que se refleja una hora precisa en el tiempo mostrado.  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a>Para implementar el temporizador para que se actualice la barra de estado  
  
1. Inserte el código siguiente en el controlador de eventos del <xref:System.Windows.Forms.Timer> componente para actualizar el panel <xref:System.Windows.Forms.StatusBar> del control.  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     Ahora está listo para ejecutar la aplicación y observar el reloj en ejecución en el panel de la barra de estado.  
  
### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1. Depure la aplicación y presione F5 para ejecutarla. Para más detalles sobre la depuración, consulte [Depurar en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
    > [!NOTE]
    > El reloj tardará aproximadamente 30 segundos en aparecer en la barra de estado. El objetivo es obtener la hora más precisa posible. Por el contrario, para que el reloj aparezca antes, puede reducir el valor de la <xref:System.Windows.Forms.Timer.Interval%2A> propiedad que estableció en el paso 7 del procedimiento anterior.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Cómo: Agregar paneles a un control StatusBar](how-to-add-panels-to-a-statusbar-control.md)
- [Procedimientos: Determinar en qué panel del control Windows Forms StatusBar se hizo clic](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [Información general sobre StatusBar (Control)](statusbar-control-overview-windows-forms.md)
