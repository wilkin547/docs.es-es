---
title: "Conceptos b&#225;sicos de las aplicaciones de Windows Forms (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "aplicaciones Windows"
  - "Windows Forms, Visual Basic"
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Conceptos b&#225;sicos de las aplicaciones de Windows Forms (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una parte importante de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] es la capacidad de crear aplicaciones de Windows Forms que se ejecutan localmente en los equipos de los usuarios.  Puede utilizar Visual Studio para crear la aplicación y la interfaz de usuario utilizando formularios Windows Forms.  Una aplicación de Windows Forms se compila a partir de las clases del espacio de nombres <xref:System.Windows.Forms>.  
  
## Diseñar aplicaciones de Windows Forms  
 Puede crear aplicaciones de Windows Forms y aplicaciones de servicios de Windows mediante [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  Para obtener más información, vea los temas siguientes:  
  
-   [Getting Started with Windows Forms](../Topic/Getting%20Started%20with%20Windows%20Forms.md).  Proporciona información sobre cómo crear y programar Windows Forms.  
  
-   [Windows Forms Walkthroughs](http://msdn.microsoft.com/es-es/fd44d13d-4733-416f-aefc-32592e59e5d9).  Incluye temas que explican el desarrollo paso a paso de las aplicaciones Windows Forms que se crean habitualmente basadas en Windows Forms.  
  
-   [Controles de Windows Forms](../Topic/Windows%20Forms%20Controls.md).  Colección de temas que detallan el uso de controles de Windows Forms.  
  
-   [Windows Service Applications](../Topic/Developing%20Windows%20Service%20Applications.md).  Muestra temas que explican cómo crear servicios de Windows.  
  
## Compilar interfaces de usuario interactivas con formato enriquecido  
 Los formularios Windows Forms son el componente cliente inteligente de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], un conjunto de bibliotecas administradas que habilitan las tareas comunes de aplicación, como la lectura y la escritura en el sistema de archivos.  Utilizando un entorno de desarrollo como [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], puede crear aplicaciones de Windows Forms que muestran información, solicitan a los usuarios la entrada de datos y se comunican con equipos remotos a través de una red.  
  
 En formularios Windows Forms, un formulario es una superficie visual en la que se muestra información al usuario.  Normalmente las aplicaciones de Windows Forms se compilan colocando controles en los formularios y programando respuestas a las acciones del usuario, como clics del mouse o presiones de teclas.  Un *control* es un elemento discreto de la interfaz de usuario que muestra datos o acepta la entrada de datos.  
  
### Eventos  
 Cuando un usuario hace algo en su formulario o en alguno de sus controles, se genera un evento.  Su aplicación reacciona a estos eventos utilizando el código y procesa los eventos cuando aparecen.  Para obtener más información, vea [Creating Event Handlers in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md).  
  
### Controles  
 Los formularios Windows Forms contienen diversos controles que puede colocar en los formularios: controles que muestran cuadros de texto, botones, cuadros desplegables, botones de radio e incluso páginas Web.  Para obtener una lista de todos los controles que se pueden usar en los formularios, vea [Controles que se utilizan en formularios Windows Forms](../Topic/Controls%20to%20Use%20on%20Windows%20Forms.md).  Si un control existente no satisface sus necesidades, los formularios Windows Forms también admiten la creación de sus propios controles personalizados mediante la clase <xref:System.Windows.Forms.UserControl>.  
  
 Los formularios Windows Forms tienen controles enriquecidos de interfaz de usuario que emulan las características de aplicaciones de tecnología avanzada como Microsoft Office.  Mediante los controles <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.MenuStrip> se pueden crear barras de herramientas y menús que contienen texto e imágenes, muestran submenús y hospedan otros controles como cuadros de texto y cuadros combinados.  
  
 Con el diseñador de formularios de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] de tipo arrastrar y colocar, puede crear fácilmente aplicaciones de Windows Forms: no tiene más que seleccionar los controles con el cursor y colocarlos en el lugar deseado del formulario.  El diseñador proporciona herramientas como líneas de cuadrícula y "líneas de ajuste" para minimizar la molestia de alinear los controles.  Y, aunque utilice [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] o compile desde la línea de comandos, puede utilizar los controles <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> y <xref:System.Windows.Forms.SplitContainer> para crear diseños de formulario avanzados con el mínimo de tiempo y de esfuerzo.  
  
