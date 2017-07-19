---
title: "Tutorial: Crear un control compuesto con Visual C# | Microsoft Docs"
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
  - "controles personalizados [C#]"
  - "controles personalizados [Windows Forms], crear"
  - "controles de usuario [C#]"
  - "controles de usuario [Windows Forms], crear con Visual C#"
  - "UserControl (clase), tutoriales"
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Tutorial: Crear un control compuesto con Visual C# #
Los controles compuestos proporcionan un medio para crear y reutilizar interfaces gráficas personalizadas.  Un control compuesto es esencialmente un componente con una representación visual.  Como tal, puede constar de uno o más controles de formularios Windows Forms, componentes o bloques de código, que pueden extender su funcionalidad mediante la validación de la entrada del usuario, la modificación de las propiedades de presentación o la ejecución de otras tareas requeridas por su autor.  Los controles compuestos se pueden colocar en formularios Windows Forms del mismo modo que otros controles.  En la primera parte del tutorial, creará un control de usuario sencillo denominado `ctlClock`.  En la segunda parte del tutorial, ampliará la funcionalidad de `ctlClock` a través de herencia.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 Cuando cree un nuevo proyecto, debe establecer el espacio de nombres de la raíz, el nombre de ensamblado y el de proyecto, además de asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.  
  
#### Para crear la biblioteca de controles ctlClockLib y el control ctlClock  
  
1.  En el menú **Archivo**, elija **Nuevo** y, a continuación, haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.  
  
2.  En la lista de proyectos de [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], seleccione la plantilla de proyecto **Biblioteca de controles de Windows Forms**, escriba `ctlClockLib` en el cuadro **Nombre** y, a continuación, haga clic en **Aceptar**.  
  
     El nombre del proyecto, `ctlClockLib`, se asigna también de forma predeterminada al espacio de nombres de la raíz.  El espacio de nombres de la raíz se utiliza para calificar los nombres de los componentes del ensamblado.  Por ejemplo, si dos ensamblados proporcionan componentes denominados `ctlClock`, puede especificar el componente `ctlClock` mediante `ctlClockLib.ctlClock.` .  
  
3.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **UserControl1.jsl** y haga clic en **Cambiar nombre**.  Cambie el nombre de archivo a `ctlClock.cs`.  Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".  
  
    > [!NOTE]
    >  De forma predeterminada, un control compuesto hereda de la clase <xref:System.Windows.Forms.UserControl> proporcionada por el sistema.  La clase <xref:System.Windows.Forms.UserControl> proporciona la funcionalidad necesaria para todos los controles de usuario e implementa métodos y propiedades estándar.  
  
4.  En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## Agregar controles y componentes de Windows al control compuesto  
 Una parte esencial del control compuesto es una interfaz visual.  Esta interfaz visual se implementa mediante la adición de uno o más controles de Windows a la superficie del diseñador.  En la demostración siguiente, incorporará controles de Windows al control compuesto y escribirá código para implementar funcionalidad.  
  
#### Para agregar un control Label y un componente Timer al control compuesto  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlClock.cs** y haga clic en **Diseñador de vistas**.  
  
2.  En el **Cuadro de herramientas**, expanda el nodo **Controles comunes** y, a continuación, haga doble clic en **Label**.  
  
     Un control <xref:System.Windows.Forms.Label> denominado `label1` se agrega al control en la superficie del diseñador.  
  
