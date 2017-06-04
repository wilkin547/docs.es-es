---
title: "Proyecciones de consultas (WCF Data Services) | Microsoft Docs"
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
  - "proyección [WCF Data Services]"
  - "proyección de consultas [WCF Data Services]"
  - "Servicios de datos de Microsoft WCF, proyección"
  - "Servicios de datos de Microsoft WCF, consultar"
ms.assetid: a09f4985-9f0d-48c8-b183-83d67a3dfe5f
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Proyecciones de consultas (WCF Data Services)
La proyección proporciona un mecanismo en [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] para reducir la cantidad de datos de la fuente devueltos por una consulta mediante la especificación de que solo se devuelven algunas propiedades de una entidad en la respuesta.  Para obtener más información, vea el tema sobre [OData: opción de consulta del sistema Select \($select\)](http://go.microsoft.com/fwlink/?LinkId=186076).  
  
 En este tema se describen la definición de la proyección de una consulta, cuáles son los requisitos para los tipos con entidad y sin ella, la realización de actualizaciones en los resultados proyectados, la creación de tipos proyectados y la enumeración de algunas consideraciones de proyecciones.  
  
## Definir una proyección de consultas  
 Puede agregar una cláusula de proyección a una consulta mediante la opción de consulta `$select` en un URI o mediante la cláusula [select](../Topic/select%20clause%20\(C%23%20Reference\).md) \([Select](../Topic/Select%20Clause%20\(Visual%20Basic\).md) en Visual Basic\) en una consulta LINQ.  Los datos de entidad devueltos se pueden proyectar en tipos de entidad o en tipos que no son de entidad en el cliente.  Los ejemplos de este tema muestran cómo usar la cláusula `select` en una consulta LINQ.  
  
> [!IMPORTANT]
>  Se puede producir una pérdida de datos en el servicio de datos cuando se guardan actualizaciones efectuadas en tipos proyectados.  Para obtener más información, vea [Consideraciones sobre proyecciones](#considerations).  
  
## Requisitos para tipos con entidad y sin ella  
 Los tipos de entidad deben tener una o varias propiedades de entidad que constituyen la clave de la entidad.  Los tipos de entidad se definen en clientes de una de las siguientes formas:  
  
-   Aplicando las clases <xref:System.Data.Services.Common.DataServiceKeyAttribute> o <xref:System.Data.Services.Common.DataServiceEntityAttribute> al tipo.  
  
-   Cuando el tipo tiene una propiedad denominada `ID`.  
  
-   Cuando el tipo tiene una propiedad denominada *type*`ID`, donde *type* es el nombre del tipo.  
  
 De forma predeterminada, cuando proyecte los resultados de la consulta en un tipo definido en el cliente, las propiedades solicitadas en la proyección deben existir en el tipo de cliente.  Sin embargo, cuando especifica un valor de `true` para la propiedad <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext>, es necesario que se produzcan las propiedades especificadas en la proyección en el tipo de cliente.  
  
### Realizar actualizaciones en los resultados proyectados  
 Cuando proyecte los resultados de la consulta en tipos de entidad en el cliente, la clase <xref:System.Data.Services.Client.DataServiceContext> puede realizar el seguimiento de esos objetos con las actualizaciones que se van a devolver al servicio de datos cuando se llame al método <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  No obstante, las actualizaciones efectuadas en datos proyectados en entidades sin tipo en el cliente no se pueden devolver al servicio de datos.  Esto se debe a que el servicio de datos no puede actualizar la entidad correcta en el origen de datos sin ninguna clave que identifique la instancia de la entidad.  Los tipos sin identidad no se adjunta a la clase <xref:System.Data.Services.Client.DataServiceContext>.  
  
 Cuando una o varias propiedades de un tipo de entidad definido en el servicio de datos no se producen en el tipo de cliente en el que se proyecta la entidad, las inserciones de nuevas entidades no contendrán estas propiedades que faltan.  En este caso, las actualizaciones realizadas en entidades existentes **tampoco** incluirán estas propiedades que faltan.  Cuando un valor existe para tal propiedad, la actualización la restablece en el valor predeterminado de la propiedad, de la forma definida en el origen de datos.  
  
### Crear tipos proyectados  
 En el siguiente ejemplo se usa una consulta LINQ anónima que proyecta propiedades de relacionadas con la dirección del tipo `Customers` en un nuevo tipo `CustomerAddress`, que se define en el cliente y al que se le puede dar el atributo de tipo de entidad:  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressspecific)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressspecific)]  
  
 En este ejemplo, se usa el patrón de inicializador de objeto para crear una nueva instancia del tipo `CustmerAddress` en vez de llamar a un constructor.  No se admiten constructores cuando se realizan proyecciones en tipos de entidad, pero se pueden usar al realizar proyecciones en tipos sin entidad y anónimos.  Puesto que `CustomerAddress` es un tipo de entidad, los cambios se pueden efectuar en el servicio de datos y devolvérselos a él.  
  
 Asimismo, los datos de tipo `Customer` se proyectan en una instancia del tipo de entidad `CustomerAddress` en vez de en un tipo anónimo.  Se admiten las proyecciones en tipos anónimos, pero los datos son de solo lectura porque los tipos anónimos se tratan como tipos sin entidad.  
  
 La configuración de la enumeración <xref:System.Data.Services.Client.MergeOption> de la clase <xref:System.Data.Services.Client.DataServiceContext> se usa para identificar la resolución durante la proyección de la consulta.  Es decir, si una instancia del tipo `Customer` ya existe en la clase <xref:System.Data.Services.Client.DataServiceContext>, una instancia de `CustomerAddress` con la misma identidad seguirá las reglas de resolución de entidades establecidas por la enumeración <xref:System.Data.Services.Client.MergeOption>.  
  
 En la siguiente tabla se describen los comportamientos cuando se proyectan resultados en tipos con entidad y sin ella:  
  