### Elementos personalizados de interfaz de usuario  
 Por último, si debe crear sus propios elementos personalizados de interfaz de usuario, el espacio de nombres <xref:System.Drawing> contiene todas las clases necesarias para representar líneas, círculos y otras formas directamente en un formulario.  
  
 Para obtener información paso a paso sobre el uso de estas características, vea los siguientes temas de Ayuda.  
  
|Para|Vea|  
|----------|---------|  
|Crear una nueva aplicación de Windows Forms con [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]|[Walkthrough: Creating a Simple Windows Form](http://msdn.microsoft.com/es-es/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Utilizar controles en formularios|[Cómo: Agregar controles a formularios Windows Forms](../Topic/How%20to:%20Add%20Controls%20to%20Windows%20Forms.md)|  
|Controlar eventos de un formulario y sus controles|[How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/es-es/8461e9b8-14e8-406f-936e-3726732b23d2)|  
|Utilizar el control <xref:System.Windows.Forms.ToolStrip>|[Cómo: Crear un control ToolStrip básico con elementos estándar mediante el Diseñador](../Topic/How%20to:%20Create%20a%20Basic%20Windows%20Forms%20ToolStrip%20with%20Standard%20Items%20Using%20the%20Designer.md)|  
|Crear gráficos con <xref:System.Drawing>|[Introducción a la programación de gráficos](../Topic/Getting%20Started%20with%20Graphics%20Programming.md)|  
|Crear controles personalizados|[Cómo: Heredar de una clase UserControl](../Topic/How%20to:%20Inherit%20from%20the%20UserControl%20Class.md)|  
  
## Mostrar y manipular datos  
 Muchas aplicaciones deben mostrar los datos de una base de datos, archivo XML, servicio Web XML u otro origen de datos.  Los formularios Windows Forms proporcionan un control flexible denominado <xref:System.Windows.Forms.DataGridView> para representar esos datos tabulados en un formato tradicional de filas y columnas, de manera que cada fragmento de datos ocupe su propia celda.  Utilizando <xref:System.Windows.Forms.DataGridView>, puede personalizar el aspecto de celdas concretas, bloquear filas y columnas arbitrarias en el lugar que ocupan y mostrar controles complejos dentro de las celdas, entre otras características.  
  
 Conectar a orígenes de datos a través una red resulta sencillo con los clientes inteligentes de formularios Windows Forms.  El componente <xref:System.Windows.Forms.BindingSource>, nuevo en los formularios Windows Forms en [!INCLUDE[vsprvslong](../../../csharp/misc/includes/vsprvslong_md.md)] y [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)], representa una conexión a los orígenes de datos, y expone los métodos para enlazar datos a los controles, navegar por los registros anterior y siguiente, modificar registros y devolver los cambios a su origen.  El control <xref:System.Windows.Forms.BindingNavigator> proporciona una interfaz simple sobre el componente <xref:System.Windows.Forms.BindingSource> para que los usuarios puedan navegar entre los registros.  
  
### Controles enlazados a datos  
 Puede crear controles enlazados a datos con facilidad utilizando la ventana Orígenes de datos, que muestra orígenes de datos como bases de datos, servicios Web y objetos de su proyecto.  Puede crear controles enlazados a datos arrastrando elementos desde esta ventana hasta los formularios de su proyecto.  También puede enlazar a datos los controles existentes arrastrando los objetos desde la ventana Orígenes de datos hasta los controles existentes.  
  
### Valores  
 Otro tipo de enlace a datos que puede administrar en formularios Windows Forms es la configuración.  La mayoría de aplicaciones de cliente inteligente deben conservar cierta información sobre su estado de ejecución, como el último tamaño conocido de los formularios, y retener información sobre las preferencias de los usuarios, como las ubicaciones predeterminadas para los archivos guardados.  Las característica de configuración de la aplicación da respuesta a estas necesidades proporcionando una manera fácil de almacenar ambos tipos de configuración en el equipo cliente.  Una vez definida utilizando [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] o un editor de código, esta configuración se conserva con formato XML y se vuelve a leer para colocarla automáticamente en la memoria en tiempo de ejecución.  
  
 Para obtener información paso a paso sobre el uso de estas características, vea los siguientes temas de Ayuda.  
  
