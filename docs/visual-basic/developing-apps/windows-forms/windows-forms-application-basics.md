---
title: "Fundamentos de la aplicación (Visual Basic) de Windows Forms | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8275d3c06ebd89254a07127b4850d32ef0580830
ms.lasthandoff: 03/13/2017

---
# <a name="windows-forms-application-basics-visual-basic"></a>Conceptos básicos de las aplicaciones de Windows Forms (Visual Basic)
Una parte importante de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] es la capacidad de crear aplicaciones de Windows Forms que se ejecuten localmente en los equipos de los usuarios. Puede utilizar Visual Studio para crear la interfaz de usuario y la aplicación con formularios Windows Forms. Una aplicación de formularios Windows Forms se basa en las clases de la <xref:System.Windows.Forms>espacio de nombres.</xref:System.Windows.Forms>  
  
## <a name="designing-windows-forms-applications"></a>Diseño de Windows Forms aplicaciones  
 Puede crear formularios Windows Forms y aplicaciones de servicio de Windows con [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]. Para obtener más información, vea los temas siguientes:  
  
-   [Introducción a formularios Windows Forms](https://msdn.microsoft.com/library/ms229601.aspx). Proporciona información sobre cómo crear y programar formularios Windows Forms.  
   
-   [Controles de formularios Windows Forms](https://msdn.microsoft.com/library/ettb6e2a.aspx). Colección de temas que detallan el uso de controles de formularios Windows Forms.  
  
-   [Aplicaciones de servicios de Windows](https://msdn.microsoft.com/library/y817hyb6.aspx). Muestra temas que explican cómo crear servicios de Windows.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Compilación de interfaces de usuario completas e interactivas  
 Windows Forms es el componente de cliente inteligente de la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], un conjunto de bibliotecas administradas que simplifican tareas de aplicación comunes, como leer y escribir en el sistema de archivos. Utilizando un entorno de desarrollo como [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], puede crear aplicaciones de Windows Forms que muestran información, solicitan a los usuarios la entrada y comunicarán con equipos remotos a través de una red.  
  
 En Windows Forms, un formulario es una superficie visual en la que se muestra información al usuario. Normalmente las aplicaciones de formularios Windows Forms se generan colocar controles en formularios y desarrollar respuestas a las acciones del usuario, como clics del mouse o presiones de teclas. Un *control* es un elemento de interfaz de usuario discreto que muestra datos o acepta la entrada de datos.  
  
### <a name="events"></a>Eventos  
 Cuando un usuario hace algo en su formulario o uno de sus controles, genera un evento. La aplicación reacciona a estos eventos mediante código y procesa los eventos cuando se producen. Para obtener más información, consulte [crear controladores de eventos en formularios Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx).  
  
### <a name="controls"></a>Controles  
 Windows Forms contiene diversos controles que puede colocar en los formularios: controles que muestran cuadros de texto, botones, cuadros desplegables, botones de radio e incluso páginas Web. Para obtener una lista de todos los controles que puede utilizar en un formulario, consulte [controles que se utilizan en formularios Windows Forms](https://msdn.microsoft.com/library/3xdhey7w.aspx). Si un control existente no satisface sus necesidades, Windows Forms también permite la creación de controles personalizados mediante la <xref:System.Windows.Forms.UserControl>clase.</xref:System.Windows.Forms.UserControl>  
  
 Windows Forms tiene controles de interfaz de usuario enriquecidos que emulan las características de las aplicaciones de tecnología avanzada como Microsoft Office. Con el <xref:System.Windows.Forms.ToolStrip>y <xref:System.Windows.Forms.MenuStrip>control, puede crear barras de herramientas y menús que contienen texto e imágenes, muestran submenús y hospedan otros controles como cuadros de texto y cuadros combinados.</xref:System.Windows.Forms.MenuStrip> </xref:System.Windows.Forms.ToolStrip>  
  
 Con el [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] el Diseñador de formularios de arrastrar y colocar, puede crear fácilmente aplicaciones de Windows Forms: simplemente seleccione los controles con el cursor y colóquelos donde desee en el formulario. El diseñador proporciona herramientas como líneas de cuadrícula y "líneas de ajuste" para minimizar la molestia de alinear controles. Y si utiliza [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] o compila en la línea de comandos, puede utilizar el <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel>y <xref:System.Windows.Forms.SplitContainer>diseños con el mínimo tiempo y esfuerzo de formularios de controles para crear avanzadas.</xref:System.Windows.Forms.SplitContainer> </xref:System.Windows.Forms.TableLayoutPanel> </xref:System.Windows.Forms.FlowLayoutPanel>  
  
### <a name="custom-ui-elements"></a>Elementos de interfaz de usuario personalizada  
 Por último, si debe crear sus propios elementos de interfaz de usuario personalizados, el <xref:System.Drawing>espacio de nombres contiene todas las clases necesarias para representar líneas, círculos y otras formas directamente en un formulario.</xref:System.Drawing>  
  
 Para obtener información detallada sobre el uso de estas características, vea los siguientes temas de ayuda.  
  
|Para|Vea|  
|--------|---------|  
|Cree una nueva aplicación de Windows Forms con[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]|[Tutorial: Crear un formulario Windows Forms sencillo](http://msdn.microsoft.com/en-us/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Usar controles en formularios|[Cómo: agregar controles a formularios Windows Forms](https://msdn.microsoft.com/library/0h5y8567.aspx)|   
|Crear gráficos con<xref:System.Drawing></xref:System.Drawing>|[Introducción a la programación de gráficos](https://msdn.microsoft.com/library/da0f23z7.aspx)|  
|Crear controles personalizados|[Cómo: heredar de la clase UserControl](https://msdn.microsoft.com/library/00ctb4z0.aspx)|  
  
## <a name="displaying-and-manipulating-data"></a>Mostrar y manipular datos  
 Muchas aplicaciones deben mostrar datos procedentes de una base de datos, archivo XML, servicio web XML u otro origen de datos. Windows Forms ofrece un control flexible denominado el <xref:System.Windows.Forms.DataGridView>control para mostrar esta información tabulada en un formato tradicional de filas y columnas, por lo que cada dato ocupe su propia celda.</xref:System.Windows.Forms.DataGridView> Con <xref:System.Windows.Forms.DataGridView>puede personalizar la apariencia de celdas individuales, bloquear filas y columnas en su lugar arbitrarias y mostrar controles complejos dentro de las celdas, entre otras características.</xref:System.Windows.Forms.DataGridView>  
  
 La conexión a orígenes de datos a través de una red es una tarea sencilla con las aplicaciones smart client de Windows Forms. El <xref:System.Windows.Forms.BindingSource>, componente, nuevo en Windows Forms en [!INCLUDE[vsprvslong](../../../csharp/misc/includes/vsprvslong_md.md)] y [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)], representa una conexión a un origen de datos y expone métodos para enlazar datos a controles, desplazarse por los registros anteriores y siguientes, modificar registros y guardar los cambios en el origen original.</xref:System.Windows.Forms.BindingSource> El <xref:System.Windows.Forms.BindingNavigator>control proporciona una interfaz sencilla en el <xref:System.Windows.Forms.BindingSource>componente para que los usuarios desplazarse por los registros.</xref:System.Windows.Forms.BindingSource> </xref:System.Windows.Forms.BindingNavigator>  
  
### <a name="data-bound-controls"></a>Controles enlazados a datos  
 Puede crear controles enlazados a datos fácilmente mediante la ventana Orígenes de datos, que muestra los orígenes de datos como bases de datos, servicios Web y objetos en el proyecto. Para crear controles enlazados a datos, arrastre los elementos desde esta ventana hasta los formularios de su proyecto. También puede enlazar controles existentes a datos si arrastra los objetos desde la ventana Orígenes de datos a los controles existentes.  
  
### <a name="settings"></a>Configuración  
 Otro tipo de enlace de datos que puede administrar en formularios Windows Forms es la configuración. Mayoría de las aplicaciones smart client debe conservar cierta información sobre su estado de tiempo de ejecución, como el último tamaño conocido de los formularios y conservar los datos de preferencias del usuario, como las ubicaciones predeterminadas de los archivos guardados. La característica de configuración de la aplicación aborda estos requisitos proporcionando una manera sencilla de almacenar ambos tipos de configuración en el equipo cliente. Una vez definido mediante [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] o un editor de código, esta configuración se conserva con formato XML y se lee automáticamente en la memoria en tiempo de ejecución.  
  
 Para obtener información detallada sobre el uso de estas características, vea los siguientes temas de ayuda.  
  
|Para|Vea|  
|--------|---------|  
|Utilizar el <xref:System.Windows.Forms.BindingSource>componente</xref:System.Windows.Forms.BindingSource>|[Cómo: enlazar controles de Windows Forms con el componente BindingSource mediante el diseñador](https://msdn.microsoft.com/library/801dxw2t.aspx)|  
|Trabajar con [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] orígenes de datos|[Cómo: ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|Utilice la ventana de orígenes de datos|[Tutorial: Mostrar datos en Windows Forms](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Implementar aplicaciones en equipos cliente  
 Una vez escrita la aplicación, debe enviar a los usuarios para que puedan instalar y ejecutar en sus equipos cliente. Mediante la [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] tecnología, puede implementar aplicaciones desde [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] con unos cuantos clics y proporcionar a los usuarios con una dirección URL que apunte a la aplicación en la Web. [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]administra todos los elementos y dependencias de la aplicación y garantiza que la aplicación está instalada correctamente en el equipo cliente.  
  
 Las aplicaciones [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] se pueden configurar para ejecutarse únicamente cuando el usuario está conectado a la red, o para ejecutarse tanto en línea como sin conexión. Al especificar que una aplicación debe admitir el funcionamiento sin conexión, [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] agrega un vínculo a la aplicación en el usuario **iniciar** menú, para que el usuario puede abrir sin utilizar la dirección URL.  
  
 Cuando se actualiza la aplicación, se publica un nuevo manifiesto de implementación y una nueva copia de la aplicación en el servidor web. [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]detecta que hay una actualización disponible y actualiza la instalación del usuario; no se requiere ninguna programación personalizada para actualizar los ensamblados antiguos.  
  
 Para obtener una introducción completa a [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)], consulte [seguridad e implementación ClickOnce](https://docs.microsoft.com/visualstudio/deployment/clickonce-security-and-deployment). Para obtener información detallada sobre el uso de estas características, vea los temas de ayuda siguientes:  
  
|Para|Vea|  
|--------|---------|  
|Implementar una aplicación con[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Cómo: Publicar una aplicación ClickOnce mediante el Asistente para publicación](https://docs.microsoft.com/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Tutorial: Implementar manualmente una aplicación ClickOnce](https://docs.microsoft.com/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Actualización de un [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] implementación|[Cómo: Administrar actualizaciones de aplicaciones ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Administrar la seguridad con[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Cómo: Habilitar la configuración de seguridad de ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Otros controles y características  
 Hay muchas otras características en Windows Forms que simplifican y agilizan las tareas comunes de implementación, como la posibilidad de crear cuadros de diálogo, imprimir, agregar ayuda y documentación, y localizar la aplicación a varios idiomas. Además, Windows Forms se basa en el sólido sistema de seguridad de la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], que permite lanzar aplicaciones más seguras para sus clientes.  
  
 Para obtener información detallada sobre el uso de estas características, vea los temas de ayuda siguientes:  
  
|Para|Vea|  
|--------|---------|  
|Imprimir el contenido de un formulario|[Cómo: imprimir gráficos en formularios Windows Forms](https://msdn.microsoft.com/library/741a0ktc.aspx)<br /><br /> [Cómo: imprimir un archivo de texto de varias páginas en formularios Windows Forms](https://msdn.microsoft.com/library/cwbe712d.aspx)|   
|Más información sobre la seguridad de Windows Forms|[Seguridad en información general de Windows Forms](https://msdn.microsoft.com/library/90k49ccb.aspx)|  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Introducción a Windows Forms](https://msdn.microsoft.com/library/8bxxy49h.aspx)   
 [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)
