---
title: Enlazar controles al componente BindingSource mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 35b3fb7b9884f07dd6e2aef311a01d3090c44227
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744392"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Cómo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Diseñador
Después de haber agregado controles al formulario y determinado la interfaz de usuario de la aplicación, puede enlazar los controles a un origen de datos, de modo que, en tiempo de ejecución, los usuarios puedan modificar y guardar los datos relacionados con la aplicación.

 Enlazar un control o una serie de controles en Windows Forms se consigue más fácilmente mediante el control <xref:System.Windows.Forms.BindingSource> como un puente entre los controles del formulario y el origen de datos.

 Uno o varios controles de un formulario se pueden enlazar a datos; en el procedimiento siguiente, se enlaza un control <xref:System.Windows.Forms.TextBox> a un origen de datos.

 Para completar el procedimiento, se supone que se enlazará a un origen de datos derivado de una base de datos. Para obtener más información sobre cómo crear orígenes de datos de otros almacenes de datos, vea [agregar nuevos orígenes](/visualstudio/data-tools/add-new-data-sources)de datos.

## <a name="to-bind-a-control-at-design-time"></a>Para enlazar un control en tiempo de diseño

1. Arrastre un control <xref:System.Windows.Forms.TextBox> al formulario.

2. En la ventana **propiedades** :

    1. Expanda el nodo **(DataBindings)** .

    2. Haga clic en la flecha situada junto a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.

         Se abre el editor de tipos de interfaz de usuario de **DataSource** .

         Si previamente se ha configurado un origen de datos para el proyecto o formulario, aparecerá.

3. Haga clic en **Agregar origen de datos del proyecto** para conectar con los datos y crear un origen de datos.

4. En la página principal del **Asistente para la configuración de orígenes de datos**, haga clic en **Siguiente**.

5. En la página **elegir un tipo de origen de datos** , seleccione **base**de datos.

6. En la página **elegir la conexión de datos** , seleccione una conexión de datos de la lista de conexiones disponibles. Si la conexión de datos deseada no está disponible, seleccione **nueva conexión** para crear una nueva conexión de datos.

7. Seleccione **sí, guardar la conexión** para guardar la cadena de conexión en el archivo de configuración de la aplicación.

8. Seleccione los objetos de base de datos que va a traer a su aplicación. En este caso, seleccione un campo de una tabla que le gustaría que mostrara el <xref:System.Windows.Forms.TextBox>.

9. Reemplace el nombre del conjunto de datos predeterminado, si lo desea.

10. Haga clic en **Finalizar**.

11. En la ventana **propiedades** , haga clic de nuevo en la flecha situada junto a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>. En el editor de tipos de interfaz de usuario de **DataSource** , seleccione el nombre del campo al que se va a enlazar el <xref:System.Windows.Forms.TextBox>.

     El editor de tipos de interfaz de usuario del **origen** de datos se cierra y el conjunto de datos, <xref:System.Windows.Forms.BindingSource> y el adaptador de tabla específicos de esa conexión de datos se agregan al formulario.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources)
- [Ventana orígenes de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
