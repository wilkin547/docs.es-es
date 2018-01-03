---
title: "Acceder al servicio desde un explorador web (Inicio rápido de Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71beb254bf258da97207f14afca73cd68c6927ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a>Acceder al servicio desde un explorador web (Inicio rápido de Data Services de WCF)
En esta tarea, iniciará [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] desde [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] y, opcionalmente, deshabilitará la lectura de fuentes en el explorador web. A continuación, se recuperará el documento de definición de servicio así como acceso a los recursos del servicio de datos enviando solicitudes GET de HTTP a través de un explorador Web a los recursos expuestos.  
  
> [!NOTE]
>  De forma predeterminada, [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] asigna automáticamente un número de puerto al URI `localhost` en el equipo. En esta tarea se usa el número de puerto `12345` en los ejemplos de URI. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]cómo establecer un número de puerto específico en su [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] proyecto vea [crear el servicio de datos](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
### <a name="to-request-the-default-service-document-by-using-internet-explorer"></a>Para solicitar el documento de servicio predeterminado utilizando Internet Explorer  
  
1.  En Internet Explorer, desde el **herramientas** menú, seleccione **opciones de Internet**, haga clic en el **contenido** , haga clic en **configuración**y desactive  **Activar la visualización de fuentes**.  
  
     De este modo, se garantiza que la lectura de fuentes queda deshabilitada. Si no deshabilita esta funcionalidad, el explorador web tratará el documento codificado como AtomPub devuelto como si fuera una fuente XML en lugar de mostrar los datos XML sin formato.  
  
    > [!NOTE]
    >  Si el explorador no puede mostrar la fuente como datos XML sin formato, todavía debería poder ver la fuente como el código fuente de la página.  
  
2.  En [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], presione la tecla F5 para iniciar la depuración de la aplicación.  
  
3.  Abra un explorador web en el equipo local. En la barra de direcciones, escriba el siguiente URI:  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     De esta forma, se devuelve el documento de servicio predeterminado, que contiene una lista de los conjuntos de entidades expuestos por este servicio de datos.  
  
### <a name="to-access-entity-set-resources-from-a-web-browser"></a>Para tener acceso a los recursos del conjunto de entidades desde un explorador web  
  
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
  
## <a name="next-steps"></a>Pasos siguientes  
 Ha obtenido acceso correctamente a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] desde un explorador web, con el explorador emitiendo solicitudes HTTP GET a los recursos especificados. Un explorador web es un modo sencillo de experimentar con la sintaxis de direccionamiento de las solicitudes y de ver los resultados. Sin embargo, este método no se suele emplear para obtener acceso a un servicio de datos de producción. Habitualmente, las aplicaciones interactúan con el servicio de datos mediante el código de la aplicación o los lenguajes de script. A continuación, creará una aplicación cliente que usa las bibliotecas de cliente para tener acceso a los recursos del servicio de datos como si fueran objetos de Common Language Runtime (CLR):  
  
 [Creación de la aplicación cliente de .NET Framework](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a>Vea también  
 [Acceso a recursos de servicios de datos](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
