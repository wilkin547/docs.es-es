---
title: "Proveedor de Entity Framework (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, proveedores"
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Proveedor de Entity Framework (WCF Data Services)
Al igual que ocurre con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], ADO.NET Entity Framework está basado en Entity Data Model, que es un tipo de modelo entidad\-relación.  Entity Framework traduce las operaciones efectuadas sobre su implementación de Entity Data Model, que se denomina el *modelo conceptual*, en operaciones equivalentes sobre un origen de datos.  De esta forma, Entity Framework se convierte en un proveedor ideal para los servicios de datos basados en datos relacionales y se puede usar cualquier base de datos con un proveedor de datos que admita Entity Framework con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  Para obtener una lista de los orígenes de datos que son compatibles actualmente con Entity Framework, vea [Proveedores de terceros para Entity Framework](http://go.microsoft.com/fwlink/?LinkId=143699).  
  
 En un modelo conceptual, el contenedor de entidades es la raíz del servicio.  Debe definir un modelo conceptual en Entity Framework antes de que un servicio de datos pueda exponer los datos.  Para obtener más información, consulta [Cómo: Crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] admite el modelo de simultaneidad optimista al permitirle definir un token de simultaneidad para una entidad.  El servicio de datos utiliza este token de simultaneidad, que incluye una o más propiedades de la entidad, para determinar si se ha producido un cambio en los datos que se solicitan, que se están actualizando o eliminando.  Cuando los valores de token obtenidos de la eTag de la solicitud difieren de los valores actuales de la entidad, el servicio de datos inicia una excepción.  Para indicar que una propiedad forma parte del token de simultaneidad, debe aplicar el atributo `ConcurrencyMode="Fixed"` en el modelo de datos definido por el proveedor de [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)].  El token de simultaneidad no puede incluir ninguna propiedad clave ni de navegación. Para obtener más información, vea [Actualizar el servicio de datos](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Para obtener más información sobre Entity Framework, vea [Información general de Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
## Vea también  
 [Proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Proveedor de reflexión](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)   
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)