---
title: 'Tutorial: Heredar de un control de formularios Windows Forms con Visual C#'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
ms.openlocfilehash: 392f0e98c3401ca5ae5e01fefbf35462462b3a4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531257"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-c"></a>Tutorial: Heredar de un control de formularios Windows Forms con Visual C# #
Con [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)], puede crear controles personalizados eficaces mediante *herencia*. A través de la herencia puede crear controles que conserven toda la funcionalidad inherente de controles de Windows Forms estándar y además incorporen funcionalidad personalizada. En este tutorial, creará un control heredado simple denominado `ValueButton`. Este botón heredará funcionalidad de los formularios de Windows estándar <xref:System.Windows.Forms.Button> controlar y expondrá una propiedad personalizada denominada `ButtonValue`.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y para asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a>Para crear la biblioteca de controles ValueButtonLib y el control ValueButton  
  
1.  En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.  
  
2.  Seleccione el **biblioteca de controles de Windows Forms** plantilla de proyecto en la lista de proyectos de Visual C# y el tipo `ValueButtonLib` en el **nombre** cuadro.  
  
     El nombre del proyecto, `ValueButtonLib` también se asigna de forma predeterminada al espacio de nombres raíz. El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado. Por ejemplo, si dos ensamblados proporcionan componentes denominados `ValueButton`, puede especificar su componente `ValueButton` mediante `ValueButtonLib.ValueButton`. Para más información, consulte [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md).  
  
3.  En el **Explorador de soluciones**, haga clic con el botón derecho en **UserControl1.cs** y elija **Cambiar nombre** en el menú contextual. Cambie el nombre del archivo a `ValueButton.cs`. Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "`UserControl1`".  
  
4.  En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.cs** y seleccione **Ver código**.  
  
5.  Busque el `class` línea de la instrucción, `public partial class ValueButton`y cambie el tipo del que hereda este control de <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>. Esto permite que el control heredado herede toda la funcionalidad de la <xref:System.Windows.Forms.Button> control.  
  
6.  En el **Explorador de soluciones**, abra el nodo **ValueButton.cs** para mostrar el archivo de código generado por el diseñador, **ValueButton.Designer.cs**. Abra este archivo en el **Editor de código**.  
  
7.  Busque el `InitializeComponent` método y quite la línea que asigna el <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> propiedad. Esta propiedad no existe en el <xref:System.Windows.Forms.Button> control.  
  
8.  En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.  
  
    > [!NOTE]
    >  Ya no hay disponible ningún diseñador visual. Dado que el <xref:System.Windows.Forms.Button> control realiza su propia representación, no puede modificar su apariencia en el diseñador. Su representación visual será exactamente el mismo que el de la clase que hereda (es decir, <xref:System.Windows.Forms.Button>) a menos que modifique en el código. Todavía puede agregar componentes, que no tienen ningún elemento de interfaz de usuario, a la superficie de diseño.  
  
## <a name="adding-a-property-to-your-inherited-control"></a>Agregar una propiedad al control heredado  
 Un uso posible de los controles de Windows Forms heredados es la creación de controles que sean idénticos en apariencia y comportamiento a los controles de Windows Forms estándar, pero que expongan propiedades personalizadas. En esta sección, agregará una propiedad denominada `ButtonValue` al control.  
  
#### <a name="to-add-the-value-property"></a>Para agregar la propiedad Value  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.cs** y haga clic en **Ver código** en el menú contextual.  
  
2.  Busque la instrucción `class`. Inmediatamente detrás de `{`, escriba el siguiente código:  
  
    ```csharp  
    // Creates the private variable that will store the value of your   
    // property.  
    private int varValue;  
    // Declares the property.  
    public int ButtonValue  
    {  
       // Sets the method for retrieving the value of your property.  
       get  
       {  
          return varValue;  
       }  
       // Sets the method for setting the value of your property.  
       set  
       {  
          varValue = value;  
       }  
    }  
    ```  
  
     Este código establece los métodos por los que se almacena y se recupera la propiedad `ButtonValue`. La instrucción `get` establece el valor devuelto en el valor que se almacena en la variable privada `varValue`, y la instrucción `set` establece el valor de la variable privada mediante la palabra clave `value`.  
  
