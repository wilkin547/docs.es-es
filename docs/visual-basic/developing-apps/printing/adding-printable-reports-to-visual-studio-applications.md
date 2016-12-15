---
title: "Agregar informes imprimibles a las aplicaciones de Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "imprimir [Visual Studio], informes"
  - "informes, imprimir en Visual Studio"
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Agregar informes imprimibles a las aplicaciones de Visual Studio
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Visual Studio admite varias soluciones de creación de informes para ayudar al usuario a agregar informes de datos enriquecidos a las aplicaciones de Visual Basic.  Se pueden crear y agregar informes mediante los controles ReportViewer, Crystal Reports o SQL Server Reporting Services.  
  
> [!NOTE]
>  SQL Server Reporting Services forma parte de SQL Server 2005 en lugar de Visual Studio.  Reporting Services no se instala en su sistema a menos que haya instalado SQL Server 2005.  
  
## Información general sobre la tecnología de elaboración de informes de Microsoft en las aplicaciones de Visual Basic  
 Elija uno de los enfoques siguientes para utilizar una tecnología de elaboración de informes de Microsoft en su aplicación:  
  
-   Agregar una o varias instancias de un control ReportViewer a una aplicación de Visual Basic para Windows.  
  
-   Integrar SQL Server Reporting Services manualmente mediante llamadas al servicio Web del servidor de informes.  
  
-   Usar el control ReportViewer y Microsoft SQL Server 2005 Reporting Services conjuntamente, utilizando el control como un visor de informes y un servidor de informes como procesador de informes.  \(Observe que debe usar Reporting Services de SQL Server 2005 si desea utilizar un servidor de informes y el control ReportViewer conjuntamente\).  
  
## Utilizar los controles ReportViewer  
 La manera más fácil de incrustar la funcionalidad de elaboración de informes en una aplicación de Visual Basic para Windows es agregar el control ReportViewer a un formulario en la aplicación.  El control agrega las funciones de procesamiento de informes directamente a la aplicación y proporciona un diseñador de informes integrado de modo que se pueden generar informes con los datos de cualquier objeto de datos de ADO.NET.  Una API completa proporciona acceso mediante programación al control y a los informes de modo que se puede configurar la funcionalidad en tiempo de ejecución.  
  
 ReportViewer proporciona funcionalidad integrada de procesamiento y visualización de informes en un solo control de datos de distribución gratuita.  Elija los controles ReportViewer si requiere la siguiente funcionalidad:  
  
-   Procesamiento de informes en la aplicación cliente.  Un informe procesado aparece en un área de visualización proporcionada por el control.  
  
-   Enlace de datos a tablas de datos de ADO.NET.  Se pueden crear informes que utilicen instancias de <xref:System.Data.DataTable> proporcionadas al control.  También se pueden enlazar datos directamente a los objetos comerciales.  
  
-   Controles redistribuibles que se pueden incluir en la aplicación.  
  
-   Funcionalidad en tiempo de ejecución como la navegación por páginas, impresión, búsquedas y formatos de exportación.  Una barra de herramientas ReportViewer permite llevar a cabo estas operaciones.  
  
 Para utilizar el control ReportViewer, puede arrastrarlo desde la sección **Datos** del Cuadro de herramientas de Visual Studio hasta un formulario en la aplicación de Visual Basic para Windows.  
  
### Crear informes en Visual Studio para controles ReportViewer  
 Para crear un informe que se ejecute en ReportViewer, agregue una plantilla **Informe** al proyecto.  Visual Studio crea un archivo de definición de informe de cliente \(.rdlc\), agrega el archivo al proyecto y abre un diseñador de informes integrado en el área de trabajo de Visual Studio.  
  
 El Diseñador de informes de Visual Studio se integra con la ventana **Orígenes de datos**.  Cuando se arrastra un campo desde la ventana **Orígenes de datos** al informe, el Diseñador de informes copia metadatos sobre el origen de datos en el archivo de definición del informe.  El control ReportViewer utiliza estos metadatos para generar automáticamente el código de enlace de datos.  
  
 El Diseñador de informes de Visual Studio no incluye la funcionalidad de vista previa de los informes.  Para ofrecer una vista previa del informe, ejecute la aplicación y genere una vista previa del informe incrustado en ella.  
  
||  
|-|  
|Para agregar la funcionalidad básica de elaboración de informes a la aplicación|  
|1.  Arrastre un control ReportViewer desde la ficha **Datos** del **Cuadro de herramientas** hasta el formulario.<br />2.  En el menú **Proyecto**, elija **Agregar nuevo elemento**.  En el cuadro de diálogo **Agregar nuevo elemento**, seleccione el icono **Informe** y, a continuación, haga clic en **Agregar**.<br />     El Diseñador de informes se abre en el entorno de desarrollo y se agrega un archivo de informe \(.rdlc\) al proyecto.<br />3.  Arrastre los elementos de informe desde el **Cuadro de herramientas** hasta el diseño de informe y organícelos según su criterio.<br />4.  Arrastre los campos desde la ventana **Orígenes de datos** hasta los elementos de informe en el diseño de informe.|  
  
