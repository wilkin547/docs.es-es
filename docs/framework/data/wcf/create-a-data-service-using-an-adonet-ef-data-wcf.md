---
title: "C&#243;mo: Crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Servicios de datos de Microsoft WCF, Entity Framework"
  - "Servicios de datos de Microsoft WCF, proveedores"
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# C&#243;mo: Crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] expone los datos de entidad como servicio de datos.  [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] proporciona estos datos de entidad cuando el origen de datos es una base de datos relacional.  En este tema se muestra cómo crear un modelo de datos basado en [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] en una aplicación web de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] que está basada en una base de datos existente y cómo usar este modelo de datos para crear un nuevo servicio de datos.  
  
 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] también proporciona una herramienta de línea de comandos que puede generar un modelo [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] fuera de un proyecto de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  Para obtener más información, consulta [Cómo: Usar EdmGen.exe para generar los archivos de asignación y de modelo](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
### Para agregar un modelo de Entity Framework que está basado en una base de datos existente a una aplicación web existente  
  
1.  En el menú **Proyecto**, haga clic en **Agregar nuevo elemento**.  
  
2.  En el panel **Plantillas**, haga clic en la categoría **Datos** y, a continuación, seleccione **Entity Data Model de ADO.NET**.  
  
3.  Escriba el nombre del modelo y, a continuación, haga clic en **Agregar**.  
  
     Se muestra la primera página del Asistente para [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
4.  En el cuadro de diálogo **Elegir contenido del modelo**, seleccione **Generar desde la base de datos**.  Después, haga clic en **Siguiente**.  
  
5.  Haga clic en el botón **Nueva conexión**.  
  
6.  En el cuadro de diálogo **Propiedades de la conexión**, escriba el nombre del servidor, seleccione el método de autenticación, escriba el nombre de la base de datos y, a continuación, haga clic en **Aceptar**.  
  
     El cuadro de diálogo **Elegir la conexión de datos** se actualiza con la configuración de la conexión de la base de datos.  
  
7.  Asegúrese de que está activada la casilla **Guardar configuración de conexión de la entidad en App.Config como**.  Después, haga clic en **Siguiente**.  
  
8.  En el cuadro de diálogo **Elija los objetos de base de datos**, seleccione todos los objetos de base de datos que piensa exponer en el servicio de datos.  
  
    > [!NOTE]
    >  El servicio de datos no expone automáticamente los objetos incluidos en el modelo de datos.  El propio servicio debe exponerlos explícitamente.  Para obtener más información, consulta [Configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
9. Haga clic en **Finalizar** para completar el asistente.  
  
     Con esto se crea un modelo de datos predeterminado basado en una base de datos específica.  [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] permite personalizar el modelo de datos.  Para obtener más información, consulta [Tasks](http://msdn.microsoft.com/es-es/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).  
  
### Para crear el servicio de datos usando el nuevo modelo de datos  
  
1.  En [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], abra el archivo .edmx que representa el modelo de datos.  
  
2.  En el **Explorador de modelos**, haga clic con el botón secundario en el modelo, haga clic en **Propiedades** y, a continuación, anote el nombre del contenedor de entidades.  
  
3.  En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y, a continuación, haga clic en **Agregar nuevo elemento**.  
  
4.  En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Servicio de datos de WCF**.  
  
5.  Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] crea los archivos de código y marcado XML para el nuevo servicio.  De forma predeterminada, se abre la ventana del editor de código.  
  
6.  En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que hereda de la clase <xref:System.Data.Objects.ObjectContext> y que es el contenedor de entidades del modelo de datos, que anotó en el paso 2.  
  
7.  En el código del servicio de datos, permita a los clientes autorizados tener acceso a los conjuntos de entidades que expone el servicio de datos.  Para obtener más información, consulta [Crear el servicio de datos](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
8.  Para probar el servicio de datos Northwind.svc usando un explorador web, siga las instrucciones del tema [Obtener acceso al servicio desde un explorador web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## Vea también  
 [Definir WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Cómo: Crear un servicio de datos mediante el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)   
 [Cómo: Crear un servicio de datos mediante un origen de datos LINQ to SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)