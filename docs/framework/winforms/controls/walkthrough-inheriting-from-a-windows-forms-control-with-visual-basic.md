---
title: 'Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
ms.openlocfilehash: a6b1e78d17d952590510bdda80bf802ccc094285
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541442"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a>Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic
Con Visual Basic, puede crear controles personalizados eficaces a través de *herencia*. A través de la herencia puede crear controles que conserven toda la funcionalidad inherente de controles de Windows Forms estándar y además incorporen funcionalidad personalizada. En este tutorial, creará un control heredado simple denominado `ValueButton`. Este botón heredará la funcionalidad de los formularios de Windows estándar <xref:System.Windows.Forms.Button> controlar y expondrá una propiedad personalizada denominada `ButtonValue`.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y para asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a>Para crear la biblioteca de controles ValueButtonLib y el control ValueButton  
  
1.  En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.  
  
2.  Seleccione el **biblioteca de controles de Windows Forms** plantilla de proyecto en la lista de proyectos de Visual Basic y el tipo `ValueButtonLib` en el **nombre** cuadro.  
  
     El nombre del proyecto, `ValueButtonLib` también se asigna de forma predeterminada al espacio de nombres raíz. El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado. Por ejemplo, si dos ensamblados proporcionan componentes denominados `ValueButton`, puede especificar su componente `ValueButton` mediante `ValueButtonLib.ValueButton`. Para más información, consulte [Espacios de nombres en Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).  
  
3.  En el **Explorador de soluciones**, haga clic con el botón derecho en **UserControl1.vb** y elija **Cambiar nombre** en el menú contextual. Cambie el nombre del archivo a `ValueButton.vb`. Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".  
  
4.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  
  
5.  Abra el nodo **ValueButton.vb** para mostrar el archivo de código generado por el diseñador, **ValueButton.Designer.vb**. Abra este archivo en el **Editor de código**.  
  
6.  Busque la `Class` instrucción, `Partial Public Class ValueButton`y cambie el tipo del que este control hereda de <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>. Esto permite al control heredado heredar toda la funcionalidad de la <xref:System.Windows.Forms.Button> control.  
  
7.  Busque la `InitializeComponent` método y quite la línea que asigna la <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> propiedad. Esta propiedad no existe en el <xref:System.Windows.Forms.Button> control.  
  
8.  En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.  
  
     Tenga en cuenta que ya no hay disponible ningún diseñador visual. Dado que el <xref:System.Windows.Forms.Button> control realiza su propia representación, no puede modificar su apariencia en el diseñador. Su representación visual será exactamente igual que la de la clase que hereda (es decir, <xref:System.Windows.Forms.Button>) a menos que modifique en el código.  
  
> [!NOTE]
>  Todavía puede agregar componentes, que no tienen ningún elemento de interfaz de usuario, a la superficie de diseño.  
  
## <a name="adding-a-property-to-your-inherited-control"></a>Agregar una propiedad al control heredado  
 Un uso posible de los controles de Windows Forms heredados es la creación de controles que sean idénticos en apariencia y comportamiento a los controles de Windows Forms estándar, pero que expongan propiedades personalizadas. En esta sección, agregará una propiedad denominada `ButtonValue` al control.  
  
#### <a name="to-add-the-value-property"></a>Para agregar la propiedad Value  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.vb** y haga clic en **Ver código** en el menú contextual.  
  
2.  Busque la instrucción `Public Class ValueButton`. Justo debajo de esta declaración, escriba el siguiente código:  
  
    ```vb  
    ' Creates the private variable that will store the value of your   
    ' property.  
    Private varValue as integer  
    ' Declares the property.  
    Property ButtonValue() as Integer  
    ' Sets the method for retrieving the value of your property.  
       Get  
          Return varValue  
       End Get  
    ' Sets the method for setting the value of your property.  
       Set(ByVal Value as Integer)  
          varValue = Value  
       End Set  
    End Property  
    ```  
  
     Este código establece los métodos por los que se almacena y se recupera la propiedad `ButtonValue`. La instrucción `Get` establece el valor devuelto en el valor que se almacena en la variable privada `varValue`, y la instrucción `Set` establece el valor de la variable privada mediante la palabra clave `Value`.  
  
