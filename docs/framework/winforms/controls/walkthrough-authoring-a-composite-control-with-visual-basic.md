---
title: 'Tutorial: Crear un control compuesto con Visual Basic'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: 6404e5933f886578b4ad8afd0d3da324541fc3f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792254"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a>Tutorial: Crear un control compuesto con Visual Basic
Los controles compuestos proporcionan una forma de crear y reutilizar interfaces gráficas personalizadas. Un control compuesto es esencialmente un componente con una representación visual. Como tal, puede constar de uno o varios controles de Windows Forms, componentes o bloques de código que pueden extender funcionalidad al validar la entrada del usuario, modificar propiedades de presentación o realizar otras tareas requeridas por el autor. Los controles compuestos se pueden colocar en Windows Forms de la misma manera que otros controles. En la primera parte de este tutorial, creará un control compuesto simple denominado `ctlClock`. En la segunda parte, extenderá la funcionalidad de `ctlClock` mediante herencia.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y asegúrese de que el componente predeterminado estará en el espacio de nombres correcto.  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a>Para crear la biblioteca de controles ctlClockLib y el control ctlClock  
  
1. En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.  
  
2. En la lista de proyectos de Visual Basic, seleccione el **biblioteca de controles de Windows** plantilla de proyecto, escriba `ctlClockLib` en el **nombre** cuadro y, a continuación, haga clic en **Aceptar**.  
  
     El nombre del proyecto, `ctlClockLib` también se asigna de forma predeterminada al espacio de nombres raíz. El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado. Por ejemplo, si dos ensamblados proporcionan componentes denominados `ctlClock`, puede especificar su componente `ctlClock` mediante `ctlClockLib.ctlClock.`  
  
3. En el Explorador de soluciones, haga clic con el botón derecho en **UserControl1.vb** y haga clic en **Cambiar nombre**. Cambie el nombre del archivo a `ctlClock.vb`. Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".  
  
    > [!NOTE]
    >  De forma predeterminada, un control compuesto hereda el <xref:System.Windows.Forms.UserControl> clase proporcionada por el sistema. La <xref:System.Windows.Forms.UserControl> clase proporciona la funcionalidad requerida por todos los controles compuestos e implementa los métodos y propiedades estándar.  
  
4. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a>Agregar componentes y controles de Windows al control compuesto  
 Una interfaz visual es una parte esencial de su control compuesto. Esta interfaz visual se implementa agregando uno o más controles de Windows a la superficie del diseñador. En la demostración siguiente, incorporará controles de Windows al control compuesto y escribirá código para implementar funcionalidad.  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a>Para agregar una etiqueta y un temporizador al control compuesto  
  
1. En el Explorador de soluciones, haga clic con el botón derecho en **ctlClock.vb** y haga clic en **Ver diseñador**.  
  
2. En el cuadro de herramientas, expanda el nodo **Controles comunes** y haga doble clic en **Label**.  
  
     Un <xref:System.Windows.Forms.Label> control denominado `Label1` se agrega al control en la superficie del diseñador.  
  
3. En el diseñador, haga clic en **label1**. En la ventana Propiedades, establezca las propiedades siguientes.  
  
    |Property|Cambiar a|  
    |--------------|---------------|  
    |**Name**|`lblDisplay`|  
    |**Texto**|`(blank space)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4. En el **cuadro de herramientas**, expanda el nodo **Componentes** y haga doble clic en **Temporizador**.  
  
     Dado que un <xref:System.Windows.Forms.Timer> es un componente, no tiene representación visual en tiempo de ejecución. Por lo tanto, no aparece con los controles en la superficie del diseñador, sino en el Diseñador de componentes (una bandeja en la parte inferior de la superficie del diseñador).  
  
5. En el Diseñador de componentes, haga clic en **Timer1**y, a continuación, establezca el <xref:System.Windows.Forms.Timer.Interval%2A> propiedad `1000` y el <xref:System.Windows.Forms.Timer.Enabled%2A> propiedad `True`.  
  
     El <xref:System.Windows.Forms.Timer.Interval%2A> propiedad controla la frecuencia con la que el componente timer hace TIC. Cada vez que `Timer1` hace tic, se ejecuta el código en el evento `Timer1_Tick`. El intervalo representa el número de milisegundos entre tics.  
  
6. En el Diseñador de componentes, haga doble clic en **Timer1** para ir al evento `Timer1_Tick` de `ctlClock`.  
  
7. Modifique el código para que se parezca al siguiente ejemplo. Asegúrese de cambiar el modificador de acceso de `Private` a `Protected`.  
  
    ```vb  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     Este código hará que la hora actual se muestre en `lblDisplay`. Como el intervalo de `Timer1` se estableció en `1000`, este evento se producirá cada mil milisegundos, lo que actualiza la hora actual cada segundo.  
  
