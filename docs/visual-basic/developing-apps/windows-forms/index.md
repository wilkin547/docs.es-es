---
title: Fundamentos de las aplicaciones de Windows Forms
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: ef02662a5492f117b252e464e92ec46e7484ef66
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282170"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Conceptos básicos de las aplicaciones de Windows Forms (Visual Basic)

Una característica importante de Visual Basic es la capacidad de crear aplicaciones de Windows Forms que se ejecutan localmente en los equipos de los usuarios. Puede usar Visual Studio para crear la aplicación y la interfaz de usuario mediante Windows Forms. Una aplicación de Windows Forms se basa en las clases del espacio de nombres <xref:System.Windows.Forms>.

## <a name="designing-windows-forms-applications"></a>Diseño de aplicaciones de Windows Forms

Puede crear aplicaciones de Windows Forms y de servicios de Windows con Visual Studio. Para obtener más información, vea los temas siguientes:

- [Introducción a los formularios Windows Forms](/dotnet/desktop/winforms/getting-started-with-windows-forms). Proporciona información sobre cómo crear y programar Windows Forms.

- [Controles de Windows Forms](/dotnet/desktop/winforms/controls/). Es una recopilación de temas donde se detalla el uso de controles de Windows Forms.

- [Aplicaciones de servicios de Windows](../../../framework/windows-services/index.md). Muestra temas en los que se explica cómo crear servicios de Windows.

## <a name="building-rich-interactive-user-interfaces"></a>Compilación de interfaces de usuario completas e interactivas

Windows Forms es el componente cliente inteligente de .NET Framework y .NET Core (desde .NET Core 3.0). Se trata de un conjunto de bibliotecas administradas que habilitan tareas comunes de las aplicaciones, como leer y escribir en el sistema de archivos. Cuando se usa un entorno de desarrollo como Visual Studio, se pueden crear aplicaciones de Windows Forms que muestran información, solicitan datos a los usuarios y se comunican con equipos remotos a través de una red.

En Windows Forms, un formulario es una superficie visual en la que se muestra información al usuario. Normalmente, las aplicaciones de Windows Forms se compilan mediante la colocación de controles en los formularios y el desarrollo de respuestas a las acciones del usuario, como clics del mouse o presiones de teclas. Un *control* es un elemento de interfaz de usuario (UI) discreto que muestra datos o acepta la entrada de datos.

### <a name="events"></a>Events

Cuando un usuario realiza una acción en el formulario o en uno de sus controles, genera un evento. La aplicación reacciona a estos eventos mediante código y procesa los eventos cuando se producen. Para más información, consulte el artículo sobre [creación de controladores de eventos en Windows Forms](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms).

### <a name="controls"></a>Controles

Windows Forms contiene una serie de controles que se pueden colocar en los formularios: controles que muestran cuadros de texto, botones, cuadros desplegables, botones de radio e incluso páginas web. Para obtener una lista de todos los controles que puede usar en un formulario, consulte el artículo sobre [controles que se utilizan en formularios Windows Forms](/dotnet/desktop/winforms/controls/controls-to-use-on-windows-forms). Si un control existente no satisface sus necesidades, Windows Forms también permite crear controles personalizados mediante la clase <xref:System.Windows.Forms.UserControl>.

Windows Forms tiene controles de interfaz de usuario enriquecidos que emulan las características de las aplicaciones de tecnología avanzada como Microsoft Office. Con el control <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.MenuStrip>, puede crear barras de herramientas y menús que contienen texto e imágenes, muestran submenús y hospedan otros controles como cuadros de texto y cuadros combinados.

Con el diseñador de formularios de arrastrar y colocar de Visual Studio, puede crear fácilmente aplicaciones de Windows Forms: simplemente seleccione los controles con el cursor y colóquelos donde quiera en el formulario. El diseñador proporciona herramientas como líneas de cuadrícula y "líneas de ajuste" para minimizar la molestia de alinear los controles. Además, si usa Visual Studio o compila en la línea de comandos, puede emplear los controles <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> y <xref:System.Windows.Forms.SplitContainer> para crear diseños de formulario avanzados con el mínimo tiempo y esfuerzo.

### <a name="custom-ui-elements"></a>Elementos personalizados de interfaz de usuario

Por último, si debe crear sus propios elementos de interfaz de usuario personalizados, el espacio de nombres <xref:System.Drawing> contiene todas las clases que necesita para representar líneas, círculos y otras formas directamente en un formulario.

Para obtener información detallada sobre cómo usar estas características, vea los siguientes temas de la Ayuda.