3.  En el diseñador, haga clic en **label1**.  En la ventana Propiedades, establezca las propiedades siguientes:  
  
    |Propiedad.|Cambie a|  
    |----------------|--------------|  
    |**Name**|`lblDisplay`|  
    |**Text**|`(espacio en blanco)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4.  En el **Cuadro de herramientas**, expanda el nodo **Componentes** y, a continuación, haga doble clic en el componente **Timer**.  
  
     Dado que <xref:System.Windows.Forms.Timer> es un componente, no tiene representación visual en tiempo de ejecución.  Por tanto, no aparece con los controles en la superficie del diseñador, sino en el **Diseñador de componentes** \(una bandeja situada en la parte inferior de la superficie del diseñador\).  
  
5.  En el **Diseñador de componentes**, haga clic en **timer1** y, a continuación, establezca la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> en `1000` y la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `true`.  
  
     La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> controla la frecuencia con la que se incrementa el valor del componente <xref:System.Windows.Forms.Timer>.  Cada vez que `timer1` marca un paso, ejecuta el código del evento `timer1_Tick`.  El intervalo representa el número de milisegundos entre paso y paso.  
  
6.  En el **Diseñador de componentes**, haga doble clic en **Timer1** para ir al evento `timer1_Tick` de `ctlClock`.  
  
7.  Modifique el código de modo que se asemeje al siguiente ejemplo:  Asegúrese de cambiar el modificador de acceso de `private` a `protected`.  
  
     \[C\#\]  
  
    ```  
    protected void timer1_Tick(object sender, System.EventArgs e)  
    {  
        // Causes the label to display the current time.  
        lblDisplay.Text = DateTime.Now.ToLongTimeString();   
    }  
    ```  
  
     Este código hace que se muestre la hora actual en `lblDisplay`.  Dado que el intervalo de `timer1` se estableció en `1000`, este evento se producirá cada mil milisegundos, por lo que la hora se actualizará cada segundo.  
  
8.  Modifique el método para que pueda reemplazarse, mediante la palabra clave `virtual`.  Para obtener más información, vea la sección siguiente "Heredar de un control de usuario".  
  
    ```  
    protected virtual void timer1_Tick(object sender, System.EventArgs e)  
    ```  
  
9. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## Agregar propiedades al control compuesto  
 El control de reloj encapsula ahora un control <xref:System.Windows.Forms.Label> y un componente <xref:System.Windows.Forms.Timer>, cada uno con su propio conjunto de propiedades inherentes.  Aunque las propiedades individuales de estos controles no estarán disponibles para los futuros usuarios del control, puede crear y exponer propiedades personalizadas escribiendo los bloques de código adecuados.  En el procedimiento siguiente, agregará al control propiedades que permiten que el usuario cambie el color del fondo y del texto.  
  
#### Para agregar una propiedad al control compuesto  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlClock.cs** y haga clic en **Ver código**.  
  
     Se abrirá el **Editor de código** para el control.  
  
2.  Busque la instrucción `public partial class ctlClock`.  Bajo la llave de apertura \(`{)`, escriba el código siguiente.  
  
     \[C\#\]  
  
    ```  
    private Color colFColor;  
    private Color colBColor;  
    ```  
  
     Estas instrucciones crean las variables privadas que se utilizarán para almacenar los valores de las propiedades que va a crear.  
  
3.  Escriba el código siguiente bajo las declaraciones de variables del paso 2:  
  
     \[C\#\]  
  
    ```  
    // Declares the name and type of the property.  
    public Color ClockBackColor  
    {  
        // Retrieves the value of the private variable colBColor.  
        get  
        {  
            return colBColor;  
        }  
        // Stores the selected value in the private variable colBColor, and   
        // updates the background color of the label control lblDisplay.  
        set  
        {  
            colBColor = value;  
            lblDisplay.BackColor = colBColor;     
        }  
    }  
    // Provides a similar set of instructions for the foreground color.  
    public Color ClockForeColor  
    {  
        get  
        {  
            return colFColor;  
        }  
        set  
        {  
            colFColor = value;  
            lblDisplay.ForeColor = colFColor;  
        }  
    }  
    ```  
  
     El código anterior crea dos propiedades personalizadas, `ClockForeColor` y `ClockBackColor`, disponibles para posteriores usuarios de este control.  Las instrucciones `get` y `set` permiten el almacenamiento y la recuperación del valor de propiedad; además, proporcionan el código necesario para implementar la funcionalidad adecuada para la propiedad.  
  
4.  En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
## Probar el control  
 Los controles no son aplicaciones independientes; deben hospedarse en un contenedor.  Pruebe el comportamiento del control en tiempo de ejecución y pruebe sus propiedades con el **UserControl Test Container**.  Para obtener más información, vea [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### Para probar el control  
  
1.  Presione F5 para compilar el proyecto y ejecutar el control en el **UserControl Test Container**.  
  
2.  En la cuadrícula de propiedad del contenedor de prueba, busque la propiedad `ClockBackColor` y, a continuación, seleccione la propiedad para mostrar la paleta de colores.  
  
3.  Haga doble clic en un color para elegirlo.  
  
     El color de fondo del control cambiará al color seleccionado.  
  
4.  Utilice una secuencia de eventos similar para comprobar que la propiedad `ClockForeColor` funciona como se esperaba.  
  
     En esta sección y en las secciones anteriores, vio cómo se pueden combinar componentes y controles de Windows con código y empaquetamiento para ofrecer funcionalidad personalizada en forma de control de usuario.  Aprendió a exponer propiedades en el control compuesto, así como a probar el control una vez terminado.  En la siguiente sección, aprenderá a construir un control de usuario heredado utilizando `ctlClock` como base.  
  
## Heredar de un control compuesto  
 En las secciones anteriores, aprendió a combinar controles de Windows, componentes y código en controles de usuario reutilizables.  Ahora puede utilizar el control compuesto como base a partir de la cual se compilarán otros controles.  El proceso de derivación de una clase a partir de una clase base se denomina *herencia*.  En esta sección, creará un control de usuario denominado `ctlAlarmClock`.  Este control se derivará de su control principal, `ctlClock`.  Aprenderá a ampliar la funcionalidad de `ctlClock` reemplazando los métodos principales y agregando métodos y propiedades nuevos.  
  
 El primer paso para crear un control heredado es derivarlo de su control primario.  Esta acción crea un nuevo control que tiene todas las propiedades, métodos y características gráficas del control primario, pero que también actúa como base para la adición de funcionalidad nueva o modificada.  
  
#### Para crear el control heredado  
  
1.  En el **Explorador de soluciones**, haga clic en el proyecto con el botón secundario del mouse, elija **Agregar** y haga clic en **Control de usuario**.  
  
     Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
2.  Seleccione la plantilla **Control de usuario heredado**.  
  
3.  En el cuadro **Nombre**, escriba `ctlAlarmClock.jsl` y haga clic en **Agregar**.  
  
     Aparece el cuadro de diálogo **Selector de herencia**.  
  
4.  En **Nombre de componente**, haga doble clic en **ctlClock**.  
  
5.  En el Explorador de soluciones, examine los proyectos actuales.  
  
    > [!NOTE]
    >  Se ha agregado un archivo denominado **que ctlAlarmClock.cs** al proyecto actual.  
  
### Agregar propiedades de alarma  
 Las propiedades se agregan a un control heredado del mismo modo que se agregan a un control compuesto.  Ahora utilizará la sintaxis de declaración de propiedades para agregar dos propiedades al control: `AlarmTime`, que almacenará el valor de fecha y hora en que se activará la alarma y `AlarmSet`, que indica si está establecida o no la alarma.  
  
##### Para agregar propiedades al control compuesto  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlAlarmClock** y, a continuación, haga clic en **Ver código**.  
  
2.  Busque la instrucción `public class`.  Observe que el control hereda de `ctlClockLib.ctlClock`.  Bajo la llave de apertura \(`{)`, escriba el código siguiente.  
  
     \[C\#\]  
  
    ```  
    private DateTime dteAlarmTime;  
    private bool blnAlarmSet;  
    // These properties will be declared as public to allow future   
    // developers to access them.  
    public DateTime AlarmTime  
    {  
        get  
        {  
            return dteAlarmTime;  
        }  
        set  
        {  
            dteAlarmTime = value;  
        }  
    }  
    public bool AlarmSet  
    {  
        get  
        {  
            return blnAlarmSet;  
        }  
        set  
        {  
            blnAlarmSet = value;  
        }  
    }  
    ```  
  
### Agregar a la interfaz gráfica del control  
 El control heredado tiene una interfaz visual que es idéntica a la del control del que se hereda.  Posee los mismos controles constituyentes que su control primario, pero las propiedades de los controles constituyentes no estarán disponibles a menos que se expongan de manera específica.  Puede agregar a la interfaz gráfica de un control compuesto heredado del mismo modo que agregaría a cualquier control compuesto.  Para continuar agregando a la interfaz visual de su reloj de alarma, agregará un control Label que parpadeará cuando esté sonando la alarma.  
  
##### Para agregar el control Label  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlAlarmClock** y, a continuación, haga clic en **Ver diseñador**.  
  
     Aparecerá el diseñador de `ctlAlarmClock` en la ventana principal.  
  
2.  Haga clic en la zona de presentación del control y observe la ventana Propiedades.  
  
    > [!NOTE]
    >  Observe que, aunque se muestran todas las propiedades, están atenuadas.  Esto indica que estas propiedades son nativas de `lblDisplay` y no se pueden modificar ni se puede tener acceso a ellas en la ventana Propiedades.  De manera predeterminada, los controles contenidos en un control compuesto son privados \(`private`\) y no se puede tener acceso a sus propiedades de ningún modo.  
  
    > [!NOTE]
    >  Si desea que los futuros usuarios del control de usuario tengan acceso a los controles internos, declárelos como `public` o `protected`.  Esto le permitirá establecer y modificar las propiedades de los controles contenidos en el control compuesto, mediante el código adecuado.  
  
3.  Agregue el control <xref:System.Windows.Forms.Label> al control compuesto.  
  
4.  Con el mouse, mueva el control <xref:System.Windows.Forms.Label> justo debajo del cuadro de vista.  En la ventana Propiedades, establezca las propiedades siguientes:  
  
    |Propiedad.|Configuración|  
    |----------------|-------------------|  
    |**Name**|`lblAlarm`|  
    |**Text**|¡Alarma\!|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visible**|`false`|  
  
### Agregar la funcionalidad de alarma  
 En los procedimientos anteriores, agregó propiedades y un control que habilitará la funcionalidad de alarma en el control compuesto.  En este procedimiento, agregará código para comparar la hora actual con la hora de la alarma y, si coinciden, iniciará la alarma.  Al anular el método `timer1_Tick` de `ctlClock` y agregar código adicional en él, ampliará la capacidad de `ctlAlarmClock` mientras conserva toda la funcionalidad inherente de `ctlClock`.  
  
##### Para reemplazar el método timer1\_Tick de ctlClock  
  
1.  En el **Editor de código**, busque la instrucción `private bool blnAlarmSet;`.  Justo después, agregue la siguiente instrucción.  
  
     \[C\#\]  
  
    ```  
    private bool blnColorTicker;  
    ```  
  
2.  En el **Editor de código** busque la llave de cierre \(`})` al final de la clase.  Inmediatamente antes de la llave, agregue el código siguiente:  
  
     \[C\#\]  
  
    ```  
    protected override void timer1_Tick(object sender, System.EventArgs e)  
    {  
        // Calls the Timer1_Tick method of ctlClock.  
        base.timer1_Tick(sender, e);  
        // Checks to see if the alarm is set.  
        if (AlarmSet == false)  
            return;  
        else  
            // If the date, hour, and minute of the alarm time are the same as  
            // the current time, flash an alarm.   
        {  
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==   
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)  
            {  
                // Sets lblAlarmVisible to true, and changes the background color based on  
                // the value of blnColorTicker. The background color of the label   
                // will flash once per tick of the clock.  
                lblAlarm.Visible = true;  
                if (blnColorTicker == false)   
                {  
                    lblAlarm.BackColor = Color.Red;  
                    blnColorTicker = true;  
                }  
                else  
                {  
                    lblAlarm.BackColor = Color.Blue;  
                    blnColorTicker = false;  
                }  
            }  
            else  
            {  
                // Once the alarm has sounded for a minute, the label is made   
                // invisible again.  
                lblAlarm.Visible = false;  
            }  
        }  
    }  
    ```  
  
     Al agregar este código se realizan varias tareas.  La instrucción `override` indica al control que utilice este método en lugar del método heredado del control base.  Cuando se llama a este método, éste llama al que reemplaza al invocar la instrucción `base.timer1_Tick`; de este modo, se asegura que toda la funcionalidad incorporada en el control original se reproduzca en este control.  A continuación, ejecuta código adicional para incorporar la funcionalidad de la alarma.  Cuando se active la alarma, aparecerá un control etiqueta intermitente.  
  
     El control de reloj de alarma está casi completo.  Lo único que queda es implementar un medio para desactivarlo.  Para ello, agregará el código al método `lblAlarm_Click`.  
  
##### Para implementar el método de apagado  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlClock.cs** y haga clic en **Ver diseñador**.  
  
     Se abrirá el diseñador.  
  
2.  Agregue un botón al control.  Establezca las propiedades del botón de la manera siguiente.  
  
    |Propiedad.|Valor|  
    |----------------|-----------|  
    |**Name**|`btnAlarmOff`|  
    |**Text**|Deshabilitar alarma|  
  
3.  En el diseñador, haga doble clic en **btnAlarmOff**.  
  
     Se abrirá el **Editor de código** en la línea `private void btnAlarmOff_Click`.  
  
4.  Modifique este método de forma que se asemeje al código siguiente.  
  
     \[C\#\]  
  
    ```  
    private void btnAlarmOff_Click(object sender, System.EventArgs e)  
    {  
        // Turns off the alarm.  
        AlarmSet = false;  
        // Hides the flashing label.  
        lblAlarm.Visible = false;  
    }  
    ```  
  
5.  En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.  
  
### Utilizar el control heredado en un formulario  
 Puede probar el control heredado de la misma forma que probó el control de la clase base, `ctlClock`: presione F5 para compilar el proyecto y ejecute el control en **UserControl Test Container**.  Para obtener más información, vea [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Para colocar el control para su uso, tendrá que hospedarlo en un formulario.  Como ocurre con los controles compuestos estándar, los controles compuestos heredados no son independientes y deben hospedarse en un formulario o en otro contenedor.  Puesto que `ctlAlarmClock` ofrece una funcionalidad más profunda, será necesario código adicional para probarlo.  En esta sección, escribirá un programa sencillo para probar la funcionalidad de `ctlAlarmClock`.  Escribirá código para definir y mostrar la propiedad `AlarmTime` de `ctlAlarmClock` y probar sus funciones heredadas.  
  
##### Para compilar y agregar el control a un formulario de prueba  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **ctlClockLib** y haga clic en **Compilar**.  
  
2.  Agregue un nuevo proyecto de **Aplicación para Windows** a la solución y denomínelo `Test`.  
  
3.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en el nodo **Referencias** del proyecto de prueba.  Haga clic en **Agregar referencia** para mostrar el cuadro de diálogo **Agregar referencia**.  Haga clic en la ficha **Proyectos**.  El proyecto `ctlClockLib` aparecerá en la lista **Nombre de proyecto**.  Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.  
  
4.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en **Test** y haga clic en **Compilar**.  
  
5.  En el **Cuadro de herramientas**, expanda el nodo **Componentes de ctlClockLib**.  
  
6.  Haga doble clic en **ctlAlarmClock** para agregar una copia de `ctlAlarmClock` al formulario.  
  
7.  En el **Cuadro de herramientas**, busque y haga doble clic en **DateTimePicker** para agregar un control <xref:System.Windows.Forms.DateTimePicker> al formulario; a continuación, haga doble clic en **Label** para agregar un control <xref:System.Windows.Forms.Label>.  
  
8.  Utilice el mouse para colocar los controles en un lugar apropiado del formulario.  
  
9. Establezca las propiedades de estos controles de la manera siguiente.  
  
    |Control|Propiedad.|Valor|  
    |-------------|----------------|-----------|  
    |`label1`|**Text**|`(espacio en blanco)`|  
    ||**Name**|`lblTest`|  
    |`dateTimePicker1`|**Name**|`dtpTest`|  
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat>|  
  
10. En el diseñador, haga doble clic en **dtpTest**.  
  
     El **Editor de código** se abrirá en `private void dtpTest_ValueChanged`.  
  
11. Modifique el código de modo que se asemeje a lo siguiente.  
  
     \[C\#\]  
  
    ```  
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)  
    {  
        ctlAlarmClock1.AlarmTime = dtpTest.Value;  
        ctlAlarmClock1.AlarmSet = true;  
        lblTest.Text = "Alarm Time is " +  
            ctlAlarmClock1.AlarmTime.ToShortTimeString();  
    }  
    ```  
  
12. En el Explorador de soluciones, haga clic con el botón secundario del mouse en **Test** y, a continuación, en **Establecer como proyecto de inicio**.  
  
13. En el menú **Depurar**, haga clic en **Iniciar depuración**.  
  
     Se iniciará el programa de prueba.  Observe que la hora actual se actualiza en el control `ctlAlarmClock` y que la hora de inicio se muestra en el control <xref:System.Windows.Forms.DateTimePicker>.  
  
14. Haga clic en <xref:System.Windows.Forms.DateTimePicker> donde se muestran los minutos.  
  
15. Con el uso del teclado, defina un valor para los minutos que sea un minuto más que la hora actual que muestra `ctlAlarmClock`.  
  
     La hora de la configuración de la alarma se muestra en `lblTest`.  Espere a que la hora que se muestra alcance la hora establecida para la alarma.  Cuando la hora mostrada coincida con la hora a la que está puesta la alarma, se iniciará `lblAlarm`.  
  
16. Para desactivar la alarma, haga clic en `btnAlarmOff`.  Ahora puede reiniciar la alarma.  
  
     Este tutorial trataba varios conceptos clave.  Aprendió a crear un control compuesto mediante la combinación de controles y componentes en un contenedor de control compuesto.  Aprendió a agregar propiedades al control y a escribir código para implementar funcionalidades personalizadas.  En la última sección aprendió a extender la funcionalidad de un control compuesto mediante herencia, y a modificar la funcionalidad de los métodos hospedados reemplazando estos últimos.  
  
## Vea también  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Programming with Components](../Topic/Programming%20with%20Components.md)   
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)   
 [Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)   
 [Tutorial: Heredar de un control de formularios Windows Forms con Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)