8. Modifique el método para que se pueda invalidar. Para más información, consulte la sección "Heredar de un control de usuario", más adelante.  
  
    ```vb  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## <a name="adding-properties-to-the-composite-control"></a>Agregar propiedades al control compuesto  
 El control de reloj encapsula ahora un <xref:System.Windows.Forms.Label> control y un <xref:System.Windows.Forms.Timer> componente, cada uno con su propio conjunto de propiedades inherentes. Aunque las propiedades individuales de estos controles no resultarán accesibles a los usuarios posteriores del control, puede crear y exponer propiedades personalizadas escribiendo los bloques de código adecuados. En el siguiente procedimiento, agregará al control propiedades que permiten al usuario cambiar el color de fondo y del texto.  
  
#### <a name="to-add-a-property-to-your-composite-control"></a>Para agregar una propiedad al control compuesto  
  
1. En el Explorador de soluciones, haga clic con el botón derecho en **ctlClock.vb** y haga clic en **Ver código**.  
  
     Se abre el Editor de código del control.  
  
2. Busque la instrucción `Public Class ctlClock`. Debajo de ella, escriba el siguiente código.  
  
    ```vb  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     Estas instrucciones crean las variables privadas que usará para almacenar los valores de las propiedades que va a crear.  
  
3. Inserte el código siguiente debajo de las declaraciones de variable del paso 2.  
  
    ```vb  
    ' Declares the name and type of the property.  
    Property ClockBackColor() as Color  
        ' Retrieves the value of the private variable colBColor.  
        Get  
            Return colBColor  
        End Get  
        ' Stores the selected value in the private variable colBColor, and   
        ' updates the background color of the label control lblDisplay.  
        Set(ByVal value as Color)  
            colBColor = value  
            lblDisplay.BackColor = colBColor     
        End Set  
  
    End Property  
    ' Provides a similar set of instructions for the foreground color.  
    Property ClockForeColor() as Color  
        Get  
            Return colFColor  
        End Get  
        Set(ByVal value as Color)  
            colFColor = value  
            lblDisplay.ForeColor = colFColor  
        End Set  
    End Property  
    ```  
  
     El código anterior crea dos propiedades personalizadas, `ClockForeColor` y `ClockBackColor`, que estarán disponibles para que posteriores usuarios de este control las invoquen mediante la instrucción `Property`. Las instrucciones `Get` y `Set` permiten almacenar y recuperar el valor de propiedad, además de proporcionar código para implementar funcionalidad adecuada para la propiedad.  
  
4. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## <a name="testing-the-control"></a>Probar el control  
 Los controles no son proyectos independientes; deben hospedarse en un contenedor. Pruebe el comportamiento en tiempo de ejecución del control y sus propiedades con **UserControl Test Container**. Para obtener más información, vea [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-your-control"></a>Para probar el control  
  
1. Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**.  
  
2. En la cuadrícula de propiedades del contenedor de prueba, seleccione la propiedad `ClockBackColor` y haga clic en la flecha desplegable para mostrar la paleta de colores.  
  
3. Haga clic en un color para elegirlo.  
  
     El color de fondo del control cambia al color seleccionado.  
  
4. Use una secuencia similar de eventos para comprobar que la propiedad `ClockForeColor` funciona según lo esperado.  
  
5. Haga clic en **Cerrar** para cerrar **UserControl Test Container**.  
  
     En esta sección y en las anteriores, ha visto cómo se pueden combinar componentes y controles de Windows con código y empaquetado para ofrecer funcionalidad personalizada en forma de control compuesto. Ha aprendido a exponer propiedades en el control compuesto y a probar el control una vez completado. En la siguiente sección, aprenderá a crear un control compuesto heredado utilizando `ctlClock` como base.  
  
## <a name="inheriting-from-a-composite-control"></a>Heredar de un control compuesto  
 En las secciones anteriores, ha aprendido a combinar controles de Windows, componentes y código en controles compuestos reutilizables. Ahora puede utilizar su control compuesto como base sobre la que crear otros controles. El proceso de derivar una clase a partir de una clase base se denomina *herencia*. En esta sección, creará un control de usuario denominado `ctlAlarmClock`. Este control se derivará de su control primario, `ctlClock`. Aprenderá a extender la funcionalidad de `ctlClock` reemplazando los métodos primarios y agregando nuevos métodos y propiedades.  
  
 El primer paso para crear un control heredado es derivarlo de su elemento primario. Esta acción crea un control que tiene todas las propiedades, los métodos y las características gráficas del control primario, pero que también puede servir de base para agregar funcionalidad nueva o modificada.  
  
#### <a name="to-create-the-inherited-control"></a>Para crear el control heredado  
  
1. En el Explorador de soluciones, haga clic con el botón derecho en **ctlClockLib**, elija **Agregar** y haga clic en **Control de usuario**.  
  
     Se abre el cuadro de diálogo **Agregar nuevo elemento**.  
  
2. Seleccione la plantilla **Control de usuario heredado**.  
  
3. En el cuadro **Nombre**, escriba `ctlAlarmClock.vb` y haga clic en **Agregar**.  
  
     Aparece el cuadro de diálogo **Selector de herencia**.  
  
4. En **Nombre de componente**, haga doble clic en **ctlClock**.  
  
5. En el Explorador de soluciones, examine los proyectos actuales.  
  
    > [!NOTE]
    >  Se ha agregado un archivo denominado **ctlAlarmClock.vb** al proyecto actual.  
  
### <a name="adding-the-alarm-properties"></a>Agregar las propiedades de alarma  
 Las propiedades se agregan a un control heredado de la misma forma que si fuera un control compuesto. Ahora utilizará la sintaxis de declaración de propiedades para agregar dos propiedades al control: `AlarmTime`, que almacenará el valor de la fecha y la hora en que debe activarse la alarma, y `AlarmSet`, que indicará si la alarma está definida.  
  
##### <a name="to-add-properties-to-your-composite-control"></a>Para agregar propiedades al control compuesto  
  
1. En el Explorador de soluciones, haga clic con el botón derecho en **ctlAlarmClock** y haga clic en **Ver código**.  
  
2. Busque la declaración de clase del control ctlAlarmClock, que aparece como `Public Class ctlAlarmClock`.  Inserte el siguiente código en la declaración de clase.  
  
    ```vb  
    Private dteAlarmTime As Date  
    Private blnAlarmSet As Boolean  
    ' These properties will be declared as Public to allow future   
    ' developers to access them.  
    Public Property AlarmTime() As Date  
        Get  
            Return dteAlarmTime  
        End Get  
        Set(ByVal value as Date)  
            dteAlarmTime = value  
        End Set  
    End Property  
    Public Property AlarmSet() As Boolean  
        Get  
            Return blnAlarmSet  
        End Get  
        Set(ByVal value as Boolean)  
            blnAlarmSet = value  
        End Set  
    End Property  
    ```  
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a>Agregar a la interfaz gráfica del control  
 El control heredado tiene una interfaz visual que es idéntica a la del control del que hereda. Posee los mismos controles constituyentes que su control primario, pero las propiedades de estos no estarán disponibles a menos que se expusieran específicamente. Puede agregar a la interfaz gráfica de un control compuesto heredado del mismo modo que agregaría a cualquier control compuesto. Para seguir agregando a la interfaz visual de su reloj despertador, agregará un control de etiqueta que parpadeará cuando suene la alarma.  
  
##### <a name="to-add-the-label-control"></a>Para agregar el control de etiqueta  
  
1. En el Explorador de soluciones, haga clic con el botón derecho en **ctlAlarmClock** y haga clic en **Ver diseñador**.  
  
     Se abre el diseñador para `ctlAlarmClock` en la ventana principal.  
  
2. Haga clic en `lblDisplay` (la parte de visualización del control) y observe la ventana Propiedades.  
  
    > [!NOTE]
    >  Aunque se muestran todas las propiedades, están atenuadas. Esto indica que estas propiedades son nativas de `lblDisplay` y no se pueden modificar ni se puede acceder a ellas en la ventana Propiedades. De forma predeterminada, los controles contenidos en un control compuesto son `Private`, y sus propiedades no son accesibles por ningún medio.  
  
    > [!NOTE]
    >  Si desea que los posteriores usuarios de su control compuesto tengan acceso a sus controles internos, declárelos como `Public` o `Protected`. Esto le permitirá establecer y modificar las propiedades de los controles contenidos en el control compuesto mediante el código adecuado.  
  
3. Agregar un <xref:System.Windows.Forms.Label> control al control compuesto.  
  
4. Con el mouse, arrastre el <xref:System.Windows.Forms.Label> control inmediatamente debajo del cuadro de visualización. En la ventana Propiedades, establezca las propiedades siguientes.  
  
    |Property|Parámetro|  
    |--------------|-------------|  
    |**Name**|`lblAlarm`|  
    |**Texto**|**¡Alarma!**|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visible**|`False`|  
  
### <a name="adding-the-alarm-functionality"></a>Agregar la funcionalidad de alarma  
 En los procedimientos anteriores, agregó propiedades y un control que habilitará la funcionalidad de alarma en el control compuesto. En este procedimiento, agregará código para comparar la hora actual con la hora de la alarma y, si son iguales, hacer que parpadee y suene una alarma. Al reemplazar el método `Timer1_Tick` de `ctlClock` y agregarle código adicional, extenderá la funcionalidad de `ctlAlarmClock` al mismo tiempo que conserva toda la funcionalidad inherente de `ctlClock`.  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a>Para reemplazar el método Timer1_Tick de ctlClock  
  
1. En el Explorador de soluciones, haga clic con el botón derecho en **ctlAlarmClock.vb** y haga clic en **Ver código**.  
  
2. Busque la instrucción `Private blnAlarmSet As Boolean`. Justo debajo de ella, agregue la siguiente instrucción.  
  
    ```vb  
    Dim blnColorTicker as Boolean  
    ```  
  
3. Busque la instrucción `End Class` en la parte inferior de la página. Justo antes de la instrucción `End Class`, agregue el código siguiente.  
  
    ```vb  
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _  
        As System.EventArgs)  
        ' Calls the Timer1_Tick method of ctlClock.  
        MyBase.Timer1_Tick(sender, e)  
        ' Checks to see if the Alarm is set.  
        If AlarmSet = False Then  
            Exit Sub  
        End If  
        ' If the date, hour, and minute of the alarm time are the same as  
        ' now, flash and beep an alarm.   
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _  
            AlarmTime.Minute = Now.Minute Then  
            ' Sounds an audible beep.  
            Beep()  
            ' Sets lblAlarmVisible to True, and changes the background color based on the   
            ' value of blnColorTicker. The background color of the label will   
            ' flash once per tick of the clock.  
            lblAlarm.Visible = True  
            If blnColorTicker = False Then  
                lblAlarm.BackColor = Color.PeachPuff  
                blnColorTicker = True  
            Else  
                lblAlarm.BackColor = Color.Plum  
                blnColorTicker = False  
            End If  
        Else  
            ' Once the alarm has sounded for a minute, the label is made   
            ' invisible again.  
            lblAlarm.Visible = False  
        End If  
    End Sub  
    ```  
  
     Con la adición de este código, se llevan a cabo varias tareas. La instrucción `Overrides` indica al control que utilice este método en lugar del que heredó del control base. Cuando se llama a este método, llama al método que reemplaza invocando la instrucción `MyBase.Timer1_Tick`, lo que garantiza que toda la funcionalidad incorporada en el control original se reproduzca en este control. A continuación, ejecuta código adicional para incorporar la funcionalidad de alarma. Aparecerá un control de etiqueta parpadeante cuando se active la alarma, y se oirá un pitido.  
  
    > [!NOTE]
    >  Dado que va a reemplazar un controlador de eventos heredado, no es necesario especificar el evento con la palabra clave `Handles`. El evento ya está enlazado. Lo que se va a reemplazar es la implementación del controlador.  
  
     El control de reloj despertador está casi completado. Lo único que queda es implementar una forma de desactivarlo. Para ello, agregará código al método `lblAlarm_Click`.  
  
##### <a name="to-implement-the-shutoff-method"></a>Para implementar el método de apagado  
  
1. En el Explorador de soluciones, haga clic con el botón derecho en **ctlAlarmClock.vb** y haga clic en **Ver diseñador**.  
  
2. En el diseñador, haga doble clic en **lblAlarm**. Se abre el **Editor de código** en la línea `Private Sub lblAlarm_Click`.  
  
3. Modifique este método para que se parezca al siguiente código.  
  
    ```vb  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
### <a name="using-the-inherited-control-on-a-form"></a>Usar el control heredado en un formulario  
 Puede probar el control heredado de la misma manera que se ha probado el control de la clase base, `ctlClock`: Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**. Para obtener más información, vea [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Para utilizar el control, debe hospedarlo en un formulario. Al igual que con los controles compuestos estándar, los controles compuestos heredados no son independientes y deben hospedarse en un formulario o en otro contenedor. Puesto que `ctlAlarmClock` tiene un mayor grado de funcionalidad, se necesita código adicional para probarlo. En este procedimiento, escribirá un programa sencillo para probar la funcionalidad de `ctlAlarmClock`. Escribirá código para establecer y mostrar la propiedad `AlarmTime` de `ctlAlarmClock` y probar sus funciones inherentes.  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a>Para compilar y agregar el control a un formulario de prueba  
  
1. En el Explorador de soluciones, haga clic con el botón derecho en **ctlClockLib** y haga clic en **Compilar**.  
  
2. En el menú **Archivo** , apunte a **Agregar**y haga clic en **Nuevo proyecto**.  
  
3. Agregue un nuevo proyecto **Aplicación Windows** a la solución y asígnele el nombre `Test`.  
  
     Se crea el proyecto **Test** y se agrega al Explorador de soluciones.  
  
4. En el Explorador de soluciones, haga clic con el botón derecho en el nodo de proyecto `Test` y, después, haga clic en **Agregar referencia** para mostrar el cuadro de diálogo **Agregar referencia**.  
  
5. Haga clic en la pestaña etiquetada como **Proyectos**. El proyecto **ctlClockLib** aparecerá en **Nombre de proyecto**. Haga doble clic en **ctlClockLib** para agregar la referencia al proyecto de prueba.  
  
6. En el Explorador de soluciones, haga clic con el botón derecho en **Probar** y haga clic en **Compilar**.  
  
7. En el **cuadro de herramientas**, expanda el nodo **Componentes de ctlClockLib**.  
  
8. Haga doble clic en **ctlAlarmClock** para agregar una instancia de `ctlAlarmClock` al formulario.  
  
9. En el **cuadro de herramientas**, busque y haga doble clic en **DateTimePicker** para agregar un <xref:System.Windows.Forms.DateTimePicker> control al formulario y, a continuación, agregue un <xref:System.Windows.Forms.Label> control haciendo doble clic en **etiqueta**.  
  
10. Use el mouse para colocar los controles en un lugar adecuado en el formulario.  
  
11. Establezca las propiedades de estos controles de la manera siguiente.  
  
    |Control|Propiedad|Valor|  
    |-------------|--------------|-----------|  
    |`label1`|**Texto**|`(blank space)`|  
    ||**Name**|`lblTest`|  
    |`dateTimePicker1`|**Name**|`dtpTest`|  
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
12. En el diseñador, haga doble clic en **dtpTest**.  
  
     Se abre el **Editor de código** en `Private Sub dtpTest_ValueChanged`.  
  
13. Modifique el código para que se parezca al siguiente.  
  
    ```vb  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. En el Explorador de soluciones, haga clic con el botón derecho en **Probar** y haga clic en **Establecer como proyecto de inicio**.  
  
15. En el menú **Depurar**, haga clic en **Iniciar depuración**.  
  
     Se inicia el programa de prueba. Tenga en cuenta que la hora actual se actualiza en el `ctlAlarmClock` control y que se muestra la hora de inicio en el <xref:System.Windows.Forms.DateTimePicker> control.  
  
16. Haga clic en el <xref:System.Windows.Forms.DateTimePicker> donde se muestran los minutos de la hora.  
  
17. Use el teclado para establecer el valor de los minutos en un minuto más tarde que la hora actual mostrada por `ctlAlarmClock`.  
  
     La hora para la configuración de alarma se muestra en `lblTest`. Espere a que la hora mostrada llegue a la hora de la alarma configurada. Cuando la hora que se muestra llegue a la hora en que está puesta la alarma, se oirá un pitido y `lblAlarm` parpadeará.  
  
18. Para desactivar la alarma, haga clic en `lblAlarm`. Ahora puede restablecer la alarma.  
  
     En este tutorial se han tratado varios conceptos clave. Ha aprendido a crear un control compuesto mediante la combinación de controles y componentes en un contenedor de control compuesto. Ha aprendido a agregar propiedades al control y a escribir código para implementar funcionalidad personalizada. En la última sección, ha aprendido a extender la funcionalidad de un control compuesto determinado mediante herencia y a modificar la funcionalidad de los métodos de host reemplazando estos últimos.  
  
## <a name="see-also"></a>Vea también

- [Variedades de controles personalizados](varieties-of-custom-controls.md)
- [Cómo: Crear controles compuestos](how-to-author-composite-controls.md)
- [Cómo: Mostrar un Control en la elija el cuadro de diálogo de elementos de cuadro de herramientas](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
