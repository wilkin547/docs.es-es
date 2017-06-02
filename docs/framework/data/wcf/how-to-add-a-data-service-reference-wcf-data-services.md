---
title: "C&#243;mo: Agregar una referencia a un servicio de datos (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, configurar"
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Agregar una referencia a un servicio de datos (WCF Data Services)
Puede usar el cuadro de diálogo **Agregar referencia de servicio** de Visual Studio para agregar una referencia a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  Esto le permite tener acceso más fácilmente a un servicio de datos en una aplicación cliente desarrollada en Visual Studio.  Cuando complete este procedimiento, se generarán clases de datos basadas en los metadatos que se obtienen del servicio de datos.  Para obtener más información, consulta [Generar la biblioteca de cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
### Para agregar una referencia a un servicio de datos  
  
1.  \(Opcional\) Si el servicio de datos no forma parte de la solución y no se está ejecutando, inícielo y anote el URI del mismo.  
  
2.  Haga clic con el botón secundario en el proyecto de cliente y, a continuación, seleccione **Agregar referencia de servicio**.  
  
3.  Si el servicio de datos forma parte de la solución actual, haga clic en **Detectar**.  
  
     o bien  
  
     En el cuadro de texto **Dirección**, escriba la dirección URL base del servicio de datos, como por ejemplo, `http://localhost:1234/Northwind.svc` y, a continuación, haga clic en **Ir**.  
  
4.  Haga clic en **Aceptar**.  
  
     De este modo se agrega un nuevo archivo de código que contiene las clases de datos que se usan para obtener acceso e interactuar con los recursos del servicio de datos como objetos.  
  
## Vea también  
 [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)