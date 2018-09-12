---
title: Solución de problemas relacionados con la creación de controles y componentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
ms.openlocfilehash: caad6a76b52a970e133425c484602deb8801d252
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44508769"
---
# <a name="troubleshooting-control-and-component-authoring"></a>Solución de problemas relacionados con la creación de controles y componentes
En este tema se enumeran los siguientes problemas comunes que surgen cuando se desarrollan componentes y controles. Para obtener más información, vea [Programar con componentes](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).  
  
-   No se puede agregar el control al cuadro de herramientas  
  
-   No se puede depurar el control de usuario de Windows Forms o un componente  
  
-   El evento se genera dos veces en el control o el componente heredado  
  
-   Error en tiempo de diseño: "Error al crear el componente '*nombre de componente*'"  
  
-   STAThreadAttribute  
  
-   El icono del componente no aparece en el cuadro de herramientas  
  
## <a name="cannot-add-control-to-toolbox"></a>No se puede agregar el control al cuadro de herramientas  
 Si desea agregar un control personalizado que creó en otro proyecto o un control de terceros al **cuadro de herramientas**, debe hacerlo manualmente. Si el proyecto actual contiene el control o componente, debería aparecer en el **cuadro de herramientas** automáticamente. Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
#### <a name="to-add-a-control-to-the-toolbox"></a>Para agregar un control al cuadro de herramientas  
  
1.  Haga clic con el botón derecho en el **cuadro de herramientas** y, en el menú contextual, seleccione **Elegir elementos**.  
  
2.  En el cuadro de diálogo **Elegir elementos de cuadro de herramientas**, agregue el componente:  
  
    -   Si desea agregar un control o un componente de .NET Framework, haga clic en la pestaña **Componentes de .NET Framework**.  
  
         -O bien-  
  
    -   Si desea agregar un componente COM o un control ActiveX, haga clic en la pestaña **Componentes COM**.  
  
3.  Si el control aparece en el cuadro de diálogo, confirme que está seleccionado y, a continuación, haga clic en **Aceptar**.  
  
     El control se agrega al **cuadro de herramientas**.  
  
4.  Si el control no aparece en el cuadro de diálogo, haga lo siguiente:  
  
    1.  Haga clic en el botón **Examinar**.  
  
    2.  Vaya a la carpeta que contiene el archivo .dll que contiene el control.  
  
    3.  Seleccione el archivo .dll y haga clic en **Abrir**.  
  
         El control aparece en el cuadro de diálogo.  
  
    4.  Confirme que el control está seleccionado y, a continuación, haga clic en **Aceptar**.  
  
         El control se agrega al **cuadro de herramientas**.  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a>No se puede depurar el control de usuario de Windows Forms o un componente  
 Si el control se deriva de la <xref:System.Windows.Forms.UserControl> (clase), puede depurar su comportamiento en tiempo de ejecución con el contenedor de prueba. Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Otros controles y componentes personalizados no son proyectos independientes. Deben hospedarse en una aplicación, como un proyecto de Windows Forms. Para depurar un control o componente, debe agregarlo a un proyecto de Windows Forms.  
  
#### <a name="to-debug-a-control-or-component"></a>Para depurar un control o componente  
  
1.  Para compilar la solución, en el menú **Compilar**, haga clic en **Compilar solución**.  
  
2.  En el menú **Archivo**, elija **Agregar** y, luego, elija **Nuevo proyecto** para agregar un proyecto de prueba a la aplicación.  
  
3.  En el cuadro de diálogo **Agregar nuevo proyecto**, elija **Aplicación de Windows** como tipo de proyecto.  
  
4.  En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** del nuevo proyecto. En el menú contextual, haga clic en **Agregar referencia** para agregar una referencia al proyecto que contiene el control o componente.  
  
5.  Crear una instancia de un control o componente en el proyecto de prueba. Si el componente está en el **cuadro de herramientas**, puede arrastrarlo a la superficie del diseñador o puede crear la instancia mediante programación, tal y como se muestra en el ejemplo de código siguiente.  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     Ahora puede depurar el control o componente como de costumbre.  
  
 Para obtener más información acerca de la depuración, consulte [Depuración en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) y [Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a>El evento se genera dos veces en el control o el componente heredado  
 Probablemente se debe a una cláusula `Handles` duplicada. Para obtener más información, consulte [Solución de problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a>Error en tiempo de diseño: "Error al crear el componente 'nombre de componente'"  
 El componente o el control deben proporcionar un constructor predeterminado sin parámetros. Cuando el entorno de diseño crea una instancia de un componente o control, no intenta proporcionar ningún parámetro a las sobrecargas del constructor que toman parámetros.  
  
## <a name="stathreadattribute"></a>STAThreadAttribute  
 El <xref:System.STAThreadAttribute> informa a common language runtime (CLR) que Windows Forms utiliza el modelo de subprocesamiento controlado simple. Podría observar un comportamiento imprevisto si no aplica este atributo al método `Main` de su aplicación de formularios Windows Forms. Por ejemplo, no pueden aparecer las imágenes de fondo para controles como <xref:System.Windows.Forms.ListView>. Algunos controles también pueden requerir este atributo para que los comportamientos de Autocompletar y arrastrar y colocar sean correctos.  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a>El icono del componente no aparece en el cuadro de herramientas  
 Cuando usas <xref:System.Drawing.ToolboxBitmapAttribute> para asociar un icono a su componente personalizado, el mapa de bits no aparece en el cuadro de herramientas para los componentes generados automáticamente. Para ver el mapa de bits, vuelva a cargar el control con el cuadro de diálogo **Elegir elementos del cuadro de herramientas**. Para obtener más información, vea [Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [Cómo: Comprobar el comportamiento de una clase UserControl en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 [Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 [Creación de componentes](https://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 [Solución de problemas de desarrollo en tiempo de diseño](https://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [Programar con componentes](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)
