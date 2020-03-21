---
title: 'Tutorial: Crear un control compuesto con Visual C#'
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ad9aad026a1a6a1266845736d7651db77fd5d5c
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546729"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a>Tutorial: Crear un control compuesto con C\#

Los controles compuestos proporcionan una forma de crear y reutilizar interfaces gráficas personalizadas. Un control compuesto es esencialmente un componente con una representación visual. Como tal, puede constar de uno o varios controles de Windows Forms, componentes o bloques de código que pueden extender funcionalidad al validar la entrada del usuario, modificar propiedades de presentación o realizar otras tareas requeridas por el autor. Los controles compuestos se pueden colocar en Windows Forms de la misma manera que otros controles. En la primera parte de este tutorial, creará un control compuesto simple denominado `ctlClock`. En la segunda parte, extenderá la funcionalidad de `ctlClock` mediante herencia.

## <a name="create-the-project"></a>Creación del proyecto

Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y asegúrese de que el componente predeterminado estará en el espacio de nombres correcto.

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a>Para crear la biblioteca de controles ctlClockLib y el control ctlClock

1. En Visual Studio, cree un nuevo proyecto de biblioteca de controles de **formularios Windows Forms** y asímócelo **ctlClockLib**.

     El nombre del proyecto, `ctlClockLib`, también se asigna de forma predeterminada al espacio de nombres raíz. El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado. Por ejemplo, si dos ensamblados proporcionan componentes denominados `ctlClock`, puede especificar su componente `ctlClock` mediante `ctlClockLib.ctlClock.`

2. En **el Explorador**de soluciones , haga clic con el botón secundario en **UserControl1.cs**y, a continuación, haga clic en Cambiar **nombre**. Cambie el nombre del archivo a `ctlClock.cs`. Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".

    > [!NOTE]
    > De forma predeterminada, un control <xref:System.Windows.Forms.UserControl> compuesto hereda de la clase proporcionada por el sistema. La <xref:System.Windows.Forms.UserControl> clase proporciona funcionalidad requerida por todos los controles compuestos e implementa propiedades y métodos estándar.

3. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.

## <a name="add-windows-controls-and-components-to-the-composite-control"></a>Agregar controles y componentes de Windows al control compuesto

Una interfaz visual es una parte esencial de su control compuesto. Esta interfaz visual se implementa agregando uno o más controles de Windows a la superficie del diseñador. En la demostración siguiente, incorporará controles de Windows al control compuesto y escribirá código para implementar funcionalidad.

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a>Para agregar una etiqueta y un temporizador al control compuesto

1. En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlClock.cs**y, a continuación, haga clic en Diseñador **de vistas**.

2. En el cuadro de **herramientas**, expanda el nodo **Controles comunes** y, a continuación, haga doble clic en **Etiqueta**.

     Se <xref:System.Windows.Forms.Label> agrega `label1` un control denominado al control en la superficie del diseñador.

3. En el diseñador, haga clic en **label1**. En la ventana Propiedades, establezca las propiedades siguientes.

    |Propiedad|Cambiar a|
    |--------------|---------------|
    |**Nombre**|`lblDisplay`|
    |**Texto**|`(blank space)`|
    |**TextAlign**|`MiddleCenter`|
    |**Font.Size**|`14`|

4. En el **cuadro de herramientas**, expanda el nodo **Componentes** y haga doble clic en **Temporizador**.

     Dado <xref:System.Windows.Forms.Timer> que a es un componente, no tiene ninguna representación visual en tiempo de ejecución. Por lo tanto, no aparece con los controles en la superficie del diseñador, sino en el Diseñador de **componentes** (una bandeja en la parte inferior de la superficie del diseñador).

5. En el **Diseñador de componentes**, <xref:System.Windows.Forms.Timer.Interval%2A> haga `1000` clic <xref:System.Windows.Forms.Timer.Enabled%2A> en `true` **timer1**y, a continuación, establezca la propiedad en .

     La <xref:System.Windows.Forms.Timer.Interval%2A> propiedad controla la <xref:System.Windows.Forms.Timer> frecuencia con la que el componente marca. Cada vez que `timer1` hace tic, se ejecuta el código en el evento `timer1_Tick`. El intervalo representa el número de milisegundos entre tics.

6. En el **Diseñador de componentes**, haga doble `ctlClock`clic en **timer1** para ir al `timer1_Tick` evento para .

7. Modifique el código para que se parezca al siguiente ejemplo. Asegúrese de cambiar el modificador de acceso de `private` a `protected`.

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     Este código hará que la hora actual se muestre en `lblDisplay`. Como el intervalo de `timer1` se estableció en `1000`, este evento se producirá cada mil milisegundos, lo que actualiza la hora actual cada segundo.

