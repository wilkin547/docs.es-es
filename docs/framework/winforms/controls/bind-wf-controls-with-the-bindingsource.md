---
title: Procedimiento para enlazar controles de formularios Windows Forms con el componente BindingSource mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 180fafa9ace5927fd84ec5dc0a1b2a342f771efd
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040024"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Procedimiento para enlazar controles de formularios Windows Forms con el componente BindingSource mediante el diseñador
Después de haber agregado controles al formulario y determinado la interfaz de usuario de la aplicación, puede enlazar los controles a un origen de datos, de modo que, en tiempo de ejecución, los usuarios puedan modificar y guardar los datos relacionados con la aplicación.

 Enlazar un control o una serie de controles en Windows Forms se consigue más fácilmente <xref:System.Windows.Forms.BindingSource> mediante el control como un puente entre los controles del formulario y el origen de datos.

 Uno o varios controles de un formulario se pueden enlazar a datos; en el procedimiento siguiente, se <xref:System.Windows.Forms.TextBox> enlaza un control a un origen de datos.

 Para completar el procedimiento, se supone que se enlazará a un origen de datos derivado de una base de datos. Para obtener más información sobre cómo crear orígenes de datos de otros almacenes de datos, vea [agregar nuevos orígenes](/visualstudio/data-tools/add-new-data-sources)de datos.

## <a name="to-bind-a-control-at-design-time"></a>Para enlazar un control en tiempo de diseño

1. Arrastre un <xref:System.Windows.Forms.TextBox> control al formulario.

2. En la ventana **propiedades** :

    1. Expanda el nodo **(DataBindings)** .

    2. Haga clic en la flecha situada <xref:System.Windows.Forms.TextBox.Text%2A> junto a la propiedad.

         Se abre el editor de tipos de interfaz de usuario de **DataSource** .

         Si previamente se ha configurado un origen de datos para el proyecto o formulario, aparecerá.

3. Haga clic en **Agregar origen de datos del proyecto** para conectar con los datos y crear un origen de datos.

4. En la página principal del **Asistente para la configuración de orígenes de datos**, haga clic en **Siguiente**.

5. En la página **elegir un tipo de origen de datos** , seleccione **base**de datos.

6. En la página **elegir la conexión de datos** , seleccione una conexión de datos de la lista de conexiones disponibles. Si la conexión de datos deseada no está disponible, seleccione **nueva conexión** para crear una nueva conexión de datos.

7. Seleccione **sí, guardar la conexión** para guardar la cadena de conexión en el archivo de configuración de la aplicación.

8. Seleccione los objetos de base de datos que va a traer a su aplicación. En este caso, seleccione un campo de una tabla que le <xref:System.Windows.Forms.TextBox> gustaría que mostrara.

9. Reemplace el nombre del conjunto de datos predeterminado, si lo desea.

10. Haga clic en **Finalizar**

11. En la ventana **propiedades** , haga clic de nuevo en la <xref:System.Windows.Forms.TextBox.Text%2A> flecha situada junto a la propiedad. En el editor de tipos de interfaz de usuario de **DataSource** , seleccione el nombre del <xref:System.Windows.Forms.TextBox> campo al que se va a enlazar.

     El editor de tipos de interfaz de usuario del **origen** de datos <xref:System.Windows.Forms.BindingSource> se cierra y el conjunto de datos y el adaptador de tabla específico de esa conexión de datos se agregan al formulario.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources)
- [Ventana orígenes de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