|Acción|Tipo de entidad|Tipo sin entidad|  
|------------|---------------------|----------------------|  
|Crear una nueva instancia proyectada mediante inicializadores, como en el ejemplo siguiente:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithInitializer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithinitializer)]
 [!code-vb[Astoria Northwind Client#ProjectWithInitializer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithinitializer)]|Compatible|Compatible|  
|Crear una nueva instancia proyectada con constructores, como en el ejemplo siguiente:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithConstructor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithconstructor)]
 [!code-vb[Astoria Northwind Client#ProjectWithConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithconstructor)]|Se inicia una clase <xref:System.NotSupportedException>.|Compatible|  
|Usar una proyección para transformar un valor de propiedad, como en el ejemplo siguiente:<br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithTransform](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithtransform)]
 [!code-vb[Astoria Northwind Client#ProjectWithTransform](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithtransform)]<br /><br /> Esta transformación no la admiten los tipos de entidad porque puede confundir y posiblemente sobrescribir los datos en el origen de datos que pertenece a otra entidad.|Se inicia una clase <xref:System.NotSupportedException>.|Compatible|  
  
<a name="considerations"></a>   
## Consideraciones sobre proyecciones  
 Se aplican las siguientes consideraciones adicionales cuando se define una proyección de consultas.  
  
-   Cuando defina las fuentes personalizadas para el formato Atom, debe asegurarse de que se incluyan todas las propiedades de entidad con asignaciones personalizadas en la proyección.  Cuando no se incluya ninguna propiedad de entidad asignada en la proyección, se puede producir la pérdida de datos.  Para obtener más información, consulta [Personalización de fuentes](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
-   Cuando se realicen inserciones en un tipo proyectado que no contenga todas las propiedades de la entidad en el modelo de datos del servicio de datos, las propiedades no incluidas en la proyección en el cliente se establecen en sus valores predeterminados.  
  
-   Cuando se realicen actualizaciones en un tipo proyectado que no contenga todas las propiedades de la entidad en el modelo de datos del servicio de datos, los valores existentes no incluidos en la proyección en el cliente se sobrescribirán con valores predeterminados sin inicializar.  
  
-   Cuando una proyección incluya una propiedad compleja, se debe devolver todo el objeto complejo.  
  
-   Cuando una proyección incluya una propiedad de navegación, los objetos relacionados se cargan implícitamente sin tener que llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>.  No se admite el método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> para su uso en una consulta proyectada.  
  
-   Las consultas de proyecciones de consultas en el cliente se traducen para usar la opción de consulta `$select` en el URI de solicitud.  Cuando una consulta con proyección se ejecuta con una versión anterior de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] que no admite la opción de consulta `$select`, se devuelve un error. Esto también puede pasar cuando la propiedad <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> de <xref:System.Data.Services.DataServiceBehavior> para el servicio de datos está establecida en un valor de <xref:System.Data.Services.Common.DataServiceProtocolVersion>.  Para obtener más información, consulta [Control de versiones del servicio de datos](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
 Para obtener más información, consulta [Cómo: Proyectar los resultados de una consulta](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md).  
  
## Vea también  
 [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)