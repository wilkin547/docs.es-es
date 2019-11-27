---
title: Fundamentos de las aplicaciones de Windows Forms
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 1aa1edf0130e388c6cc87662d83591f41a8e2325
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349164"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Conceptos básicos de las aplicaciones de Windows Forms (Visual Basic)

Una parte importante de Visual Basic es la capacidad de crear Windows Forms aplicaciones que se ejecutan localmente en los equipos de los usuarios. Puede usar Visual Studio para crear la aplicación y la interfaz de usuario mediante Windows Forms. Una aplicación Windows Forms se basa en las clases del espacio de nombres <xref:System.Windows.Forms>.

## <a name="designing-windows-forms-applications"></a>Diseño de aplicaciones Windows Forms

Puede crear Windows Forms y aplicaciones de servicios de Windows con Visual Studio. Para obtener más información, vea los temas siguientes:

- [Introducción con Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Proporciona información sobre cómo crear y programar Windows Forms.

- [Windows Forms controles](../../../framework/winforms/controls/index.md). Colección de temas que detallan el uso de controles de Windows Forms.

- [Aplicaciones de servicios de Windows](../../../framework/windows-services/index.md). Muestra temas en los que se explica cómo crear servicios de Windows.

## <a name="building-rich-interactive-user-interfaces"></a>Compilación de interfaces de usuario completas e interactivas

Windows Forms es el componente de cliente inteligente de la .NET Framework, un conjunto de bibliotecas administradas que permiten tareas de aplicación comunes, como la lectura y la escritura en el sistema de archivos. Con un entorno de desarrollo como Visual Studio, puede crear Windows Forms aplicaciones que muestran información, solicitan a los usuarios la entrada de datos y se comunican con equipos remotos a través de una red.

En Windows Forms, un formulario es una superficie visual en la que se muestra información al usuario. Normalmente, las aplicaciones Windows Forms se compilan colocando controles en formularios y desarrollando respuestas a las acciones del usuario, como clics del mouse o presiones de teclas. Un *control* es un elemento de interfaz de usuario (UI) discreto que muestra datos o acepta la entrada de datos.

### <a name="events"></a>Eventos

Cuando un usuario realiza una acción en el formulario o en uno de sus controles, genera un evento. La aplicación reacciona a estos eventos mediante código y procesa los eventos cuando se producen. Para más información, consulte el artículo sobre [creación de controladores de eventos en Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).

### <a name="controls"></a>Controles

Windows Forms contiene diversos controles que puede colocar en formularios: controles que muestran cuadros de texto, botones, cuadros desplegables, botones de radio e incluso páginas Web. Para obtener una lista de todos los controles que puede usar en un formulario, consulte el artículo sobre [controles que se utilizan en formularios Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Si un control existente no satisface sus necesidades, Windows Forms también permite crear controles personalizados mediante la clase <xref:System.Windows.Forms.UserControl>.

Windows Forms tiene controles de interfaz de usuario enriquecidos que emulan las características de las aplicaciones de tecnología avanzada como Microsoft Office. Con el control <xref:System.Windows.Forms.ToolStrip> y el <xref:System.Windows.Forms.MenuStrip>, puede crear barras de herramientas y menús que contienen texto e imágenes, muestran submenús y hospedan otros controles como cuadros de texto y cuadros combinados.

Con el diseñador de formularios de arrastrar y colocar de Visual Studio, puede crear fácilmente aplicaciones de Windows Forms: simplemente seleccione los controles con el cursor y colóquelos donde desee en el formulario. El diseñador proporciona herramientas como líneas de cuadrícula y "líneas de ajuste" para aprovechar las molestias de alinear los controles. Y si usa Visual Studio o compilar en la línea de comandos, puede usar los controles <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> y <xref:System.Windows.Forms.SplitContainer> para crear diseños de formulario avanzados con tiempo y esfuerzo mínimos.

### <a name="custom-ui-elements"></a>Elementos de interfaz de usuario personalizados

Por último, si debe crear sus propios elementos de interfaz de usuario personalizados, el espacio de nombres <xref:System.Drawing> contiene todas las clases que necesita para representar líneas, círculos y otras formas directamente en un formulario.

Para obtener información paso a paso sobre el uso de estas características, vea los siguientes temas de ayuda.

|Para|Consulte|
|--------|---------|
|Creación de una nueva aplicación de Windows Forms con Visual Studio|[Tutorial 1: crear un visor de imágenes](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|Usar controles en formularios|[Cómo: Agregar controles a Windows Forms](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|
|Crear gráficos con <xref:System.Drawing>|[Introducción a la programación de gráficos](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|
|Crear controles personalizados|[Cómo: Heredar de una clase UserControl](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|

## <a name="displaying-and-manipulating-data"></a>Mostrar y manipular datos

Muchas aplicaciones deben mostrar datos procedentes de una base de datos, archivo XML, servicio web XML u otro origen de datos. Windows Forms proporciona un control flexible denominado control de <xref:System.Windows.Forms.DataGridView> para representar estos datos tabulares en un formato tradicional de filas y columnas, de modo que cada dato ocupe su propia celda. Con <xref:System.Windows.Forms.DataGridView> puede personalizar la apariencia de celdas individuales, bloquear filas y columnas arbitrarias en contexto y mostrar controles complejos dentro de las celdas, entre otras características.

La conexión a orígenes de datos a través de una red es una tarea sencilla con las aplicaciones smart client de Windows Forms. El componente de <xref:System.Windows.Forms.BindingSource>, nuevo con Windows Forms en Visual Studio 2005 y el .NET Framework 2,0, representa una conexión a un origen de datos y expone métodos para enlazar datos a controles, desplazarse a los registros anteriores y siguientes, modificar registros y guardar los cambios de nuevo en el origen original. El control <xref:System.Windows.Forms.BindingNavigator> proporciona una interfaz sencilla en el componente <xref:System.Windows.Forms.BindingSource> para que los usuarios se desplacen por los registros.

### <a name="data-bound-controls"></a>Controles enlazados a datos

Puede crear fácilmente controles enlazados a datos mediante la ventana orígenes de datos, que muestra los orígenes de datos como bases de datos, servicios web y objetos en el proyecto. Para crear controles enlazados a datos, arrastre los elementos desde esta ventana hasta los formularios de su proyecto. También puede enlazar controles existentes a datos si arrastra los objetos desde la ventana Orígenes de datos a los controles existentes.

### <a name="settings"></a>Configuración

Otro tipo de enlace de datos que puede administrar en Windows Forms es el de configuración. La mayoría de las aplicaciones cliente inteligentes deben conservar cierta información sobre su estado de tiempo de ejecución, como el último tamaño conocido de los formularios, y conservar los datos de las preferencias de usuario, como las ubicaciones predeterminadas para los archivos guardados. La característica de configuración de la aplicación aborda estos requisitos al proporcionar una manera sencilla de almacenar ambos tipos de configuración en el equipo cliente. Una vez definida con Visual Studio o un editor de código, esta configuración se conserva como XML y se vuelve a leer automáticamente en la memoria en tiempo de ejecución.

Para obtener información paso a paso sobre el uso de estas características, vea los siguientes temas de ayuda.

|Para|Consulte|
|--------|---------|
|Usar el componente de <xref:System.Windows.Forms.BindingSource>|[Cómo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Diseñador](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|
|Trabajar con orígenes de datos de ADO.NET|[Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de Windows Forms](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Usar la ventana orígenes de datos|[Tutorial: Mostrar datos en Windows Forms](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>Implementar aplicaciones en equipos cliente

Una vez que haya escrito la aplicación, debe enviarla a los usuarios para que puedan instalarla y ejecutarla en sus equipos cliente. Con la tecnología ClickOnce, puede implementar sus aplicaciones desde Visual Studio con tan solo unos clics y proporcionar a los usuarios una dirección URL que apunte a la aplicación en la Web. ClickOnce administra todos los elementos y dependencias de la aplicación y garantiza que la aplicación está instalada correctamente en el equipo cliente.

Las aplicaciones ClickOnce se pueden configurar para que se ejecuten solo cuando el usuario está conectado a la red o para ejecutarse tanto en línea como sin conexión. Cuando se especifica que una aplicación debe admitir el funcionamiento sin conexión, ClickOnce agrega un vínculo a la aplicación en el menú **Inicio** del usuario, para que el usuario pueda abrirla sin usar la dirección URL.

Cuando se actualiza la aplicación, se publica un nuevo manifiesto de implementación y una nueva copia de la aplicación en el servidor web. ClickOnce detecta que hay una actualización disponible y actualiza la instalación del usuario; no se requiere ninguna programación personalizada para actualizar los ensamblados antiguos.

Para obtener una introducción completa a ClickOnce, consulte [seguridad e implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Para obtener información paso a paso sobre el uso de estas características, vea los siguientes temas de ayuda:

|Para|Consulte|
|--------|---------|
|Implementar una aplicación con ClickOnce|[Cómo: Publicar una aplicación ClickOnce mediante el Asistente para publicación](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Tutorial: Implementar manualmente una aplicación ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Actualizar una implementación ClickOnce|[Cómo: Administrar actualizaciones de aplicaciones ClickOnce](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Administrar la seguridad con ClickOnce|[Cómo: Habilitar la configuración de seguridad de ClickOnce](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>Otros controles y características

Hay muchas otras características en Windows Forms que simplifican y agilizan las tareas comunes de implementación, como la posibilidad de crear cuadros de diálogo, imprimir, agregar ayuda y documentación, y localizar la aplicación a varios idiomas. Además, Windows Forms se basa en el sólido sistema de seguridad de la .NET Framework, lo que le permite publicar aplicaciones más seguras para sus clientes.

Para obtener información paso a paso sobre el uso de estas características, vea los siguientes temas de ayuda:

|Para|Consulte|
|--------|---------|
|Imprimir el contenido de un formulario|[Cómo: Imprimir gráficos en Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Más información sobre la seguridad de Windows Forms|[Información general sobre la seguridad en Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Información general sobre formularios Windows Forms](../../../framework/winforms/windows-forms-overview.md)
- [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)
