---
title: "Conceptos básicos de las aplicaciones de Windows Forms (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2082d8169dc325b86957e7a54c6e49304660aa94
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="windows-forms-application-basics-visual-basic"></a>Conceptos básicos de las aplicaciones de Windows Forms (Visual Basic)
Una parte importante de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] es la capacidad para crear aplicaciones de Windows Forms que se ejecutan localmente en equipos de los usuarios. Puede usar Visual Studio para crear la interfaz de usuario y la aplicación con formularios Windows Forms. Una aplicación de formularios Windows Forms se basa en las clases de la <xref:System.Windows.Forms> espacio de nombres.  
  
## <a name="designing-windows-forms-applications"></a>Las aplicaciones de diseño de Windows Forms  
 Puede crear formularios Windows Forms y aplicaciones de servicio de Windows con [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]. Para obtener más información, vea los temas siguientes:  
  
-   [Introducción a Windows Forms](../../../../docs/framework/winforms/getting-started-with-windows-forms.md). Proporciona información sobre cómo crear y programar formularios Windows Forms.  
   
-   [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md). Colección de temas que detalla el uso de controles de formularios Windows Forms.  
  
-   [Las aplicaciones de servicio de Windows](../../../../docs/framework/windows-services/index.md). Enumera los temas que explican cómo crear servicios de Windows.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Compilación de interfaces de usuario completas e interactivas  
 Formularios Windows Forms es el componente de cliente inteligente de la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], un conjunto de bibliotecas administradas que permiten que las tareas de aplicación comunes, como leer y escribir en el sistema de archivos. Usar un entorno de desarrollo como [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], puede crear aplicaciones de Windows Forms que muestran información, pedir la opinión de los usuarios y se comunican con equipos remotos a través de una red.  
  
 En Windows Forms, un formulario es una superficie visual en el que se muestra información al usuario. Normalmente las aplicaciones de formularios Windows Forms se generan colocar controles en formularios y desarrollo de respuestas a las acciones del usuario, como clics del mouse o presiones de teclas. Un *control* es un elemento de interfaz de usuario (UI) discreto que muestra datos o acepta la entrada de datos.  
  
