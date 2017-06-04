---
title: "Tutorial: Crear un control compuesto con Visual Basic | Microsoft Docs"
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
  - "controles compuestos, crear"
  - "controles [Windows Forms], controles compuestos"
  - "controles personalizados [Visual Basic]"
  - "controles personalizados [Windows Forms], crear"
  - "controles de usuario [Visual Basic]"
  - "controles de usuario [Windows Forms], crear con Visual Basic"
  - "UserControl (clase), tutoriales"
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Tutorial: Crear un control compuesto con Visual Basic
Los controles compuestos proporcionan un medio para crear y reutilizar interfaces gráficas personalizadas.  Un control compuesto es esencialmente un componente con una representación visual.  Como tal, puede constar de uno o más controles de formularios Windows Forms, componentes o bloques de código, que pueden extender su funcionalidad mediante la validación de la entrada del usuario, la modificación de las propiedades de presentación o la ejecución de otras tareas requeridas por su autor.  Los controles compuestos se pueden colocar en formularios Windows Forms del mismo modo que otros controles.  En la primera parte del tutorial, creará un control de usuario sencillo denominado `ctlClock`.  En la segunda parte del tutorial, ampliará la funcionalidad de `ctlClock` a través de herencia.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 Cuando cree un nuevo proyecto, debe establecer el espacio de nombres de la raíz, el nombre de ensamblado y el de proyecto, además de asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.  
  
#### Para crear la biblioteca de controles ctlClockLib y el control ctlClock  
  
1.  En el menú **Archivo**, elija **Nuevo** y, a continuación, haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.  
  
2.  En la lista de proyectos de [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], seleccione la plantilla de proyectos **Biblioteca de controles de Windows**, escriba `ctlClockLib` en el cuadro **Nombre** y, a continuación, haga clic en **Aceptar**.  
  
     El nombre del proyecto, `ctlClockLib`, se asigna también de forma predeterminada al espacio de nombres de la raíz.  El espacio de nombres de la raíz se utiliza para calificar los nombres de los componentes del ensamblado.  Por ejemplo, si dos ensamblados proporcionan componentes denominados `ctlClock`, puede especificar el componente `ctlClock` mediante `ctlClockLib.ctlClock.` .  
  
3.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **UserControl1.vb** y haga clic en **Cambiar nombre**.  Cambie el nombre de archivo a `ctlClock.vb`.  Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".  
  
    > [!NOTE]
    >  De forma predeterminada, un control compuesto hereda de la clase <xref:System.Windows.Forms.UserControl> proporcionada por el sistema.  La clase <xref:System.Windows.Forms.UserControl> proporciona la funcionalidad necesaria para todos los controles de usuario e implementa métodos y propiedades estándar.  
  
4.  En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## Agregar controles y componentes de Windows al control compuesto  
 Una parte esencial del control compuesto es una interfaz visual.  Esta interfaz visual se implementa mediante la adición de uno o más controles de Windows a la superficie del diseñador.  En la demostración siguiente, incorporará controles de Windows al control compuesto y escribirá código para implementar funcionalidad.  
  
#### Para agregar un control Label y un componente Timer al control compuesto  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlClock.vb** y haga clic en **Diseñador de vistas**.  
  
2.  En el Cuadro de herramientas, expanda el nodo **Controles comunes** y, a continuación, haga doble clic en **Label**.  
  
     Un control <xref:System.Windows.Forms.Label> denominado `Label1` se agrega al control en la superficie del diseñador.  
  
