---
title: Agregar informes imprimibles a las aplicaciones de Visual Studio
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ce2a8b12d8202a9f201a82b0d4a571249210d48
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a>Agregar informes imprimibles a las aplicaciones de Visual Studio
Visual Studio admite una variedad de soluciones de informes que le ayudarán a agregar informes a sus aplicaciones de Visual Basic de datos enriquecidos. Puede crear y agregar informes con controles ReportViewer, Crystal Reports o SQL Server Reporting Services.  
  
> [!NOTE]
>  SQL Server Reporting Services es parte de SQL Server 2005 en lugar de Visual Studio. Reporting Services no está instalados en el sistema a menos que se ha instalado SQL Server 2005.  
  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a>Información general de Microsoft Reporting tecnología en aplicaciones de Visual Basic  
 Elija uno de los métodos siguientes para utilizar una tecnología de la aplicación de informes de Microsoft:  
  
-   Agregar una o más instancias de un control ReportViewer a una aplicación de Windows de Visual Basic.  
  
-   Integrar SQL Server Reporting Services mediante programación mediante la realización de llamadas al servicio Web del servidor de informes.  
  
-   Use el control ReportViewer y Microsoft SQL Server 2005 Reporting Services juntos, utilizando el control como un visor de informes y un servidor de informes como un procesador de informes. (Tenga en cuenta que debe usar la versión de SQL Server 2005 de Reporting Services si desea usar un servidor de informes y el control ReportViewer conjuntamente).  
  
## <a name="using-reportviewer-controls"></a>Utilizar controles ReportViewer  
 La manera más fácil de incrustar la funcionalidad de informes en una aplicación de Windows de Visual Basic es agregar el control ReportViewer a un formulario en la aplicación. El control agrega capacidades directamente a la aplicación de procesamiento de informes y proporciona un diseñador de informes integrado para que pueda generar informes con datos de cualquier objeto de datos ADO.NET. Una API completa proporciona acceso mediante programación al control y los informes de modo que puede configurar la funcionalidad de tiempo de ejecución.  
  
 ReportViewer proporciona la capacidad de visualización en un control de datos único, puede distribuir libremente y procesamiento de informes integrados. Elija que los controles ReportViewer si necesita la funcionalidad de informe siguientes:  
  
-   Procesamiento de informes en la aplicación cliente. Un informe procesado aparece en un área de visualización proporcionado por el control.  
  
-   Enlace de datos a tablas de datos ADO.NET. Puede crear informes que utilicen <xref:System.Data.DataTable> instancias proporcionadas al control. También puede enlazar directamente a objetos de negocio.  
  
-   Controles redistribuibles que se pueden incluir en la aplicación.  
  
-   Funcionalidad en tiempo de ejecución, como la navegación en páginas, impresión, búsqueda y formatos de exportación. Una barra de herramientas de ReportViewer proporciona compatibilidad para estas operaciones.  
  
 Para utilizar el control ReportViewer, puede arrastrar desde el **datos** sección del cuadro de herramientas Visual Studio en un formulario en la aplicación de Windows de Visual Basic.  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a>Creación de informes en Visual Studio para los controles ReportViewer  
 Para generar un informe que se ejecute en ReportViewer, agregue un **informe** plantilla al proyecto. Visual Studio crea un archivo de definición de informe de cliente (.rdlc), agrega el archivo al proyecto y abre un diseñador de informes integrado en el área de trabajo de Visual Studio.  
  
 El Diseñador de informes de Visual Studio se integra con la **orígenes de datos** ventana. Cuando se arrastra un campo desde el **orígenes de datos** ventana para el informe, el Diseñador de informes copia metadatos sobre el origen de datos en el archivo de definición de informe. Estos metadatos se utilizan el control ReportViewer para generar automáticamente código de enlace de datos.  
  
 El Diseñador de informes de Visual Studio no incluye funcionalidad de vista previa del informe. Para obtener una vista previa del informe, ejecute la aplicación y obtener una vista previa del informe incrustado en ella.  
  
|Para agregar la funcionalidad básica de informes a la aplicación|  
|---|    
|1.  Arrastre un control ReportViewer desde la **datos** pestaña de la **cuadro de herramientas** al formulario.<br />2.  En el menú **Proyecto** , elija **Agregar nuevo elemento**. En el **Agregar nuevo elemento** cuadro de diálogo, seleccione la **informe** icono y haga clic en **agregar**.<br />     El Diseñador de informes se abre en el entorno de desarrollo y un archivo de informe (.rdlc) se agrega al proyecto.<br />3.  Arrastre los elementos de informe desde el **cuadro de herramientas** en el diseño del informe y organizarlos como desee.<br />4.  Arrastre los campos desde el **orígenes de datos** ventana a los elementos de informe en el diseño del informe.|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a>Utilizar Reporting Services en aplicaciones de Visual Basic  
 Reporting Services es una tecnología informes basada en servidor que se incluye con SQL Server. Reporting Services incluye características adicionales que no se encuentran en los controles ReportViewer. Elija Reporting Services si requiere alguna de las siguientes características:  
  
