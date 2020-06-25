---
title: Información general
description: Obtenga información acerca de cómo puede usar Windows Forms para crear clientes inteligentes que satisfagan las necesidades de las empresas y los usuarios finales de hoy en día.
ms.date: 03/30/2017
helpviewer_keywords:
- smart clients
- Windows Forms, about Windows Forms
ms.assetid: 3a2b6284-c8d6-4e1c-8c69-0bed38f38cd4
ms.openlocfilehash: 820d5bae54ecb5a868314197d6a7e45e097b57de
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325984"
---
# <a name="windows-forms-overview"></a>Información general de Windows Forms

La información general siguiente explica las ventajas de las aplicaciones smart client, las características principales de la programación de Windows Forms y cómo puede usar Windows Forms para compilar smart clients que satisfagan las necesidades actuales de las empresas y usuarios.

## <a name="windows-forms-and-smart-client-apps"></a>Aplicaciones de Windows Forms y Smart Client

 Con Windows Forms, puede desarrollar aplicaciones smart client. Las aplicaciones de *cliente inteligente* son aplicaciones gráficamente enriquecidas, fáciles de implementar y actualizar, que pueden funcionar con o sin conexión a Internet y que pueden acceder a los recursos del equipo local de un modo más seguro que las aplicaciones tradicionales basadas en Windows.

### <a name="build-rich-interactive-user-interfaces"></a>Cree interfaces de usuario completas e interactivas

 Windows Forms es una tecnología Smart Client para .NET Framework, un conjunto de bibliotecas administradas que simplifican las tareas comunes de las aplicaciones, como leer y escribir en el sistema de archivos. Cuando se usa un entorno de desarrollo como Visual Studio, se pueden crear aplicaciones Smart Client de Windows Forms que muestran información, solicitan a los usuarios la entrada de datos y se comunican con equipos remotos a través de una red.

 En Windows Forms, un *formulario* es una superficie visual en la que se muestra información al usuario. Normalmente, las aplicaciones de Windows Forms se compilan mediante la adición de controles a los formularios y el desarrollo de respuestas a las acciones del usuario, como clics del mouse o presiones de teclas. Un *control* es un elemento de interfaz de usuario (UI) discreto que muestra datos o acepta la entrada de datos.

 Cuando un usuario realiza una acción en un formulario o en uno de sus controles, la acción genera un evento. La aplicación reacciona a estos eventos mediante código y procesa los eventos cuando se producen. Para más información, consulte el artículo sobre [creación de controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md).

 Windows Forms contiene diversos controles que puede agregar a los formularios: controles que muestran cuadros de texto, botones, cuadros desplegables, botones de radio e incluso páginas web. Para obtener una lista de todos los controles que puede usar en un formulario, consulte el artículo sobre [controles que se utilizan en formularios Windows Forms](./controls/controls-to-use-on-windows-forms.md). Si un control existente no satisface sus necesidades, Windows Forms también permite crear controles personalizados mediante la clase <xref:System.Windows.Forms.UserControl>.

 Windows Forms tiene controles de interfaz de usuario enriquecidos que emulan las características de las aplicaciones de tecnología avanzada como Microsoft Office. Los controles <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.MenuStrip> le permiten crear barras de herramientas y menús que contienen texto e imágenes, muestran submenús y hospedan otros controles como cuadros de texto y cuadros combinados.

 Con la **Diseñador de Windows Forms** de arrastrar y colocar en Visual Studio, puede crear fácilmente aplicaciones de Windows Forms. Simplemente seleccione los controles con el cursor y agréguelos donde desee en el formulario. El diseñador proporciona herramientas como líneas de cuadrícula y líneas de ajuste para minimizar la molestia de alinear los controles. Y si usa Visual Studio o compilar en la línea de comandos, puede usar <xref:System.Windows.Forms.FlowLayoutPanel> los <xref:System.Windows.Forms.TableLayoutPanel> controles, y <xref:System.Windows.Forms.SplitContainer> para crear diseños de formularios avanzados en menos tiempo.

 Por último, si debe crear sus propios elementos de interfaz de usuario personalizados, el espacio de nombres <xref:System.Drawing> contiene una gran selección de clases para representar líneas, círculos y otras formas directamente en un formulario.