3.  En el diseñador, haga clic en **Label1**.  En la ventana Propiedades, establezca las propiedades siguientes:  
  
    |Propiedad.|Cambie a|  
    |----------------|--------------|  
    |**Name**|`lblDisplay`|  
    |**Text**|`(espacio en blanco)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4.  En el **Cuadro de herramientas**, expanda el nodo **Componentes** y, a continuación, haga doble clic en el componente **Timer**.  
  
     Dado que <xref:System.Windows.Forms.Timer> es un componente, no tiene representación visual en tiempo de ejecución.  Por tanto, no aparece con los controles en la superficie del diseñador, sino en el Diseñador de componentes \(una bandeja situada en la parte inferior de la superficie del diseñador\).  
  
5.  En el Diseñador de componentes, haga clic en **timer1** y, a continuación, establezca la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> en `1000` y la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `True`.  
  
     La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> controla la frecuencia con la que se incrementa el valor del componente temporizador.  Cada vez que `Timer1` marca un paso, ejecuta el código del evento `Timer1_Tick`.  El intervalo representa el número de milisegundos entre paso y paso.  
  
6.  En el Diseñador de componentes, haga doble clic en **Timer1** para ir al evento `Timer1_Tick` de `ctlClock`.  
  
7.  Modifique el código de modo que se asemeje al siguiente ejemplo:  Asegúrese de cambiar el modificador de acceso de `Private` a `Protected`.  
  
     \[Visual Basic\]  
  
    ```  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     Este código hace que se muestre la hora actual en `lblDisplay`.  Dado que el intervalo de `Timer1` se estableció en `1000`, este evento se activará cada mil milisegundos, por lo que la hora se actualizará cada segundo.  
  
8.  Modifique el método para que pueda reemplazarse.  Para obtener más información, vea la sección siguiente "Heredar de un control de usuario".  
  
     \[Visual Basic\]  
  
    ```  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## Agregar propiedades al control compuesto  
 El control de reloj encapsula ahora un control <xref:System.Windows.Forms.Label> y un componente <xref:System.Windows.Forms.Timer>, cada uno con su propio conjunto de propiedades inherentes.  Aunque las propiedades individuales de estos controles no estarán disponibles para los futuros usuarios del control, puede crear y exponer propiedades personalizadas escribiendo los bloques de código adecuados.  En el procedimiento siguiente, agregará al control propiedades que permiten que el usuario cambie el color del fondo y del texto.  
  
#### Para agregar una propiedad al control compuesto  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlClock.vb** y haga clic en **Ver código**.  
  
     Se abrirá el Editor de código para el control.  
  
2.  Busque la instrucción `Public Class ctlClock`.  A continuación, escriba el código siguiente:  
  
     \[Visual Basic\]  
  
    ```  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     Estas instrucciones crean las variables privadas que se utilizarán para almacenar los valores de las propiedades que va a crear.  
  
