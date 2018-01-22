---
title: "Cómo: Crear un servicio de datos utilizando un origen de datos de ADO.NET Entity Framework (Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e90b11800685707460171e5e2d250ef757979c44
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Cómo: Crear un servicio de datos utilizando un origen de datos de ADO.NET Entity Framework (Data Services de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] expone los datos de entidad como servicio de datos. Estos datos de entidad proporciona la [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] cuando el origen de datos es una base de datos relacional. En este tema se muestra cómo crear un modelo de datos basado en [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] en una aplicación web de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] que está basada en una base de datos existente y cómo usar este modelo de datos para crear un nuevo servicio de datos.  
  
 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] también proporciona una herramienta de línea de comandos que puede generar un modelo [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] fuera de un proyecto de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Para obtener más información, consulte [Cómo: usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>Para agregar un modelo de Entity Framework que está basado en una base de datos existente a una aplicación web existente  
  
1.  En el **proyecto** menú, haga clic en **Agregar nuevo elemento**.  
  
2.  En el **plantillas** panel, haga clic en el **datos** categoría y, a continuación, seleccione **ADO.NET Entity Data Model**.  
  
3.  Escriba el nombre del modelo y, a continuación, haga clic en **agregar**.  
  
     Se muestra la primera página del Asistente para [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
4.  En el **Elegir contenido del modelo** cuadro de diálogo, seleccione **generar desde la base de datos**. Después, haga clic en **Siguiente**.  
  
5.  Haga clic en el **nueva conexión** botón.  
  
6.  En el **propiedades de conexión** cuadro de diálogo, escriba el nombre del servidor, seleccione el método de autenticación, escriba el nombre de la base de datos y, a continuación, haga clic en **Aceptar**.  
  
     El **elegir la conexión de datos**cuadro de diálogo se actualiza con la configuración de conexión de base de datos.  
  
7.  Asegúrese de que el **Guardar configuración de conexión de entidad en App.Config como:** casilla de verificación está activada. Después, haga clic en **Siguiente**.  
  
8.  En el **elija los objetos de base de datos** seleccionar todo de base de datos de cuadro de diálogo, objetos que piensa exponer en el servicio de datos.  
  
    > [!NOTE]
    >  El servicio de datos no expone automáticamente los objetos incluidos en el modelo de datos. El propio servicio debe exponerlos explícitamente. Para obtener más información, consulte [configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
9. Haga clic en **finalizar** para completar el asistente.  
  
     Con esto se crea un modelo de datos predeterminado basado en una base de datos específica. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] permite personalizar el modelo de datos. Para obtener más información, consulte [Tareas](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a>Para crear el servicio de datos usando el nuevo modelo de datos  
  
1.  En [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], abra el archivo .edmx que representa el modelo de datos.  
  
2.  En el **Explorador de modelos**, haga clic en el modelo, haga clic en **propiedades**y, a continuación, anote el nombre del contenedor de entidades.  
  
3.  En **el Explorador de soluciones**, haga clic en el nombre de su [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del proyecto y, a continuación, haga clic en **Agregar nuevo elemento**.  
  
4.  En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **servicio de datos de WCF**.  
  
5.  Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] crea los archivos de código y marcado XML para el nuevo servicio. De forma predeterminada, se abre la ventana del editor de código.  
  
6.  En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que hereda de la clase <xref:System.Data.Objects.ObjectContext> y que es el contenedor de entidades del modelo de datos, que anotó en el paso 2.  
  
7.  En el código del servicio de datos, permita a los clientes autorizados tener acceso a los conjuntos de entidades que expone el servicio de datos. Para obtener más información, consulte [crear el servicio de datos](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
8.  Para probar el servicio de datos Northwind.svc mediante un explorador Web, siga las instrucciones que aparecen en el tema [acceder al servicio desde un explorador Web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## <a name="see-also"></a>Vea también  
 [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Proveedores de Data Services](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Creación de un servicio de datos utilizando el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [Creación de un servicio de datos utilizando un origen de datos de LINQ to SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