|Para|Vea|  
|----------|---------|  
|Utilizar el componente <xref:System.Windows.Forms.BindingSource>|[Cómo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Diseñador](../Topic/How%20to:%20Bind%20Windows%20Forms%20Controls%20with%20the%20BindingSource%20Component%20Using%20the%20Designer.md)|  
|Trabajar con orígenes de datos de [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)]|[Cómo: Ordenar y filtrar datos ADO.NET con el componente BindingSource de formularios Windows Forms](../Topic/How%20to:%20Sort%20and%20Filter%20ADO.NET%20Data%20with%20the%20Windows%20Forms%20BindingSource%20Component.md)|  
|Utilizar la ventana Orígenes de datos|[Tutorial: Mostrar datos en Windows Forms](../Topic/Walkthrough:%20Displaying%20Data%20on%20a%20Windows%20Form.md)|  
|Utilizar la configuración de la aplicación|[How to: Create Application Settings Using the Designer](http://msdn.microsoft.com/es-es/53b3af80-1c02-4e35-99c6-787663148945)|  
  
## Implementar aplicaciones en los equipos cliente  
 Una vez escrita su aplicación, debe enviarla a sus usuarios para que puedan instalarla y ejecutarla en sus equipos clientes.  Con ayuda de la tecnología [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)], puede implementar sus aplicaciones desde [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] con unos cuantos clics y proporcionar a los usuarios una dirección URL que señale a la aplicación en la Web.  [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] administra todos los elementos y dependencias de la aplicación, y garantiza que la aplicación se instale correctamente en el equipo cliente.  
  
 Las aplicaciones [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] se pueden configurar para ejecutarse únicamente cuando el usuario se conecta a la red o ejecutarse con o sin conexión.  Cuando especifique que una aplicación debe admitir el funcionamiento sin conexión, [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] agrega un vínculo a su aplicación en el menú **Inicio** del usuario, de manera que el usuario pueda abrirla sin utilizar la dirección URL.  
  
 Al actualizar una aplicación, se publica un nuevo manifiesto de implementación y una nueva copia de la aplicación en el servidor web.  [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] detecta que hay una actualización disponible y actualiza la instalación del usuario; no se requiere programación personalizada para actualizar los ensamblados anteriores.  
  
 Para obtener una introducción completa a [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)], vea [Seguridad e implementación ClickOnce](/visual-studio/deployment/clickonce-security-and-deployment).  Para obtener información paso a paso sobre el uso de estas características, vea los siguientes temas de Ayuda:  
  
|Para|Vea|  
|----------|---------|  
|Implementar una aplicación con [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Cómo: Publicar una aplicación ClickOnce sin usar el Asistente para publicación](../Topic/How%20to:%20Publish%20a%20ClickOnce%20Application%20using%20the%20Publish%20Wizard.md)<br /><br /> [Tutorial: Implementar manualmente una aplicación ClickOnce](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md)|  
|Actualizar una implementación de [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Cómo: Administrar actualizaciones de aplicaciones ClickOnce](../Topic/How%20to:%20Manage%20Updates%20for%20a%20ClickOnce%20Application.md)|  
|Administrar la seguridad con [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]|[Cómo: Habilitar la configuración de seguridad para aplicaciones ClickOnce](../Topic/How%20to:%20Enable%20ClickOnce%20Security%20Settings.md)|  
  
## Otros controles y características  
 Los formularios Windows Forms tienen muchas otras características que hacen que las tareas frecuentes de implementación sean rápidas y fáciles, como la posibilidad de crear cuadros de diálogo, imprimir, agregarles Ayuda y documentación, y adaptar y traducir su aplicación a varios idiomas.  Además, los formularios Windows Forms confían en el robusto sistema de seguridad de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], permitiéndole publicar aplicaciones más seguras para sus clientes.  
  
 Para obtener información paso a paso sobre el uso de estas características, vea los siguientes temas de Ayuda:  
  
|Para|Vea|  
|----------|---------|  
|Imprimir el contenido de un formulario|[How to: Print Graphics in Windows Forms](../Topic/How%20to:%20Print%20Graphics%20in%20Windows%20Forms.md)<br /><br /> [How to: Print a Multi\-Page Text File in Windows Forms](../Topic/How%20to:%20Print%20a%20Multi-Page%20Text%20File%20in%20Windows%20Forms.md)|  
|Globalizar una aplicación de Windows Forms|[Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/es-es/9a96220d-a19b-4de0-9f48-01e5d82679e5)|  
|Obtener más información sobre la seguridad de los formularios Windows Forms|[Security in Windows Forms Overview](../Topic/Security%20in%20Windows%20Forms%20Overview.md)|  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Información general sobre formularios Windows Forms](../Topic/Windows%20Forms%20Overview.md)   
 [My.Forms \(Objeto\)](../../../visual-basic/language-reference/objects/my-forms-object.md)