-   Implementación de ampliación horizontal y procesamiento de informes de servidor que proporciona un rendimiento mejorado para informes complejos o de ejecución prolongada y para la actividad de informes de gran volumen.  
  
-   Formatos de salida de datos integrados y procesamiento del informe, con compatibilidad para controles de informe personalizados y enriquecidos para la representación.  
  
-   Programar el procesamiento de informes para que pueda especificar exactamente cuándo se ejecutan los informes.  
  
-   Distribución de informes basada en el suscriptor a través de correo electrónico o a ubicaciones de recursos compartidos de archivo.  
  
-   Informes ad hoc para que los usuarios empresariales puedan crear informes según sea necesario.  
  
-   Suscripciones controladas por datos que se enrutan la salida de informes personalizados a una lista dinámica de destinatarios.  
  
-   Extensiones personalizadas para el procesamiento de datos, la entrega de informes, autenticación personalizada y representación de informes.  
  
 El servidor de informes se implementa como servicio Web. El código de aplicación debe incluir llamadas al servicio Web para tener acceso a informes y otros metadatos. El servicio Web proporciona acceso mediante programación completa a una instancia de servidor de informes.  
  
 Dado que Reporting Services es una tecnología informes basada en Web, el visor predeterminado muestra los informes que se representan en formato HTML. Si no desea utilizar HTML como formato de presentación de informes predeterminado, tendrá que escribir un visor de informes personalizado para su aplicación.  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a>Creación de informes en Visual Studio para Reporting Services  
 Para crear informes que se ejecutan en un servidor de informes, crea definición de informe (.rdl) archivos en Visual Studio mediante Business Intelligence Development Studio, que se incluye con SQL Server 2005.  
  
> [!NOTE]
>  Debe tener SQL Server 2005 instalado para poder utilizar SQL Server Reporting Services y Business Intelligence Development Studio.  
  
 Business Intelligence Development Studio agrega plantillas de proyecto que son específicas de los componentes de SQL Server. Para crear informes, puede elegir entre la **Report Server Project** o **Asistente de proyectos de servidor de informes** plantillas. Puede especificar las conexiones de origen de datos y las consultas a una variedad de tipos de origen de datos, incluidos SQL Server, Oracle, Analysis Services, XML y SQL Server Integration Services. A **datos** ficha, **diseño** ficha, y **vista previa** ficha le permiten definir los datos, crear un diseño de informe y obtener una vista previa del informe en la misma área de trabajo.  
  
 Las definiciones de informe que se generación para el control o el servidor de informes se pueden reutilizar en ambas tecnologías.  
  
|Para crear un informe que se ejecuta en un servidor de informes|  
|---|    
|1.  En el **archivo** menú, elija **nuevo**.<br />     Aparece el cuadro de diálogo **Nuevo proyecto** .<br />2.  En el **tipos de proyecto** panel, haga clic en **proyectos de Business Intelligence**.<br />3.  En el panel Plantillas, seleccione **Report Server Project** o **Asistente de proyectos de servidor de informes**.|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a>Mediante los controles ReportViewer y SQL Server Reporting Services conjuntamente  
 Los controles ReportViewer y SQL Server 2005 Reporting Services se pueden utilizar juntos en la misma aplicación.  
  
-   El control ReportViewer proporciona un visor que se utiliza para mostrar informes en la aplicación.  
  
-   Reporting Services proporciona los informes y realiza todo el procesamiento en un servidor remoto.  
  
 El control ReportViewer puede configurarse para mostrar los informes que se almacenan y se procesan en un servidor de informes de Reporting Services remoto. Este tipo de configuración se denomina *modo de procesamiento remoto*. En el modo de procesamiento remoto, el control solicita un informe que se almacena en un servidor de informes remoto. El servidor de informes realiza todos los el procesamiento de informes, el procesamiento de datos y representación de informes. Un informe terminado y representado es devuelto por el control y se muestra en el área de vista.  
  
 Informes que se ejecutan en un soporte de servidor de informes adicional formatos de exportación, tiene una implementación de la parametrización de informes diferente, use los tipos de origen de datos que son compatibles con el servidor de informes y se accede a través del modelo de autorización basada en roles en el servidor de informes.  
  
 Para usar el modo de procesamiento remoto, especifique la dirección URL y la ruta de acceso a un servidor de informes al configurar el control ReportViewer.
