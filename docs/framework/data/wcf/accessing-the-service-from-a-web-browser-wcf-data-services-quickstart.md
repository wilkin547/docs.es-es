---
title: "Obtener acceso al servicio desde un explorador web (Tutorial r&#225;pido de WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Obtener acceso al servicio desde un explorador web (Tutorial r&#225;pido de WCF Data Services)
En esta tarea, iniciará [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] desde [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] y, opcionalmente, deshabilitará la lectura de fuentes en el explorador web.  A continuación, recuperará el documento de definición de servicio y tendrá acceso a los recursos del servicio de datos enviando solicitudes HTTP GET a través de un explorador web a los recursos expuestos.  
  
> [!NOTE]
>  De forma predeterminada, [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] asigna automáticamente un número de puerto al URI `localhost` en el equipo.  En esta tarea se usa el número de puerto `12345` en los ejemplos de URI.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo establecer un número de puerto concreto en su proyecto de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], vea [Crear el servicio de datos](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
### Para solicitar el documento de servicio predeterminado utilizando Internet Explorer  
  
1.  Seleccione **Opciones de Internet** en el menú **Herramientas** de Internet Explorer, haga clic en la pestaña **Contenido**, haga clic en la opción **Configuración** de la sección Fuentes y desactive **Activar la vista de lectura de fuentes**.  
  
     De este modo, se garantiza que la lectura de fuentes queda deshabilitada.  Si no deshabilita esta funcionalidad, el explorador web tratará el documento codificado como AtomPub devuelto como si fuera una fuente XML en lugar de mostrar los datos XML sin formato.  
  
    > [!NOTE]
    >  Si el explorador no puede mostrar la fuente como datos XML sin formato, todavía debería poder ver la fuente como el código fuente de la página.  
  
2.  En [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], presione la tecla F5 para iniciar la depuración de la aplicación.  
  
3.  Abra un explorador web en el equipo local.  En la barra de direcciones, escriba el siguiente URI:  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     De esta forma, se devuelve el documento de servicio predeterminado, que contiene una lista de los conjuntos de entidades expuestos por este servicio de datos.  
  
### Para tener acceso a los recursos del conjunto de entidades desde un explorador web  
  
1.  En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     Esto devuelve un conjunto de todos los clientes de la base de datos de ejemplo Northwind.  
  
2.  En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     De esta forma, se devuelve una instancia de la entidad para un cliente concreto, `ALFKI`.  
  
3.  En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     De esta forma, se recorre la relación entre clientes y pedidos para devolver un conjunto de todos los pedidos para ese cliente, `ALFKI`.  
  
4.  En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     De esta forma, se filtran los pedidos que pertenecen a un cliente determinado, `ALFKI`, de modo que solo se devuelve un pedido concreto dependiendo del valor proporcionado para `OrderID`.  
  
## Pasos siguientes  
 Ha obtenido acceso correctamente a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] desde un explorador web, con el explorador emitiendo solicitudes HTTP GET a los recursos especificados.  Un explorador web es un modo sencillo de experimentar con la sintaxis de direccionamiento de las solicitudes y de ver los resultados.  Sin embargo, este método no se suele emplear para obtener acceso a un servicio de datos de producción.  Normalmente, las aplicaciones interactúan con el servicio de datos a través de código de aplicación o lenguajes de scripting. Después, creará una aplicación cliente que use bibliotecas cliente para tener acceso a recursos del servicio de datos como si fueran objetos de Common Language Runtime \(CLR\):  
  
 [Crear la aplicación cliente de .NET Framework](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## Vea también  
 [Acceso a recursos del servicio de datos](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)