---
title: "Materializaci&#243;n de objetos (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, biblioteca de cliente"
  - "Servicios de datos de Microsoft WCF, consultar"
ms.assetid: f0dbf7b0-0292-4e31-9ae4-b98288336dc1
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Materializaci&#243;n de objetos (WCF Data Services)
Cuando use el cuadro de diálogo **Agregar referencia de servicio** para utilizar una fuente [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] en una aplicación cliente basada en .NET Framework, se generarán clases equivalentes para cada tipo de entidad en el modelo de datos expuesto por la fuente.  Para obtener más información, consulta [Generar la biblioteca de cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  Los datos de entidad devueltos por una consulta se materializan en una instancia de una de estas clases de servicio de datos de cliente generadas.  Para obtener más información sobre las opciones de combinación y resolución de identidades para objetos de los que se realiza el seguimiento, vea [Administrar el contexto del servicio de datos](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] también le permite definir sus propias clases de servicio de datos de cliente en lugar de usar las clases de datos generadas por herramientas.  De esta forma, puede usar sus propias clases de datos, que también se conocen como clases de datos "tipos de objetos CLR antiguos sin formato" \(POCO\).  Al usar estos tipos de clases de datos personalizadas, debe asignar un atributo a la clase de datos con la clase <xref:System.Data.Services.Common.DataServiceKeyAttribute> o la clase <xref:System.Data.Services.Common.DataServiceEntityAttribute> y asegurarse de que los nombres de tipos en el cliente coincidan con los del modelo de datos del servicio de datos.  
  
 Después de que la biblioteca recibe el mensaje de respuesta de la consulta, materializa los datos devueltos desde la fuente [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] en instancias de las clases del servicio de datos de cliente que tienen el tipo de la consulta.  El proceso general para materializar estos objetos es el siguiente:  
  
1.  La biblioteca de cliente lee el tipo serializado desde el elemento `entry` en la fuente del mensaje de respuesta e intenta crear una nueva instancia del tipo correcto de una de estas formas:  
  
    -   Cuando el tipo declarado en la fuente tenga el mismo nombre que el tipo de la clase <xref:System.Data.Services.Client.DataServiceQuery%601>, se crea una nueva instancia de este tipo mediante el constructor vacío.  
  
    -   Cuando el tipo declarado en la fuente tenga el mismo tipo que se deriva del tipo de la clase <xref:System.Data.Services.Client.DataServiceQuery%601>, se crea una nueva instancia de este tipo derivado mediante el constructor vacío.  
  
    -   Cuando el tipo declarado en la fuente no se pueda hacer coincidir con el tipo de la clase <xref:System.Data.Services.Client.DataServiceQuery%601> ni con ningún tipo derivado, se crea una nueva instancia del tipo consultado mediante el constructor vacío.  
  
    -   Cuando se establezca la propiedad <xref:System.Data.Services.Client.DataServiceContext.ResolveType%2A>, se llama al delegado proporcionado para invalidar la asignación de tipos basada en nombre predeterminada y, en su lugar, se crea una nueva instancia del tipo devuelto por el delgado <xref:System.Func%602>.  Si este delegado devuelve un valor NULL, en su lugar se crea una nueva instancia del tipo consultado.  Quizá sea necesario invalidar la asignación de nombre basada en tipo predeterminada para admitir escenarios de herencia.  
  
2.  La biblioteca de cliente lee el valor de URI desde el elemento `id` de `entry`, que es el valor de identidad de la entidad.  A menos que se use un valor de la propiedad <xref:System.Data.Services.Client.DataServiceContext.MergeOption%2A> de la enumeración <xref:System.Data.Services.Client.MergeOption>, se usa el valor de identidad para realizar el seguimiento del objeto en la clase <xref:System.Data.Services.Client.DataServiceContext>.  El valor de identidad también se usa para garantizar que solo se cree una única instancia de identidad, aunque se devuelva varias veces una entidad en la respuesta de la consulta.  
  
3.  La biblioteca de cliente lee propiedades desde la entrada de la fuente y establece las propiedades correspondientes en el objeto recién creado.  Cuando un objeto con el mismo valor de identidad se produce en la clase <xref:System.Data.Services.Client.DataServiceContext>, las propiedades se establecen basándose en la configuración de <xref:System.Data.Services.Client.MergeOption> de la clase <xref:System.Data.Services.Client.DataServiceContext>.  Puede que la respuesta contenga valores de propiedad para los que no se produzca ninguna propiedad correspondiente en el tipo de cliente.  En este caso, la acción depende del valor de la propiedad <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> de la clase <xref:System.Data.Services.Client.DataServiceContext>.  Cuando esta propiedad se establece en `true`, se ignora la propiedad que falta.  En caso contrario, se produce un error.  Las propiedades se establecen de la siguiente forma:  
  
    -   Las propiedades escalares se establecen en el valor correspondiente de la entrada del mensaje de respuesta.  
  
    -   Las propiedades complejas se establecen en una nueva instancia de tipo complejo, que se establecen con las propiedades del tipo complejo de la respuesta.  
  
    -   Las propiedades de navegación que devuelven una colección de entidades relacionadas se establecen en una instancia nueva o en una instancia existente de la interfaz <xref:System.Collections.Generic.ICollection%601>, donde `T` es el tipo de entidad relacionada.  Esta colección está vacía a menos que se hayan cargado los objetos relacionados en la clase <xref:System.Data.Services.Client.DataServiceContext>.  Para obtener más información, consulta [Cargar contenido aplazado](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
        > [!NOTE]
        >  Cuando las clases de datos del cliente generadas admitan el enlace de datos, las propiedades de navegación devuelven instancias de la clase <xref:System.Data.Services.Client.DataServiceCollection%601> en su lugar.  Para obtener más información, consulta [Enlazar datos a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
4.  Se genera el evento <xref:System.Data.Services.Client.DataServiceContext.ReadingEntity>.  
  
5.  La biblioteca de clientes adjunta el objeto a la clase <xref:System.Data.Services.Client.DataServiceContext>.  El objeto no se adjunta cuando la clase <xref:System.Data.Services.Client.MergeOption> es la enumeración <xref:System.Data.Services.Client.MergeOption>.  
  
## Vea también  
 [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)   
 [Proyecciones de consultas](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)