3.  En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.  
  
## <a name="testing-your-control"></a>Probar el control  
 Los controles no son proyectos independientes; deben hospedarse en un contenedor. Para probar el control, debe proporcionar un proyecto de prueba donde pueda ejecutarse. También debe hacer que el control resulte accesible al proyecto de prueba al compilarlo. En esta sección, compilará el control y lo probará en Windows Forms.  
  
#### <a name="to-build-your-control"></a>Para compilar el control  
  
1.  En el menú **Compilar** , haga clic en **Compilar solución**.  
  
     La compilación debería completarse correctamente sin advertencias ni errores del compilador.  
  
#### <a name="to-create-a-test-project"></a>Para crear un proyecto de prueba  
  
1.  En el menú **Archivo**, elija **Agregar** y haga clic en **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.  
  
2.  Seleccione el nodo **Windows**, debajo del nodo **Visual C#**, y haga clic en **Aplicación de Windows Forms**.  
  
3.  En el cuadro **Nombre**, escriba `Test`.  
  
4.  En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** para su proyecto de prueba y seleccione **Agregar referencia** en el menú contextual para mostrar el cuadro de diálogo **Agregar referencia**.  
  
5.  Haga clic en la pestaña etiquetada como **Proyectos**. El proyecto `ValueButtonLib` aparecerá bajo **Nombre de proyecto**. Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.  
  
6.  En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y seleccione **Compilar**.  
  
#### <a name="to-add-your-control-to-the-form"></a>Para agregar el control al formulario  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en **Form1.cs** y elija **Ver diseñador** en el menú contextual.  
  
2.  En el **cuadro de herramientas**, haga clic en **Componentes de ValueButtonLib**. Haga doble clic en **ValueButton**.  
  
     Aparece un componente **ValueButton** en el formulario.  
  
3.  Haga clic con el botón derecho en **ValueButton** y seleccione **Propiedades** en el menú contextual.  
  
4.  En la ventana **Propiedades**, examine las propiedades de este control. Observe que son idénticas a las propiedades expuestas por un botón estándar, excepto en que hay una propiedad adicional, `ButtonValue`.  
  
5.  Establezca la propiedad `ButtonValue` en `5`.  
  
6.  En el **todos los formularios de Windows** pestaña de la **cuadro de herramientas**, haga doble clic en **etiqueta** para agregar un <xref:System.Windows.Forms.Label> al formulario.  
  
7.  Mueva la etiqueta al centro del formulario.  
  
8.  Haga doble clic en `valueButton1`.  
  
     Se abre el **Editor de código** en el evento `valueButton1_Click`.  
  
9. Inserte la siguiente línea de código.  
  
    ```csharp  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y elija **Establecer como proyecto de inicio** en el menú contextual.  
  
11. En el menú **Depurar**, seleccione **Iniciar depuración**.  
  
     Aparece `Form1`.  
  
12. Haga clic en `valueButton1`.  
  
     Se muestra el número "5" en `label1`, lo que demuestra que la propiedad `ButtonValue` del control heredado se ha pasado a `label1` a través del método `valueButton1_Click`. Por lo tanto, su control `ValueButton` hereda toda la funcionalidad del botón estándar de Windows Forms, pero expone una propiedad personalizada adicional.  
  
## <a name="see-also"></a>Vea también
- [Programar con componentes](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)
- [Tutoriales sobre la creación de componentes](https://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)
- [Cómo: Mostrar un Control en la elija el cuadro de diálogo de elementos de cuadro de herramientas](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [Tutorial: Crear un Control compuesto con VisualC#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