3.  Inserte el código siguiente bajo las declaraciones de variables del paso 2.  
  
     \[Visual Basic\]  
  
    ```  
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
  
     El código precedente crea dos propiedades personalizadas, `ClockForeColor` y `ClockBackColor`, que permiten el acceso a los usuarios del control por medio de la invocación a la instrucción `Property`.  Las instrucciones `Get` y `Set` permiten el almacenamiento y la recuperación del valor de propiedad; además, proporcionan el código necesario para implementar la funcionalidad adecuada para la propiedad.  
  
4.  En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## Probar el control  
 Los controles no son proyectos independientes; deben hospedarse en un contenedor.  Pruebe el comportamiento del control en tiempo de ejecución y pruebe sus propiedades con el **UserControl Test Container**.  Para obtener más información, vea [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### Para probar el control  
  
1.  Presione F5 para compilar el proyecto y ejecutar el control en el **UserControl Test Container**.  
  
2.  En la cuadrícula de propiedades del contenedor de prueba, seleccione la propiedad `ClockBackColor` y haga clic en la flecha de la lista desplegable para mostrar la paleta de color.  
  
3.  Haga doble clic en un color para elegirlo.  
  
     El color de fondo del control cambiará al color seleccionado.  
  
4.  Utilice una secuencia de eventos similar para comprobar que la propiedad `ClockForeColor` funciona como se esperaba.  
  
5.  Haga clic en **Cerrar** para cerrar la ventana **UserControl Test Container**.  
  
     En esta sección y en las secciones anteriores, vio cómo se pueden combinar componentes y controles de Windows con código y empaquetamiento para ofrecer funcionalidad personalizada en forma de control de usuario.  Aprendió a exponer propiedades en el control compuesto, así como a probar el control una vez terminado.  En la siguiente sección, aprenderá a construir un control de usuario heredado utilizando `ctlClock` como base.  
  
## Heredar de un control compuesto  
 En las secciones anteriores, aprendió a combinar controles de Windows, componentes y código en controles de usuario reutilizables.  Ahora puede utilizar el control compuesto como base a partir de la cual se compilarán otros controles.  El proceso de derivación de una clase a partir de una clase base se denomina *herencia*.  En esta sección, creará un control de usuario denominado `ctlAlarmClock`.  Este control se derivará de su control principal, `ctlClock`.  Aprenderá a ampliar la funcionalidad de `ctlClock` reemplazando los métodos principales y agregando métodos y propiedades nuevos.  
  
 El primer paso para crear un control heredado es derivarlo de su control primario.  Esta acción crea un nuevo control que tiene todas las propiedades, métodos y características gráficas del control primario, pero que también actúa como base para la adición de funcionalidad nueva o modificada.  
  
#### Para crear el control heredado  
  
1.  En el **Explorador de soluciones**, haga clic en el proyecto con el botón secundario del mouse, elija **Agregar** y haga clic en **Control de usuario**.  
  
     Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
2.  Seleccione la plantilla **Control de usuario heredado**.  
  
3.  En el cuadro **Nombre**, escriba `ctlAlarmClock.vb` y haga clic en **Agregar**.  
  
     Aparece el cuadro de diálogo **Selector de herencia**.  
  
4.  En **Nombre de componente**, haga doble clic en **ctlClock**.  
  
5.  En el Explorador de soluciones, examine los proyectos actuales.  
  
    > [!NOTE]
    >  Se ha agregado un archivo denominado **ctlAlarmClock.vb** al proyecto actual.  
  
### Agregar propiedades de alarma  
 Las propiedades se agregan a un control heredado del mismo modo que se agregan a un control compuesto.  Ahora utilizará la sintaxis de declaración de propiedades para agregar dos propiedades al control: `AlarmTime`, que almacenará el valor de fecha y hora en que se activará la alarma y `AlarmSet`, que indica si está establecida o no la alarma.  
  
##### Para agregar propiedades al control compuesto  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlAlarmClock** y, a continuación, haga clic en **Ver código**.  
  
2.  Busque la declaración de clase del control ctlAlarmClock, que aparece como `Public Class ctlAlarmClock`.  En la declaración de clase, inserte el código siguiente.  
  
     \[Visual Basic\]  
  
    ```  
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
  
### Agregar a la interfaz gráfica del control  
 El control heredado tiene una interfaz visual que es idéntica a la del control del que se hereda.  Posee los mismos controles constituyentes que su control primario, pero las propiedades de los controles constituyentes no estarán disponibles a menos que se expongan de manera específica.  Puede agregar a la interfaz gráfica de un control compuesto heredado del mismo modo que agregaría a cualquier control compuesto.  Para continuar agregando a la interfaz visual de su reloj de alarma, agregará un control Label que parpadeará cuando esté sonando la alarma.  
  
##### Para agregar el control Label  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlAlarmClock** y, a continuación, haga clic en **Ver diseñador**.  
  
     Aparecerá el diseñador de `ctlAlarmClock` en la ventana principal.  
  
2.  Haga clic en `lblDisplay` \(la zona de presentación del control\) y observe la ventana Propiedades.  
  
    > [!NOTE]
    >  Observe que, aunque se muestran todas las propiedades, están atenuadas.  Esto indica que estas propiedades son nativas de `lblDisplay` y no se pueden modificar ni se puede tener acceso a ellas en la ventana Propiedades.  De manera predeterminada, los controles contenidos en un control compuesto son `Private` y no se puede tener acceso a sus propiedades de ningún modo.  
  
    > [!NOTE]
    >  Si desea que los futuros usuarios del control de usuario tengan acceso a los controles internos, declárelos como `Public` o `Protected`.  Esto le permitirá establecer y modificar las propiedades de los controles contenidos en el control compuesto, mediante el código adecuado.  
  
