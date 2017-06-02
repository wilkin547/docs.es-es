---
title: "C&#243;mo: Personalizar fuentes con el proveedor de Entity Framework (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, personalizar"
  - "Servicios de datos de Microsoft WCF, personalizar fuentes"
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Personalizar fuentes con el proveedor de Entity Framework (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite personalizar la serialización Atom en una respuesta del servicio de datos para que las propiedades de una entidad se puedan asignar a los elementos no usados que se definen en el protocolo AtomPub.  En este tema se explica cómo definir los atributos de asignación para los tipos de entidad en un modelo de datos definido en un archivo .edmx utilizando el proveedor de Entity Framework.  Para obtener más información, consulta [Personalización de fuentes](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 En este tema modificará manualmente el archivo .edmx generado por la herramienta que contiene el modelo de datos.  Dado que Entity Designer no admite las extensiones al modelo de datos, debe modificar manualmente el archivo.  Para obtener más información sobre el archivo .edmx generado por las herramientas de Entity Data Model, vea [.edmx File Overview](http://msdn.microsoft.com/es-es/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### Para modificar manualmente el archivo Northwind.edmx para agregar los atributos de personalización de fuente  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el archivo `Northwind.edmx` y, a continuación, elija **Abrir con**.  
  
2.  En el cuadro de diálogo **Abrir con \- Northwind.edmx**, seleccione **Editor XML** y, a continuación, haga clic en **Aceptar**.  
  
3.  Busque el elemento `ConceptualModels` y reemplace el tipo de entidad `Customers` existente con el siguiente elemento que contiene los atributos de asignación de personalización de la fuente:  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4.  Guarde los cambios y cierre el archivo Northwind.edmx.  
  
5.  \(Opcional\) Haga clic con el botón secundario en el archivo Northwind.edmx y, a continuación, haga clic en **Ejecutar herramienta personalizada**.  
  
     Esto regenera el archivo de capa de objeto, que puede ser necesario.  
  
6.  Compile de nuevo el proyecto.  
  
## Ejemplo  
 En el ejemplo anterior se devuelve el resultado siguiente para el URI `http://myservice/``Northwind.svc/Customers('ALFKI')`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## Vea también  
 [Proveedor de Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)