8. Modifique el método para que se pueda reemplazar con la palabra clave `virtual`. Para más información, consulte la sección "Heredar de un control compuesto".

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.

## <a name="add-properties-to-the-composite-control"></a>Agregar propiedades al control compuesto

El control de reloj <xref:System.Windows.Forms.Label> ahora <xref:System.Windows.Forms.Timer> encapsula un control y un componente, cada uno con su propio conjunto de propiedades inherentes. Aunque las propiedades individuales de estos controles no resultarán accesibles a los usuarios posteriores del control, puede crear y exponer propiedades personalizadas escribiendo los bloques de código adecuados. En el siguiente procedimiento, agregará al control propiedades que permiten al usuario cambiar el color de fondo y del texto.

### <a name="to-add-a-property-to-your-composite-control"></a>Para agregar una propiedad al control compuesto

1. En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlClock.cs**y, a continuación, haga clic en Ver **código**.

     Se abre el **Editor de código** del control.

2. Busque la instrucción `public partial class ctlClock`. Bajo la llave de apertura (`{)`, escriba el código siguiente.

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     Estas instrucciones crean las variables privadas que usará para almacenar los valores de las propiedades que va a crear.

3. Escriba o pegue el siguiente código debajo de las declaraciones de variables del paso 2.

    ```csharp
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

     El código anterior crea dos propiedades personalizadas, `ClockForeColor` y `ClockBackColor`, que estarán disponibles para posteriores usuarios de este control. Las instrucciones `get` y `set` permiten almacenar y recuperar el valor de propiedad, además de proporcionar código para implementar funcionalidad adecuada para la propiedad.

4. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.

## <a name="test-the-control"></a>Probar el control

Los controles no son aplicaciones independientes; deben hospedarse en un contenedor. Pruebe el comportamiento en tiempo de ejecución del control y sus propiedades con **UserControl Test Container**. Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

### <a name="to-test-your-control"></a>Para probar el control

1. Presione **F5** para compilar el proyecto y ejecutar el control en el contenedor de **pruebas UserControl**.

2. En la cuadrícula de propiedades del contenedor de prueba, busque la propiedad `ClockBackColor` y selecciónela para mostrar la paleta de colores.

3. Haga clic en un color para elegirlo.

   El color de fondo del control cambia al color seleccionado.

4. Use una secuencia similar de eventos para comprobar que la propiedad `ClockForeColor` funcione según lo esperado.

   En esta sección y en las anteriores, ha visto cómo se pueden combinar componentes y controles de Windows con código y empaquetado para ofrecer funcionalidad personalizada en forma de control compuesto. Ha aprendido a exponer propiedades en el control compuesto y a probar el control una vez completado. En la siguiente sección, aprenderá a crear un control compuesto heredado utilizando `ctlClock` como base.

## <a name="inherit-from-a-composite-control"></a>Heredar de un control compuesto

En las secciones anteriores, ha aprendido a combinar controles de Windows, componentes y código en controles compuestos reutilizables. Ahora puede utilizar su control compuesto como base sobre la que crear otros controles. El proceso de derivar una clase a partir de una clase base se denomina *herencia*. En esta sección, creará un control de usuario denominado `ctlAlarmClock`. Este control se derivará de su control primario, `ctlClock`. Aprenderá a extender la funcionalidad de `ctlClock` reemplazando los métodos primarios y agregando nuevos métodos y propiedades.

El primer paso para crear un control heredado es derivarlo de su elemento primario. Esta acción crea un control que tiene todas las propiedades, los métodos y las características gráficas del control primario, pero que también puede servir de base para agregar funcionalidad nueva o modificada.

### <a name="to-create-the-inherited-control"></a>Para crear el control heredado

1. En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlClockLib**, seleccione **Agregar**y, a continuación, haga clic en Control **de usuario**.

     Se abre el cuadro de diálogo **Agregar nuevo elemento** .

2. Seleccione la plantilla **Control de usuario heredado**.

3. En el cuadro **Nombre**, escriba `ctlAlarmClock.cs` y haga clic en **Agregar**.

     Aparece el cuadro de diálogo **Selector de herencia**.

4. En **Nombre de componente**, haga doble clic en **ctlClock**.

5. En el Explorador de **soluciones**, examine los proyectos actuales.

    > [!NOTE]
    > Se ha agregado un archivo denominado **ctlAlarmClock.cs** al proyecto actual.

### <a name="add-the-alarm-properties"></a>Añadir las propiedades de alarma

Las propiedades se agregan a un control heredado de la misma forma que si fuera un control compuesto. Ahora utilizará la sintaxis de declaración de propiedades para agregar dos propiedades al control: `AlarmTime`, que almacenará el valor de la fecha y la hora en que debe activarse la alarma, y `AlarmSet`, que indicará si la alarma está definida.

#### <a name="to-add-properties-to-your-composite-control"></a>Para agregar propiedades al control compuesto

1. En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlAlarmClock**y, a continuación, haga clic en **Ver código**.

2. Busque la instrucción `public class`. Tenga en cuenta que el control hereda de `ctlClockLib.ctlClock`. Bajo la instrucción con la llave de apertura (`{)`, escriba el código siguiente.

    ```csharp
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

### <a name="add-to-the-graphical-interface-of-the-control"></a>Añadir a la interfaz gráfica del control

El control heredado tiene una interfaz visual que es idéntica a la del control del que hereda. Posee los mismos controles constituyentes que su control primario, pero las propiedades de estos no estarán disponibles a menos que se expusieran específicamente. Puede agregar a la interfaz gráfica de un control compuesto heredado del mismo modo que agregaría a cualquier control compuesto. Para seguir agregando a la interfaz visual de su reloj despertador, agregará un control de etiqueta que parpadeará cuando suene la alarma.

#### <a name="to-add-the-label-control"></a>Para agregar el control de etiqueta

1. En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlAlarmClock**y, a continuación, haga clic en Diseñador de **vistas**.

     Se abre el diseñador para `ctlAlarmClock` en la ventana principal.

2. Haga clic en la parte de presentación del control y observe la ventana Propiedades.

    > [!NOTE]
    > Aunque se muestran todas las propiedades, están atenuadas. Esto indica que estas propiedades son nativas de `lblDisplay` y no se pueden modificar ni se puede acceder a ellas en la ventana Propiedades. De forma predeterminada, los controles contenidos en un control compuesto son `private`, y sus propiedades no son accesibles por ningún medio.

    > [!NOTE]
    > Si desea que los posteriores usuarios de su control compuesto tengan acceso a sus controles internos, declárelos como `public` o `protected`. Esto le permitirá establecer y modificar las propiedades de los controles contenidos en el control compuesto mediante el código adecuado.

3. Agregue <xref:System.Windows.Forms.Label> un control al control compuesto.

4. Con el ratón, <xref:System.Windows.Forms.Label> arrastre el control inmediatamente debajo del cuadro de visualización. En la ventana Propiedades, establezca las propiedades siguientes.

    |Propiedad|Configuración|
    |--------------|-------------|
    |**Nombre**|`lblAlarm`|
    |**Texto**|**¡Alarma!**|
    |**TextAlign**|`MiddleCenter`|
    |**Visible**|`false`|

### <a name="add-the-alarm-functionality"></a>Añadir la funcionalidad de alarma

En los procedimientos anteriores, agregó propiedades y un control que habilitará la funcionalidad de alarma en el control compuesto. En este procedimiento, agregará código para comparar la hora actual con la hora de la alarma y, si son iguales, hacer que parpadee una alarma. Al reemplazar el método `timer1_Tick` de `ctlClock` y agregarle código adicional, extenderá la funcionalidad de `ctlAlarmClock` al mismo tiempo que conserva toda la funcionalidad inherente de `ctlClock`.

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a>Para reemplazar el método timer1_Tick de ctlClock

1. En el **Editor de código**, busque la instrucción `private bool blnAlarmSet;`. Justo debajo de ella, agregue la siguiente instrucción.

    ```csharp
    private bool blnColorTicker;
    ```

2. En el **Editor de código**, busque la llave de cierre (`})` al final de la clase. Justo antes de la llave, agregue el código siguiente.

    ```csharp
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

     Con la adición de este código, se llevan a cabo varias tareas. La instrucción `override` indica al control que utilice este método en lugar del que heredó del control base. Cuando se llama a este método, llama al método que reemplaza invocando la instrucción `base.timer1_Tick`, lo que garantiza que toda la funcionalidad incorporada en el control original se reproduzca en este control. A continuación, ejecuta código adicional para incorporar la funcionalidad de alarma. Aparecerá un control de etiqueta parpadeante cuando se active la alarma.

     El control de reloj despertador está casi completado. Lo único que queda es implementar una forma de desactivarlo. Para ello, agregará código al método `lblAlarm_Click`.

#### <a name="to-implement-the-shutoff-method"></a>Para implementar el método de apagado

1. En el Explorador de **soluciones**, haga clic **con el**botón secundario en ctlAlarmClock.cs y, a continuación, haga clic en Diseñador **de vistas**.

     Se abre el diseñador.

2. Agregue un botón al control. Establezca las propiedades del botón de la manera siguiente.

    |Propiedad|Value|
    |--------------|-----------|
    |**Nombre**|`btnAlarmOff`|
    |**Texto**|**Deshabilitar alarma**|

3. En el diseñador, haga doble clic en **btnAlarmOff**.

     Se abre el **Editor de código** en la línea `private void btnAlarmOff_Click`.

4. Modifique este método para que se parezca al siguiente código.

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. En el menú **Archivo**, haga clic en **Guardar todo** para guardar el proyecto.

### <a name="use-the-inherited-control-on-a-form"></a>Use el Control Heredado en un Formulario

Puede probar el control heredado de la misma manera `ctlClock`que probó el control de clase base: presione **F5** para compilar el proyecto y ejecutar el control en el contenedor de **pruebas UserControl**. Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

Para utilizar el control, debe hospedarlo en un formulario. Al igual que con los controles compuestos estándar, los controles compuestos heredados no son independientes y deben hospedarse en un formulario o en otro contenedor. Puesto que `ctlAlarmClock` tiene un mayor grado de funcionalidad, se necesita código adicional para probarlo. En este procedimiento, escribirá un programa sencillo para probar la funcionalidad de `ctlAlarmClock`. Escribirá código para establecer y mostrar la propiedad `AlarmTime` de `ctlAlarmClock` y probar sus funciones inherentes.

#### <a name="to-build-and-add-your-control-to-a-test-form"></a>Para compilar y agregar el control a un formulario de prueba

1. En **el Explorador**de soluciones , haga clic con el botón secundario en **ctlClockLib**y, a continuación, haga clic en **Generar**.

2. Agregue un nuevo proyecto de aplicación de **windows Forms** a la solución y asíse como **Prueba**.

3. En el Explorador de **soluciones**, haga clic con el botón secundario en el nodo **Referencias** del proyecto de prueba. Haga clic en **Agregar referencia** para mostrar el cuadro de diálogo **Agregar referencia**. Haga clic en la pestaña etiquetada como **Proyectos**. El proyecto `ctlClockLib` aparecerá bajo **Nombre de proyecto**. Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.

4. En **el Explorador**de soluciones , haga clic con el botón secundario en **Probar**y, a continuación, haga clic en **Generar**.

5. En el **cuadro de herramientas**, expanda el nodo **Componentes de ctlClockLib**.

6. Haga doble clic en **ctlAlarmClock** para agregar una copia de `ctlAlarmClock` al formulario.

7. En el cuadro de **herramientas**, busque y <xref:System.Windows.Forms.DateTimePicker> haga doble clic en <xref:System.Windows.Forms.Label> **DateTimePicker** para agregar un control al formulario y, a continuación, agregue un control haciendo doble clic en **Etiqueta**.

8. Use el mouse para colocar los controles en un lugar adecuado en el formulario.

9. Establezca las propiedades de estos controles de la manera siguiente.

    |Control|Propiedad|Value|
    |-------------|--------------|-----------|
    |`label1`|**Texto**|`(blank space)`|
    ||**Nombre**|`lblTest`|
    |`dateTimePicker1`|**Nombre**|`dtpTest`|
    ||**Formato**|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. En el diseñador, haga doble clic en **dtpTest**.

     Se abre el **Editor de código** en `private void dtpTest_ValueChanged`.

11. Modifique el código para que se parezca al siguiente.

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. En **el Explorador**de soluciones , haga clic con el botón secundario en **Probar**y, a continuación, haga clic en Establecer como proyecto **de inicio**.

13. En el menú **Depurar** , haga clic en **Iniciar depuración**.

     Se inicia el programa de prueba. Tenga en cuenta que la `ctlAlarmClock` hora actual se actualiza en <xref:System.Windows.Forms.DateTimePicker> el control y que la hora de inicio se muestra en el control.

14. Haga <xref:System.Windows.Forms.DateTimePicker> clic en el lugar donde se muestran los minutos de la hora.

15. Use el teclado para establecer el valor de los minutos en un minuto más tarde que la hora actual mostrada por `ctlAlarmClock`.

     La hora para la configuración de alarma se muestra en `lblTest`. Espere a que la hora mostrada llegue a la hora de la configuración de alarma. Cuando la hora que se muestra llegue a la hora en que está puesta la alarma, `lblAlarm` parpadeará.

16. Para desactivar la alarma, haga clic en `btnAlarmOff`. Ahora puede restablecer la alarma.

Este artículo ha cubierto una serie de conceptos clave. Ha aprendido a crear un control compuesto mediante la combinación de controles y componentes en un contenedor de control compuesto. Ha aprendido a agregar propiedades al control y a escribir código para implementar funcionalidad personalizada. En la última sección, ha aprendido a extender la funcionalidad de un control compuesto determinado mediante herencia y a modificar la funcionalidad de los métodos de host reemplazando estos últimos.

## <a name="see-also"></a>Consulte también

- [Variedades de controles personalizados](varieties-of-custom-controls.md)
- [Cómo: Mostrar un control en el cuadro de diálogo Seleccionar elementos del cuadro de herramientas](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [Tutorial: Heredar de un control de formularios Windows Forms con Visual C#](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