## Utilizar Reporting Services en las aplicaciones de Visual Basic  
 Reporting Services es una tecnología de elaboración de informes basada en servidor que viene incluida con SQL Server.  Reporting Services incluye características adicionales que no ofrecen los controles ReportViewer.  Elija Reporting Services si requiere alguna de las características siguientes:  
  
-   Implementación de ampliación en horizontal y procesamiento de informes en el servidor que mejoran el rendimiento de los informes complejos o de ejecución prolongada y de una actividad de elaboración de informes de gran volumen.  
  
-   Procesamiento de informes y datos integrados, con compatibilidad para controles de informe personalizados y formatos enriquecidos para la representación de los resultados.  
  
-   Procesamiento programado de los informes, de modo que se puede especificar exactamente cuándo se ejecutan los informes.  
  
-   Distribución de informes basada en suscriptores a través del correo electrónico o a ubicaciones de recursos compartidos de archivos.  
  
-   Creación de informes ad hoc para que los usuarios empresariales puedan crear informes de acuerdo con sus necesidades.  
  
-   Suscripciones controladas por datos que dirigen los resultados de informes personalizados a una lista dinámica de destinatarios.  
  
-   Extensiones personalizadas para el procesamiento de datos, la entrega de informes, la autenticación personalizada y la representación de informes.  
  
 El servidor de informes se implementa como un servicio Web.  El código de la aplicación debe incluir llamadas al servicio Web para obtener acceso a los informes y otros metadatos.  El servicio Web proporciona total acceso mediante programación a una instancia del servidor de informes.  
  
 Dado que Reporting Services es una tecnología de elaboración de informes basada en Web, el visor predeterminado representa los informes en formato HTML.  Si no desea utilizar HTML como formato de presentación predeterminado, deberá escribir un visor personalizado para la aplicación.  
  
### Crear informes en Visual Studio para Reporting Services  
 Para crear informes que se van a ejecutar en un servidor de informes, se crean archivos de definición de informe \(.rdl\) en Visual Studio a través de Business Intelligence Development Studio, incluido con SQL Server 2005.  
  
> [!NOTE]
>  Debe tener instalado SQL Server 2005 para poder utilizar SQL Server Reporting Services y Business Intelligence Development Studio.  
  
 Business Intelligence Development Studio agrega plantillas de proyecto específicas para los componentes de SQL Server.  Para crear informes, puede elegir entre las plantillas **Proyecto de servidor de informes** o **Asistente para proyectos de servidor de informes**.  Puede especificar conexiones a orígenes de datos y consultas en varios tipos de orígenes de datos, incluidos SQL Server, Oracle, Analysis Services, XML y SQL Server Integration Services.  Las fichas **Datos**, **Diseño** y **Vista previa** permiten definir los datos, crear un diseño de informe y obtener la vista previa del informe en el mismo área de trabajo.  
  
 Las definiciones de informe creadas para el control o el servidor de informes pueden volver a utilizarse en ambas tecnologías.  
  
||  
|-|  
|Para crear un informe que se ejecute en un servidor de informes|  
|1.  En el menú **Archivo**, elija **Nuevo**.<br />     Aparece el cuadro de diálogo **Nuevo proyecto**.<br />2.  En el panel **Tipos de proyecto**, haga clic en **Proyectos de Business Intelligence**.<br />3.  En el panel Plantillas, seleccione **Proyecto de servidor de informes** o **Asistente para proyectos de servidor de informes**.|  
  
## Utilizar los controles ReportViewer y SQL Server Reporting Services conjuntamente  
 Los controles ReportViewer y SQL Server 2005 Reporting Services pueden utilizarse conjuntamente en la misma aplicación.  
  
-   El control ReportViewer proporciona un visor que se utiliza para mostrar los informes en la aplicación.  
  
-   Reporting Services proporciona los informes y realiza todo el procesamiento en un servidor remoto.  
  
 El control ReportViewer puede configurarse de modo que se muestren los informes almacenados y procesados en un servidor de informes remoto de Reporting Services.  Este tipo de configuración se denomina *modo de procesamiento remoto*.  En este modo, el control solicita un informe que está almacenado en un servidor de informes remoto.  El servidor de informes procesa los informes, procesa los datos y representa los informes.  Se devuelve un informe terminado y representado al control y se muestra dicho informe en el área de visualización.  
  
 Los informes que se ejecutan en un servidor de informes admiten otros formatos de exportación, tienen otra implementación de la parametrización de los informes, utilizan los tipos de orígenes de datos que el servidor de informes admite y su acceso se realiza a través del modelo de autorización basada en roles en el servidor de informes.  
  
 Para utilizar el modo de procesamiento remoto, especifique la dirección URL y la ruta de acceso a un informe del servidor cuando configure el control ReportViewer.