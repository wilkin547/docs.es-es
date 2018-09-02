---
title: 'Cómo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 95f375d8845c60441aa5eefdd37e32541ea2d5a7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418602"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Cómo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Diseñador
Una vez que haya agregado los controles al formulario y determina la interfaz de usuario para la aplicación, puede enlazar los controles a un origen de datos, por lo que, en tiempo de ejecución, los usuarios pueden modificar y guardar los datos relacionados con la aplicación.  
  
 Enlazar un control o una serie de controles en Windows Forms se consigue más fácilmente mediante el <xref:System.Windows.Forms.BindingSource> control como un puente entre los controles del formulario y el origen de datos.  
  
 Uno o varios controles en un formulario que se pueden enlazar a datos; en el procedimiento siguiente, un <xref:System.Windows.Forms.TextBox> control se enlaza a un origen de datos.  
  
 Para completar el procedimiento, se supone que se enlazará a un origen de datos derivado de una base de datos. Para obtener más información sobre cómo crear orígenes de datos desde otros almacenes de datos, vea [agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-a-control-at-design-time"></a>Para enlazar un control en tiempo de diseño  
  
1.  Arrastre un <xref:System.Windows.Forms.TextBox> control de sesión en el formulario.  
  
2.  En el **propiedades** ventana:  
  
    1.  Expanda el **(DataBindings)** nodo.  
  
    2.  Haga clic en la flecha situada junto a la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad.  
  
         El **DataSource** abre el editor de tipos de interfaz de usuario.  
  
         Si un origen de datos se ha configurado previamente para el proyecto o formulario, aparecerá.  
  
3.  Haga clic en **Agregar origen de datos del proyecto** para conectar con los datos y crear un origen de datos.  
  
4.  En la página principal del **Asistente para la configuración de orígenes de datos**, haga clic en **Siguiente**.  
  
5.  En el **elegir un tipo de origen de datos** página, seleccione **base de datos**.  
  
6.  En el **elegir la conexión de datos** , seleccione una conexión de datos de la lista de conexiones disponibles. Si la conexión de datos deseada no está disponible seleccione **nueva conexión** para crear una nueva conexión de datos.  
  
7.  Seleccione **Sí, guardar la conexión** para guardar la cadena de conexión en el archivo de configuración de la aplicación.  
  
8.  Seleccione los objetos de base de datos que va a traer a su aplicación. En este caso, seleccione un campo de una tabla que le gustaría el <xref:System.Windows.Forms.TextBox> para mostrar.  
  
9. Reemplace el nombre del conjunto de datos predeterminado, si lo desea.  
  
10. Haga clic en **Finalizar**.  
  
11. En el **propiedades** ventana, haga clic en la flecha situada junto a la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad nuevo. En el **DataSource** editor de tipos de interfaz de usuario, seleccione el nombre del campo que se va a enlazar el <xref:System.Windows.Forms.TextBox> a.  
  
     El **DataSource** la interfaz de usuario escriba editor cierra y el conjunto de datos, <xref:System.Windows.Forms.BindingSource> y adaptador de tabla específico para que la conexión de datos se agregan al formulario.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [Agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources)  
 [Ventana Orígenes de datos](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