3.  En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.  
  
## <a name="testing-your-control"></a>Probar el control  
 Los controles no son proyectos independientes; deben hospedarse en un contenedor. Para probar el control, debe proporcionar un proyecto de prueba donde pueda ejecutarse. También debe hacer que el control resulte accesible al proyecto de prueba al compilarlo. En esta sección, compilará el control y lo probará en Windows Forms.  
  
#### <a name="to-build-your-control"></a>Para compilar el control  
  
1.  En el menú **Compilar** , haga clic en **Compilar solución**.  
  
     La compilación debería completarse correctamente sin advertencias ni errores del compilador.  
  
#### <a name="to-create-a-test-project"></a>Para crear un proyecto de prueba  
  
1.  En el menú **Archivo**, elija **Agregar** y haga clic en **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.  
  
2.  Seleccione el nodo de proyectos de Visual Basic y haga clic en **aplicación de Windows Forms**.  
  
3.  En el cuadro **Nombre**, escriba `Test`.  
  
4.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  
  
5.  En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** para su proyecto de prueba y seleccione **Agregar referencia** en el menú contextual para mostrar el cuadro de diálogo **Agregar referencia**.  
  
6.  Haga clic en la pestaña **Proyectos**.  
  
7.  Haga clic en la pestaña etiquetada como **Proyectos**. El proyecto `ValueButtonLib` aparecerá bajo **Nombre de proyecto**. Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.  
  
8.  En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y seleccione **Compilar**.  
  
#### <a name="to-add-your-control-to-the-form"></a>Para agregar el control al formulario  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en **Form1.vb** y elija **Ver diseñador** en el menú contextual.  
  
2.  En el **cuadro de herramientas**, haga clic en **Componentes de ValueButtonLib**. Haga doble clic en **ValueButton**.  
  
     Aparece un componente **ValueButton** en el formulario.  
  
3.  Haga clic con el botón derecho en **ValueButton** y seleccione **Propiedades** en el menú contextual.  
  
4.  En la ventana **Propiedades**, examine las propiedades de este control. Observe que son idénticas a las propiedades expuestas por un botón estándar, excepto en que hay una propiedad adicional, `ButtonValue`.  
  
5.  Establezca la propiedad `ButtonValue` en `5`.  
  
6.  En el **todos los formularios Windows Forms** pestaña de la **cuadro de herramientas**, haga doble clic en **etiqueta** para agregar un <xref:System.Windows.Forms.Label> al formulario.  
  
7.  Mueva la etiqueta al centro del formulario.  
  
8.  Haga doble clic en `ValueButton1`.  
  
     Se abre el **Editor de código** en el evento `ValueButton1_Click`.  
  
9. Escriba la siguiente línea de código.  
  
    ```vb  
    Label1.Text = CStr(ValueButton1.ButtonValue)  
    ```  
  
10. En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y elija **Establecer como proyecto de inicio** en el menú contextual.  
  
11. En el menú **Depurar**, seleccione **Iniciar depuración**.  
  
     Aparece `Form1`.  
  
12. Haga clic en `Valuebutton1`.  
  
     Se muestra el número "5" en `Label1`, lo que demuestra que la propiedad `ButtonValue` del control heredado se ha pasado a `Label1` a través del método `ValueButton1_Click`. Por lo tanto, su control `ValueButton` hereda toda la funcionalidad del botón estándar de Windows Forms, pero expone una propiedad personalizada adicional.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Cómo: Mostrar un control en el cuadro de diálogo Seleccionar elementos del cuadro de herramientas](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [Desarrollar controles personalizados de Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Fundamentos de la herencia (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Tutoriales sobre la creación de componentes](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)