> [!NOTE]
> Los controles de Windows Forms no están diseñados para que se serialicen entre dominios de aplicación. Por esta razón, Microsoft no admite que un control de Windows Forms traspase un límite de <xref:System.AppDomain>, ni siquiera si el tipo base <xref:System.Windows.Controls.Control> de <xref:System.MarshalByRefObject> pareciera indicar que esto es posible. Se admiten las aplicaciones de Windows Forms que tienen varios dominios de aplicación siempre y cuando no se pasen controles de Windows Forms a través de los límites del dominio de aplicación.

#### <a name="create-forms-and-controls"></a>Crear formularios y controles

Para obtener información detallada sobre cómo usar estas características, vea los siguientes temas de ayuda.

|Descripción|Tema de ayuda|
|-----------------|----------------|
|Usar controles en formularios|[Cómo: Agregar controles a formularios Windows Forms](./controls/how-to-add-controls-to-windows-forms.md)|
|Usar el control <xref:System.Windows.Forms.ToolStrip>|[Procedimiento para crear un control ToolStrip básico con elementos estándar mediante el diseñador](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md)|
|Crear gráficos con <xref:System.Drawing>|[Introducción a la programación de gráficos](./advanced/getting-started-with-graphics-programming.md)|
|Creación de controles personalizados|[Procedimiento para heredar de la clase UserControl](./controls/how-to-inherit-from-the-usercontrol-class.md)|

### <a name="display-and-manipulate-data"></a>Mostrar y manipular datos
 Muchas aplicaciones deben mostrar datos procedentes de una base de datos, archivo XML, servicio web XML u otro origen de datos. Windows Forms proporciona un control flexible denominado control <xref:System.Windows.Forms.DataGridView> para mostrar esa información tabulada en un formato tradicional de filas y columnas, de modo que cada dato ocupe su propia celda. Al usar <xref:System.Windows.Forms.DataGridView>, puede personalizar la apariencia de celdas individuales, bloquear en su posición filas y columnas arbitrarias y mostrar controles complejos dentro de las celdas, entre otras características.

 La conexión a orígenes de datos a través de una red es una tarea sencilla con las aplicaciones smart client de Windows Forms. El <xref:System.Windows.Forms.BindingSource> componente representa una conexión a un origen de datos y expone métodos para enlazar datos a controles, navegando a los registros anteriores y siguientes, editando registros y guardando los cambios de nuevo en el origen original. El control <xref:System.Windows.Forms.BindingNavigator> proporciona una interfaz sencilla en el componente <xref:System.Windows.Forms.BindingSource> para que los usuarios se desplacen por los registros.

 Puede crear fácilmente controles enlazados a datos en la ventana Orígenes de datos. La ventana muestra los orígenes de datos como bases de datos, servicios web y objetos en el proyecto. Para crear controles enlazados a datos, arrastre los elementos desde esta ventana hasta los formularios de su proyecto. También puede enlazar controles existentes a datos si arrastra los objetos desde la ventana Orígenes de datos a los controles existentes.

 Otro tipo de enlace de datos que puede administrar en Windows Forms es el de *configuración*. La mayoría de las aplicaciones smart client deben conservar cierta información sobre su estado de tiempo de ejecución, como el último tamaño conocido de los formularios, y conservar los datos de preferencias del usuario, como las ubicaciones predeterminadas de los archivos guardados. La característica Configuración de la aplicación aborda estos requisitos al proporcionar una manera sencilla de almacenar ambos tipos de configuración en el equipo cliente. Después de definir esta configuración mediante Visual Studio o un editor de código, la configuración se conserva como XML y se vuelve a leer automáticamente en la memoria en tiempo de ejecución.

#### <a name="display-and-manipulate-data"></a>Mostrar y manipular datos

Para obtener información detallada sobre cómo usar estas características, vea los siguientes temas de ayuda.

