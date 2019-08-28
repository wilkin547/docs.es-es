---
title: 'Tutorial: Demostración de la herencia visual'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 32df98852b28963ffb748895156f7d9977c74b92
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046150"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a>Tutorial: Demostración de la herencia visual

La herencia visual le permite ver los controles del formulario base y agregar controles nuevos. En este tutorial, creará un formulario base y lo compilará para convertirlo en una biblioteca de clases. Importará la biblioteca de clases en otro proyecto y creará un nuevo formulario que herede del formulario base. Durante este tutorial aprenderá a:

- Crear un proyecto de biblioteca de clases que contiene un formulario base.

- Agregar un botón con propiedades que las clases derivadas del formulario base pueden modificar.

- Agregar un botón que los herederos del formulario base no pueden modificar.

- Crear un proyecto que contiene un formulario que hereda de `BaseForm`.

Por último, en este tutorial se mostrará la diferencia entre los controles privados y los protegidos de un formulario heredado.

> [!CAUTION]
> No todos los controles admiten la herencia visual a partir de un formulario base. Los siguientes controles no admiten el escenario que se describe en este tutorial:
>
> - <xref:System.Windows.Forms.WebBrowser>
>
> - <xref:System.Windows.Forms.ToolStrip>
>
> - <xref:System.Windows.Forms.ToolStripPanel>
>
> - <xref:System.Windows.Forms.TableLayoutPanel>
>
> - <xref:System.Windows.Forms.FlowLayoutPanel>
>
> - <xref:System.Windows.Forms.DataGridView>
>
> Estos controles del formulario heredado siempre son de solo lectura, independientemente de los modificadores que utilice (`private`, `protected` o `public`).

## <a name="create-a-class-library-project-containing-a-base-form"></a>Crear un proyecto de biblioteca de clases que contenga un formulario base

1. En Visual Studio, en el menú **archivo** , elija **nuevo** > **proyecto** para abrir el cuadro de diálogo **nuevo proyecto** .

2. Cree una aplicación de Windows Forms `BaseFormLibrary`denominada.

3. Para crear una biblioteca de clases en lugar de una aplicación de Windows Forms estándar, en **Explorador de soluciones**, haga clic con el botón secundario en el nodo del proyecto **BaseFormLibrary** y seleccione **propiedades**.

4. En las propiedades del proyecto, cambie el **tipo de salida** de **aplicación Windows** a **biblioteca de clases**.

5. En el menú **archivo** , elija **guardar todo** para guardar el proyecto y los archivos en la ubicación predeterminada.

Los dos procedimientos siguientes agregan botones al formulario base. Para ilustrar la herencia visual, proporcionará a los botones distintos niveles de acceso estableciendo sus propiedades `Modifiers`.

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a>Agregar un botón que los herederos del formulario base pueden modificar

1. Abra **Form1** en el diseñador.

2. En la pestaña **todos los Windows Forms** del **cuadro de herramientas**, haga doble clic en el **botón** para agregar un botón al formulario. Use el mouse para colocar y cambiar de tamaño el botón.

3. En la ventana Propiedades, establezca las propiedades siguientes del botón:

    - Establezca la propiedad **Text** en **Hello**.

    - Establezca la propiedad **(Name)** en **btnProtected**.

    - Establezca la propiedad Modifiers en **Protected**. Esto hace posible que los formularios que heredan de **Form1** modifiquen las propiedades de **btnProtected**.

4. Haga doble clic en el botón **Say Hola** para agregar un controlador de eventos para el evento **click** .

5. Agregue la línea de código siguiente al controlador del evento:

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a>Agregar un botón que los herederos del formulario base no pueden modificar

1. Cambie a la vista de diseño haciendo clic en la pestaña **Form1. VB [diseño], Form1.CS [diseño] o Form1. jsl [diseño]** situado encima del editor de código o presionando F7.