### <a name="events"></a>Eventos  
 Cuando un usuario realiza una acción en un formulario o uno de sus controles, genera un evento. La aplicación reacciona a estos eventos mediante código y procesa los eventos cuando se producen. Para más información, consulte el artículo sobre [creación de controladores de eventos en Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
### <a name="controls"></a>Controles  
 Windows Forms contiene diversos controles que se pueden colocar en los formularios: controles que muestran cuadros de texto, botones, cuadros desplegables, botones de radio e incluso páginas Web. Para obtener una lista de todos los controles que puede usar en un formulario, consulte el artículo sobre [controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md). Si un control existente no satisface sus necesidades, Windows Forms también permite crear controles personalizados mediante la clase <xref:System.Windows.Forms.UserControl>.  
  
 Windows Forms tiene controles de interfaz de usuario enriquecidos que emulan las características de las aplicaciones de tecnología avanzada como Microsoft Office. Mediante el <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.MenuStrip> (control), puede crear barras de herramientas y menús que contienen texto e imágenes, muestran submenús y hospedan otros controles como cuadros de texto y cuadros combinados.  
  
 Con el [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Diseñador de formularios de arrastrar y colocar, puede crear fácilmente aplicaciones de Windows Forms: basta con seleccionar los controles con el cursor y colóquelos donde desee en el formulario. El diseñador proporciona herramientas como líneas de cuadrícula y "líneas de ajuste" para minimizar la molestia de alinear los controles. Y si utiliza [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] o compilación en la línea de comandos, puede usar el <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> y <xref:System.Windows.Forms.SplitContainer> diseños con el mínimo tiempo y esfuerzo de formularios de controles para crear avanzadas.  
  
### <a name="custom-ui-elements"></a>Elementos de interfaz de usuario personalizada  
 Por último, si debe crear sus propios elementos de interfaz de usuario personalizados, el <xref:System.Drawing> espacio de nombres contiene todas las clases necesarias para representar líneas, círculos y otras formas directamente en un formulario.  
  
 Para obtener información detallada sobre el uso de estas características, vea los siguientes temas de ayuda.  
  
|Para|Vea|  
|--------|---------|  
|Cree una nueva aplicación de Windows Forms con[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]|[Tutorial: Crear un formulario Windows Forms sencillo](http://msdn.microsoft.com/en-us/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Usar controles en formularios|[Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|   
|Crear gráficos con<xref:System.Drawing>|[Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|Crear controles personalizados|[Cómo: Heredar de una clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
## <a name="displaying-and-manipulating-data"></a>Mostrar y manipular datos  
 Muchas aplicaciones deben mostrar datos procedentes de una base de datos, archivo XML, servicio web XML u otro origen de datos. Windows Forms proporciona un control flexible denominado el <xref:System.Windows.Forms.DataGridView> control para representar esa información tabulada en un formato tradicional de filas y columnas, por lo que cada dato ocupe su propia celda. Con <xref:System.Windows.Forms.DataGridView> puede personalizar la apariencia de celdas individuales, bloquear filas y columnas en su lugar arbitrarias y mostrar controles complejos dentro de las celdas, entre otras características.  
  
 La conexión a orígenes de datos a través de una red es una tarea sencilla con las aplicaciones smart client de Windows Forms. El componente <xref:System.Windows.Forms.BindingSource> —introducido en Windows Forms en [!INCLUDE[vsprvslong](~/includes/vsprvslong-md.md)] y [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)]— representa una conexión a un origen de datos y expone métodos para enlazar datos a controles, desplazarse por los registros anteriores y siguientes, modificar registros y guardar los cambios en el origen. El control <xref:System.Windows.Forms.BindingNavigator> proporciona una interfaz sencilla en el componente <xref:System.Windows.Forms.BindingSource> para que los usuarios se desplacen por los registros.  
  
### <a name="data-bound-controls"></a>Controles enlazados a datos  
 Puede crear controles enlazados a datos fácilmente mediante la ventana Orígenes de datos, que muestra los orígenes de datos tales como bases de datos, servicios Web y objetos del proyecto. Para crear controles enlazados a datos, arrastre los elementos desde esta ventana hasta los formularios de su proyecto. También puede enlazar controles existentes a datos si arrastra los objetos desde la ventana Orígenes de datos a los controles existentes.  
  
### <a name="settings"></a>Configuración  
 Otro tipo de enlace de datos que se puede administrar en Windows Forms es la configuración. Mayoría de las aplicaciones smart client debe conservar cierta información sobre su estado de tiempo de ejecución, como el último tamaño conocido de los formularios y conservar los datos de preferencia del usuario, como las ubicaciones predeterminadas de los archivos guardados. La característica de configuración de la aplicación aborda estos requisitos al proporcionar una manera sencilla de almacenar ambos tipos de configuración en el equipo cliente. Una vez definido mediante [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] o un editor de código, esta configuración se conserva con formato XML y se lee automáticamente en la memoria en tiempo de ejecución.  
  
 Para obtener información detallada sobre el uso de estas características, vea los siguientes temas de ayuda.  
  
|Para|Vea|  
|--------|---------|  
|Use la <xref:System.Windows.Forms.BindingSource> componente|[Cómo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Diseñador](../../../../docs/framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|Trabajar con [!INCLUDE[vstecado](~/includes/vstecado-md.md)] orígenes de datos|[Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de Windows Forms](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|Utilice la ventana de orígenes de datos|[Tutorial: Mostrar datos en Windows Forms](/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Implementar aplicaciones en equipos cliente  
 Una vez escrita la aplicación, debe enviar a los usuarios para que puedan instalar y ejecutar en sus equipos cliente. Mediante el [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] tecnología, puede implementar aplicaciones desde [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] mediante unos pocos clics y proporcionar a los usuarios con una dirección URL que apunte a la aplicación en la Web. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]administra todos los elementos y dependencias de la aplicación y se asegura de que la aplicación está instalada correctamente en el equipo cliente.  
  
 Las aplicaciones [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] se pueden configurar para ejecutarse únicamente cuando el usuario está conectado a la red, o para ejecutarse tanto en línea como sin conexión. Cuando se especifica que una aplicación debe admitir el funcionamiento sin conexión, [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] agrega un vínculo a la aplicación en el usuario **iniciar** menú, por lo que el usuario pueda abrirla sin utilizar la dirección URL.  
  
 Cuando se actualiza la aplicación, se publica un nuevo manifiesto de implementación y una nueva copia de la aplicación en el servidor web. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]detecta que hay una actualización disponible y actualiza la instalación del usuario; no se requiere ninguna programación personalizada para actualizar los ensamblados antiguos.  
  
 Para obtener una introducción completa a [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)], consulte [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Para obtener información detallada sobre el uso de estas características, vea los temas de ayuda siguientes:  
  
|Para|Vea|  
|--------|---------|  
|Implementar una aplicación con[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Cómo: Publicar una aplicación ClickOnce mediante el Asistente para publicación](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Tutorial: Implementar manualmente una aplicación ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Actualización de un [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] implementación|[Cómo: Administrar actualizaciones de aplicaciones ClickOnce](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Administrar la seguridad con[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Cómo: Habilitar la configuración de seguridad de ClickOnce](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Otros controles y características  
 Hay muchas otras características en Windows Forms que simplifican y agilizan las tareas comunes de implementación, como la posibilidad de crear cuadros de diálogo, imprimir, agregar ayuda y documentación, y localizar la aplicación a varios idiomas. Además, Windows Forms se basa en el sólido sistema de seguridad de la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], lo que le permite publicar aplicaciones más seguras para sus clientes.  
  
 Para obtener información detallada sobre el uso de estas características, vea los temas de ayuda siguientes:  
  
|Para|Vea|  
|--------|---------|  
|Imprimir el contenido de un formulario|[Cómo: Imprimir gráficos en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|   
|Más información sobre la seguridad de Windows Forms|[Información general sobre la seguridad en Windows Forms](../../../../docs/framework/winforms/security-in-windows-forms-overview.md)|  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Información general sobre formularios Windows Forms](../../../../docs/framework/winforms/windows-forms-overview.md)  
 [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)