|Descripción|Tema de ayuda|
|-----------------|----------------|
|Usar el componente <xref:System.Windows.Forms.BindingSource>|[Procedimiento para enlazar controles de formularios Windows Forms con el componente BindingSource mediante el diseñador](./controls/bind-wf-controls-with-the-bindingsource.md)|
|Trabajar con orígenes de datos de ADO.NET|[Procedimiento para ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms](./controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Usar la ventana Orígenes de datos|[Enlazar controles de Windows Forms a datos en Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)|
|Uso de la configuración de la aplicación|[Procedimiento para crear la configuración de la aplicación](./advanced/how-to-create-application-settings.md)|

### <a name="deploy-apps-to-client-computers"></a>Implementar aplicaciones en equipos cliente

Una vez escrita la aplicación, hay que enviarla a los usuarios para que puedan instalarla y ejecutarla en sus equipos cliente. Al usar la tecnología ClickOnce, puede implementar sus aplicaciones desde Visual Studio con tan solo unos clics y proporcionar a los usuarios una dirección URL que apunte a la aplicación en la Web. ClickOnce administra todos los elementos y dependencias de la aplicación y garantiza que la aplicación se instala correctamente en el equipo cliente.

Las aplicaciones ClickOnce se pueden configurar para que se ejecuten solo cuando el usuario está conectado a la red o para ejecutarse tanto en línea como sin conexión. Cuando se especifica que una aplicación debe admitir el funcionamiento sin conexión, ClickOnce agrega un vínculo a la aplicación en el menú **Inicio** del usuario. El usuario puede entonces abrir la aplicación sin usar la dirección URL.

Cuando se actualiza la aplicación, se publica un nuevo manifiesto de implementación y una nueva copia de la aplicación en el servidor web. ClickOnce detectará que hay una actualización disponible y actualizará la instalación del usuario. no se requiere ninguna programación personalizada para actualizar los ensamblados antiguos.

#### <a name="deploy-clickonce-apps"></a>Implementación de aplicaciones ClickOnce

Para obtener una introducción completa a ClickOnce, consulte [seguridad e implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Para obtener información detallada sobre cómo usar estas características, vea los siguientes temas de ayuda.

|Descripción|Tema de ayuda|
|-----------------|----------------|
|Implementar una aplicación mediante ClickOnce|[Cómo: Publicar una aplicación ClickOnce sin usar el Asistente para publicación](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Tutorial: Implementar manualmente una aplicación ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Actualizar una implementación ClickOnce|[Cómo: administrar actualizaciones de una aplicación ClickOnce](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Administrar la seguridad con ClickOnce|[Cómo: Habilitación de la configuración de seguridad ClickOnce](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

### <a name="other-controls-and-features"></a>Otros controles y características

Hay muchas otras características en Windows Forms que simplifican y agilizan las tareas comunes de implementación, como la posibilidad de crear cuadros de diálogo, imprimir, agregar ayuda y documentación, y localizar la aplicación a varios idiomas. Además, Windows Forms se basa en el sólido sistema de seguridad de la .NET Framework. Con este sistema, puede publicar aplicaciones más seguras para sus clientes.

#### <a name="implement-other-controls-and-features"></a>Implementar otros controles y características

Para obtener información detallada sobre cómo usar estas características, vea los siguientes temas de ayuda.

|Descripción|Tema de ayuda|
|-----------------|----------------|
|Imprimir el contenido de un formulario|[Procedimiento para imprimir gráficos en formularios Windows Forms](./advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Procedimiento para imprimir un archivo de texto de varias páginas en formularios Windows Forms](./advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Más información sobre la seguridad de Windows Forms|[Información general sobre la seguridad en formularios Windows Forms](security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Vea también

- [Introducción con Windows Forms](getting-started-with-windows-forms.md)
- [Crear un nuevos Windows Forms](creating-a-new-windows-form.md)
- [Información sobre el control ToolStrip](./controls/toolstrip-control-overview-windows-forms.md)
- [Información general del control DataGridView](./controls/datagridview-control-overview-windows-forms.md)
- [Información general sobre el componente BindingSource](./controls/bindingsource-component-overview.md)
- [Introducción a la configuración de la aplicación](./advanced/application-settings-overview.md)
- [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