|En|Vea|
|--------|---------|
|Crear una nueva aplicación de Windows Forms con Visual Studio|[Tutorial 1: Crear un visor de imágenes](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|Usar controles en formularios|[Cómo: Agregar controles a formularios Windows Forms](/dotnet/desktop/winforms/controls/how-to-add-controls-to-windows-forms)|
|Crear gráficos con <xref:System.Drawing>|[Introducción a la programación de gráficos](/dotnet/desktop/winforms/advanced/getting-started-with-graphics-programming)|
|Crear controles personalizados|[Cómo: Heredar de una clase UserControl](/dotnet/desktop/winforms/controls/how-to-inherit-from-the-usercontrol-class)|

## <a name="displaying-and-manipulating-data"></a>Mostrar y manipular datos

Muchas aplicaciones deben mostrar datos procedentes de una base de datos, archivo XML, servicio web XML u otro origen de datos. Windows Forms proporciona un control flexible denominado control <xref:System.Windows.Forms.DataGridView> para representar esos datos tabulares en un formato tradicional de filas y columnas, de modo que cada fragmento de datos ocupe su propia celda. Con <xref:System.Windows.Forms.DataGridView> puede personalizar el aspecto de celdas individuales, bloquear en su posición filas y columnas arbitrarias y mostrar controles complejos dentro de celdas, entre otras características.

La conexión a orígenes de datos a través de una red es una tarea sencilla con las aplicaciones smart client de Windows Forms. El componente <xref:System.Windows.Forms.BindingSource>, nuevo con Windows Forms en Visual Studio 2005 y .NET Framework 2.0, representa una conexión a un origen de datos y expone métodos para enlazar datos a controles, desplazarse al registro anterior y siguiente, modificar registros y volver a guardar los cambios en el origen. El control <xref:System.Windows.Forms.BindingNavigator> proporciona una interfaz sencilla en el componente <xref:System.Windows.Forms.BindingSource> para que los usuarios se desplacen por los registros.

### <a name="data-bound-controls"></a>Controles enlazados a datos

Puede crear controles enlazados a datos fácilmente mediante la ventana Orígenes de datos, que muestra orígenes de datos como bases de datos, servicios web y objetos del proyecto. Para crear controles enlazados a datos, arrastre los elementos desde esta ventana hasta los formularios de su proyecto. También puede enlazar controles existentes a datos si arrastra los objetos desde la ventana Orígenes de datos a los controles existentes.

### <a name="settings"></a>Configuración

Otro tipo de enlace de datos que puede administrar en Windows Forms es la configuración. La mayoría de las aplicaciones cliente inteligentes deben conservar cierta información sobre su estado de tiempo de ejecución, como el último tamaño conocido de los formularios, y conservar los datos de preferencias del usuario, como las ubicaciones predeterminadas de los archivos guardados. La característica de configuración de la aplicación aborda estos requisitos al proporcionar una manera sencilla de almacenar ambos tipos de configuración en el equipo cliente. Una vez definida mediante Visual Studio o un editor de código, la configuración se conserva como XML y se vuelve a leer automáticamente en la memoria en tiempo de ejecución.

Para obtener información detallada sobre cómo usar estas características, vea los siguientes temas de la Ayuda.

|En|Vea|
|--------|---------|
|Usar el componente <xref:System.Windows.Forms.BindingSource>|[Cómo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Diseñador](/dotnet/desktop/winforms/controls/bind-wf-controls-with-the-bindingsource)|
|Trabajar con orígenes de datos de ADO.NET|[Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de Windows Forms](/dotnet/desktop/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component)|
|Usar la ventana Orígenes de datos|[Tutorial: Mostrar datos en Windows Forms](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>Implementar aplicaciones en equipos cliente

Una vez escrita la aplicación, hay que enviarla a los usuarios para que puedan instalarla y ejecutarla en sus propios equipos cliente. Con la tecnología ClickOnce, puede implementar las aplicaciones desde Visual Studio con solo unos cuantos clics y proporcionar a los usuarios una dirección URL que apunte a la aplicación en Internet. ClickOnce administra todos los elementos y las dependencias de la aplicación y garantiza que está instalada correctamente en el equipo cliente.

Las aplicaciones ClickOnce se pueden configurar para ejecutarse únicamente cuando el usuario está conectado a la red, o para ejecutarse tanto en línea como sin conexión. Al especificar que una aplicación debe admitir el funcionamiento sin conexión, ClickOnce agrega un vínculo a la aplicación en el menú **Inicio** del usuario para que este pueda abrirla sin usar la dirección URL.

Cuando se actualiza la aplicación, se publica un nuevo manifiesto de implementación y una nueva copia de la aplicación en el servidor web. ClickOnce detecta que hay una actualización disponible y actualiza la instalación del usuario; no se requiere ninguna programación personalizada para actualizar los ensamblados antiguos.

Para obtener una introducción completa a ClickOnce, vea [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Para obtener información detallada sobre cómo usar estas características, vea los siguientes temas de la Ayuda:

|En|Vea|
|--------|---------|
|Implementar una aplicación con ClickOnce|[Cómo: Publicación de una aplicación ClickOnce mediante el Asistente para publicación](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Tutorial: Implementación manual de una aplicación ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Actualizar una implementación de ClickOnce|[Cómo: Administración de actualizaciones de aplicaciones ClickOnce](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Administrar la seguridad con ClickOnce|[Cómo: Habilitación de la configuración de seguridad ClickOnce](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>Otros controles y características

Hay muchas otras características en Windows Forms que simplifican y agilizan las tareas comunes de implementación, como la posibilidad de crear cuadros de diálogo, imprimir, agregar documentación y localizar la aplicación a varios idiomas. Además, Windows Forms se basa en el sólido sistema de seguridad de .NET, lo que permite publicar aplicaciones más seguras para los clientes.

Para obtener información detallada sobre cómo usar estas características, vea los siguientes temas de la Ayuda:

|En|Vea|
|--------|---------|
|Imprimir el contenido de un formulario|[Cómo: Imprimir gráficos en formularios Windows Forms](/dotnet/desktop/winforms/advanced/how-to-print-graphics-in-windows-forms)<br /><br /> [Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms](/dotnet/desktop/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms)|
|Más información sobre la seguridad de Windows Forms|[Información general sobre la seguridad en Windows Forms](/dotnet/desktop/winforms/security-in-windows-forms-overview)|

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Información general sobre formularios Windows Forms](/dotnet/desktop/winforms/windows-forms-overview)
- [My.Forms (objeto)](../../language-reference/objects/my-forms-object.md)