3.  Agregue el control <xref:System.Windows.Forms.Label> al control compuesto.  
  
4.  Con el mouse, mueva el control <xref:System.Windows.Forms.Label> justo debajo del cuadro de vista.  En la ventana Propiedades, establezca las propiedades siguientes:  
  
    |Propiedad.|Configuración|  
    |----------------|-------------------|  
    |**Name**|`lblAlarm`|  
    |**Text**|¡Alarma\!|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visible**|`False`|  
  
### Agregar la funcionalidad de alarma  
 En los procedimientos anteriores, agregó propiedades y un control que habilitará la funcionalidad de alarma en el control compuesto.  En este procedimiento, agregará código para comparar la hora actual con la hora de alarma y, si son iguales, hacer que suene y parpadee una alarma.  Al anular el método `Timer1_Tick` de `ctlClock` y agregar código adicional en él, ampliará la capacidad de `ctlAlarmClock` mientras conserva toda la funcionalidad inherente de `ctlClock`.  
  
##### Para reemplazar el método Timer1\_Tick de ctlClock  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlAlarmClock.vb** y haga clic en **Ver código**.  
  
2.  Busque la instrucción `Private blnAlarmSet As Boolean`.  Justo después, agregue la siguiente instrucción.  
  
     \[Visual Basic\]  
  
    ```  
    Dim blnColorTicker as Boolean  
    ```  
  