2. Agregue un segundo botón y establezca sus propiedades como sigue:

    - Establezca la propiedad **Text** en **Say Goodbye**.

    - Establezca la propiedad **(Name)** en **btnPrivate**.

    - Establezca la propiedad Modifiers en **Private**. Esto hace imposible que los formularios que heredan de **Form1** modifiquen las propiedades de **btnPrivate**.

3. Haga doble clic en el botón **Say adiós** para agregar un controlador de eventos para el evento **click** . Coloque la siguiente línea de código en el procedimiento de evento:

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. En el menú compilar, elija compilar **biblioteca BaseForm** para compilar la biblioteca de clases.

     Una vez compilada la biblioteca, puede crear un nuevo proyecto que herede del formulario que acaba de crear.

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a>Crear un proyecto que contenga un formulario que herede del formulario base

1. En el menú **archivo** , elija **Agregar** y, a continuación, **nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto** .

2. Cree una aplicación de Windows Forms `InheritanceTest`denominada.

## <a name="add-an-inherited-form"></a>Agregar un formulario heredado

1. En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest** , seleccione **Agregar**y, a continuación, seleccione **nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la categoría **Windows Forms** (si tiene una lista de categorías) y, a continuación, seleccione la plantilla de **formulario heredado** .

3. Deje el nombre `Form2` predeterminado y, a continuación, haga clic en **Agregar**.

4. En el cuadro de diálogo **selector de herencia** , seleccione **Form1** desde el proyecto **BaseFormLibrary** como el formulario del que se va a heredar y haga clic en **Aceptar**.

     Esto crea un formulario en el proyecto **InheritanceTest** que se deriva del formulario en **BaseFormLibrary**.

5. Abra el formulario heredado (**Form2**) en el diseñador haciendo doble clic en él, si aún no está abierto.

    En el diseñador, los botones heredados tienen un símbolo (![Captura de pantalla del símbolo de herencia Visual Basic.](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)) en la esquina superior, lo que indica que se han heredado.

6. Seleccione el botón **Say Hola** y observe los controladores de tamaño. Como este botón está protegido, los herederos pueden moverlo, cambiarlo de tamaño, cambiar su descripción y realizar otras modificaciones.

7. Seleccione el botón privado **decir adiós** y observe que no tiene controladores de tamaño. Además, en la ventana **propiedades** , las propiedades de este botón aparecen atenuadas para indicar que no se pueden modificar.

8. Si usa visual C#:

    1. En **Explorador de soluciones**, haga clic con el botón secundario en **Form1** en el proyecto **InheritanceTest** y seleccione **eliminar**. En el cuadro de mensaje que aparece, haga clic en **Aceptar** para confirmar la eliminación.

    2. Abra el archivo Program.cs y cambie la línea `Application.Run(new Form1());` por `Application.Run(new Form2());`.

9. En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest** y seleccione **establecer como proyecto de inicio**.

10. En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest** y seleccione **propiedades**.

11. En las páginas de propiedades de **InheritanceTest** , establezca el **objeto de inicio** para que sea el formulario heredado (**Form2**).

12. Presione **F5** para ejecutar la aplicación y observe el comportamiento del formulario heredado.

## <a name="next-steps"></a>Pasos siguientes

La herencia de los controles de usuario funciona más o menos de la misma manera. Abra un proyecto nuevo de biblioteca de clases y agregue un control de usuario. Coloque en él controles constituyentes y compile el proyecto. Abra otro proyecto nuevo de biblioteca de clases y agregue una referencia a la biblioteca de clases compilada. Además, intente agregar un control heredado (mediante el cuadro de diálogo **agregar nuevos elementos** ) al proyecto y usando el **selector de herencia**. Agregue un control de usuario y cambie la `Inherits` instrucción`:` (en C#visual). Para obtener más información, vea [Cómo: Heredar](how-to-inherit-windows-forms.md)Windows Forms.

## <a name="see-also"></a>Vea también

- [Cómo: Heredar Windows Forms](how-to-inherit-windows-forms.md)
- [Herencia visual de Windows Forms](windows-forms-visual-inheritance.md)
- [Windows Forms](../index.md)