3.  Busque la instrucción `End Class` en la parte inferior de la página.  Inmediatamente antes de la instrucción `End Class`, agregue el código siguiente:  
  
     \[Visual Basic\]  
  
    ```  
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
  
     Al agregar este código se realizan varias tareas.  La instrucción `Overrides` indica al control que utilice este método en lugar del método heredado del control base.  Cuando se llama a este método, éste llama al que reemplaza al invocar la instrucción `MyBase.Timer1_Tick`; de este modo, se asegura que toda la funcionalidad incorporada en el control original se reproduzca en este control.  A continuación, ejecuta código adicional para incorporar la funcionalidad de la alarma.  Cuando suena la alarma, aparece un control de etiqueta intermitente y se oye un sonido.  
  
    > [!NOTE]
    >  Observe que desde que reemplaza un controlador de eventos heredado, no tiene que especificar el evento con la palabra clave `Handles`.  El evento ya está enlazado.  Lo único que reemplaza es la implementación del controlador.  
  
     El control de reloj de alarma está casi completo.  Lo único que queda es implementar un medio para desactivarlo.  Para ello, agregará el código al método `lblAlarm_Click`.  
  
##### Para implementar el método de apagado  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlAlarmClock.vb** y haga clic en **Ver diseñador**.  
  
2.  En el diseñador, haga doble clic en **lblAlarm**.  Se abrirá el **Editor de código** en la línea `Private Sub lblAlarm_Click`.  
  
3.  Modifique este método de forma que se asemeje al código siguiente.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4.  En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
### Utilizar el control heredado en un formulario  
 Puede probar el control heredado de la misma forma que probó el control de la clase base, `ctlClock`: presione F5 para compilar el proyecto y ejecute el control en **UserControl Test Container**.  Para obtener más información, vea [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Para colocar el control para su uso, tendrá que hospedarlo en un formulario.  Como ocurre con los controles compuestos estándar, los controles compuestos heredados no son independientes y deben hospedarse en un formulario o en otro contenedor.  Puesto que `ctlAlarmClock` ofrece una funcionalidad más profunda, será necesario código adicional para probarlo.  En esta sección, escribirá un programa sencillo para probar la funcionalidad de `ctlAlarmClock`.  Escribirá código para definir y mostrar la propiedad `AlarmTime` de `ctlAlarmClock` y probar sus funciones heredadas.  
  
##### Para compilar y agregar el control a un formulario de prueba  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlClockLib** y haga clic en **Compilar**.  
  
2.  En el menú **Archivo**, elija **Agregar** y, después, haga clic en **Nuevo proyecto**.  
  
3.  Agregue un nuevo proyecto de **Aplicación para Windows** a la solución y denomínelo `Test`.  
  
     El proyecto **Test** se agrega al Explorador de soluciones.  
  
4.  En Explorador de soluciones, haga clic con el botón secundario del mouse en el nodo de proyecto `Test` y, a continuación, haga clic en **Agregar referencia** para mostrar el cuadro de diálogo **Agregar referencia**.  
  
5.  Haga clic en la ficha **Proyectos**.  Aparecerá **ctlClockLib** en la lista **Nombre de proyecto**.  Haga doble clic en **ctlClockLib** para agregar la referencia al proyecto de prueba.  
  
6.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **Test** y haga clic en **Compilar**.  
  
7.  En el **Cuadro de herramientas**, expanda el nodo **Componentes de ctlClockLib**.  
  
8.  Haga doble clic en **ctlAlarmClock** para agregar una instancia de `ctlAlarmClock` al formulario.  
  
9. En el **Cuadro de herramientas**, busque y haga doble clic en **DateTimePicker** para agregar un control <xref:System.Windows.Forms.DateTimePicker> al formulario; a continuación, haga doble clic en **Label** para agregar un control <xref:System.Windows.Forms.Label>.  
  
10. Utilice el mouse para colocar los controles en un lugar apropiado del formulario.  
  
11. Establezca las propiedades de estos controles de la manera siguiente.  
  
    |Control|Propiedad.|Valor|  
    |-------------|----------------|-----------|  
    |`label1`|**Text**|`(espacio en blanco)`|  
    ||**Name**|`lblTest`|  
    |`dateTimePicker1`|**Name**|`dtpTest`|  
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat>|  
  
12. En el diseñador, haga doble clic en **dtpTest**.  
  
     El **Editor de código** se abrirá en `Private Sub dtpTest_ValueChanged`.  
  
13. Modifique el código de modo que se asemeje a lo siguiente.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. En el Explorador de soluciones, haga clic con el botón secundario del mouse en **Test** y, a continuación, en **Establecer como proyecto de inicio**.  
  
15. En el menú **Depurar**, haga clic en **Iniciar depuración**.  
  
     Se iniciará el programa de prueba.  Observe que la hora actual se actualiza en el control `ctlAlarmClock` y que la hora de inicio se muestra en el control <xref:System.Windows.Forms.DateTimePicker>.  
  
16. Haga clic en <xref:System.Windows.Forms.DateTimePicker> donde se muestran los minutos.  
  
17. Con el uso del teclado, defina un valor para los minutos que sea un minuto más que la hora actual que muestra `ctlAlarmClock`.  
  
     La hora de la configuración de la alarma se muestra en `lblTest`.  Espere a que la hora que se muestra alcance la hora establecida para la alarma.  Cuando la hora que se muestra alcance la hora establecida para la alarma, sonará el tono y parpadeará `lblAlarm`.  
  
18. Para desactivar la alarma, haga clic en `lblAlarm`.  Ahora puede reiniciar la alarma.  
  
     Este tutorial trataba varios conceptos clave.  Aprendió a crear un control compuesto mediante la combinación de controles y componentes en un contenedor de control compuesto.  Aprendió a agregar propiedades al control y a escribir código para implementar funcionalidades personalizadas.  En la última sección aprendió a extender la funcionalidad de un control compuesto mediante herencia, y a modificar la funcionalidad de los métodos hospedados reemplazando estos últimos.  
  
## Vea también  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Cómo: Crear controles compuestos](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)   
 [Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)   
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)