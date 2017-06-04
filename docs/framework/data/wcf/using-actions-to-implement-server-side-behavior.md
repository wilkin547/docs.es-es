---
title: "Usar acciones para implementar el comportamiento del servidor | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11a372db-7168-498b-80d2-9419ff557ba5
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Usar acciones para implementar el comportamiento del servidor
Las acciones OData proporcionan una manera de implementar un comportamiento que actúa sobre un recurso obtenido de un servicio OData.  Por ejemplo, considere una película digital como un recurso; se pueden hacer muchas cosas con ella: desproteger, valorar\/comentar o proteger.  Todos estos son ejemplos de acciones que se pueden implementar mediante un Servicio de datos de WCF que administre películas digitales.  Las acciones se describen en una respuesta OData que contiene un recurso en el que se puede invocar la acción.  Cuando un usuario solicita un recurso que representa una película digital, la respuesta devuelta por el Servicio de datos de WCF contiene información sobre las acciones disponibles para dicho recurso.  La disponibilidad de una acción puede depender del estado del servicio de datos o del recurso.  Por ejemplo, una vez desprotegida una película digital otro usuario no la puede desproteger.  Los clientes pueden invocar una acción con solo especificar una dirección URL.  Por ejemplo, http:\/\/MiServidor\/MovieService.svc\/Movies\(6\) identificaría una película digital concreta y http:\/\/MiServidor\/MovieService.svc\/Movies\(6\)\/Checkout invocaría la acción en esa película específica.  Las acciones le permiten exponer su modelo de servicio sin exponer el modelo de datos.  Continuando con el ejemplo de servicio de películas, quizás desee permitir que un usuario valore una película pero no desee exponer directamente los datos de valoración como un recurso.  Podría implementar una acción de valoración que permitiera al usuario valorar una película pero no tener acceso directamente a los datos de valoración como un recurso.  
  
 Para obtener un ejemplo completo de cómo implementar una acción de WCF Data Service, vea el tema sobre el [proveedor de acciones de WCF Data Services para Entity Framework](http://efactionprovider.codeplex.com/)  
  
## Implementar una acción  
 Para implementar una acción de servicio debe implementar las interfaces <xref:System.IServiceProvider>, <xref:System.Data.Services.Providers.IDataServiceActionProvider> y <xref:System.Data.Services.Providers.IDataServiceInvokable>.  <xref:System.IServiceProvider> permite que WCF Data Services obtenga su implementación de <xref:System.Data.Services.Providers.IDataServiceActionProvider>.  <xref:System.Data.Services.Providers.IDataServiceActionProvider> permite que WCF Data Services cree, busque, describa e invoque acciones de servicio.  <xref:System.Data.Services.Providers.IDataServiceInvokable> le permite invocar el código que implementa el comportamiento de las acciones de servicio y obtener los resultados, si hay alguno.  Tenga en cuenta que WCF Data Services son Servicios de WCF por llamada; se creará una nueva instancia del servicio cada vez que se llame al servicio.  Asegúrese de que no se realiza trabajo innecesario cuando se crea el servicio.  
  
### IServiceProvider  
 <xref:System.IServiceProvider> contiene un método denominado <xref:System.IServiceProvider.GetService%2A>.  WCF Data Services llama a este método para recuperar una serie de proveedores de servicios, incluidos proveedores de servicios de metadatos y proveedores de acciones de servicios de datos.  Cuando se le pida un proveedor de acciones de servicios de datos, devuelva su implementación de <xref:System.Data.Services.Providers.IDataServiceActionProvider>.  
  
### IDataServiceActionProvider  
 <xref:System.Data.Services.Providers.IDataServiceActionProvider> contiene métodos que permiten recuperar información sobre las acciones disponibles.  Al implementar <xref:System.Data.Services.Providers.IDataServiceActionProvider> se aumentan los metadatos para el servicio definidos por la implementación del servicio de <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> con acciones y control de envío a esas acciones según corresponda.  
  
#### AdvertiseServiceAction  
 Se llama a <xref:System.Data.Services.Providers.IDataServiceActionProvider.AdvertiseServiceAction%2A> para determinar qué acciones hay disponibles para el recurso especificado.  Solo se llama a este método para las acciones que no están siempre disponibles.  Se emplea para comprobar si la acción se debe incluir en la respuesta OData según el estado del recurso que se solicita o el estado del servicio.  Usted decide cómo se realiza esta comprobación.  Si resulta costoso calcular la disponibilidad y el recurso actual está en una fuente, es aceptable omitir la comprobación y anunciar la acción.  El parámetro `inFeed` se establece en `true` si el recurso actual que se devuelve forma parte de una fuente.  
  
#### CreateInvokable  
 Se llama a [M:System.Data.Services.Providers.IDataServiceActionProvider.CreateInvokable\(System.Data.Services.DataServiceOperationContext,System.Data.Services.Providers.ServiceAction,System.Object\<xref:System.Data.Services.Providers.IDataServiceActionProvider.CreateInvokable%2A> para crear una <xref:System.Data.Services.Providers.IDataServiceInvokable> que contiene un delegado que encapsula el código que implementa el comportamiento de la acción.  Esto crea la instancia de <xref:System.Data.Services.Providers.IDataServiceInvokable> pero no invoca la acción.  Las acciones de un Servicio de datos de WCF tienen efectos secundarios y deben usarse junto con el proveedor de actualizaciones para guardar estos cambios en disco.  Se llama al método <xref:System.Data.Services.Providers.IDataServiceInvokable.Invoke%2A> desde el método SaveChanges\(\) del proveedor de actualizaciones.  
  
#### GetServiceActions  
 Este método devuelve una colección de instancias de <xref:System.Data.Services.Providers.ServiceAction> que representan todas las acciones que un Servicio de datos de WCF expone.  <xref:System.Data.Services.Providers.ServiceAction> es la representación de metadatos de una acción, que incluye información como el nombre de acción, sus parámetros y su tipo de valor devuelto.  
  
#### GetServiceActionsByBindingParameterType  
 Este método devuelve una colección de todas las instancias de <xref:System.Data.Services.Providers.ServiceAction> que se pueden enlazar al tipo de parámetro de enlace especificado.  Es decir, todos los <xref:System.Data.Services.Providers.ServiceAction> que pueden actuar en el tipo de recurso especificado \(conocido también como tipo de parámetro de enlace\). Esto se usa cuando el servicio devuelve un recurso para incluir información sobre las acciones que se pueden invocar en dicho recurso.  Este método solo debe devolver acciones que se pueden enlazar al tipo de parámetro de enlace exacto \(no a tipos derivados\).  Se llama a este método una vez por solicitud por tipo encontrado y WCF Data Services almacena en memoria caché el resultado.  
  
#### TryResolveServiceAction  
 Este método busca un <xref:System.Data.Services.Providers.ServiceAction> especificado y devuelve `true` si se encuentra <xref:System.Data.Services.Providers.ServiceAction>.  Si se encuentra, se devuelve <xref:System.Data.Services.Providers.ServiceAction> en el parámetro `serviceAction` `out`.  
  
### IDataServiceInvokable  
 Esta interfaz proporciona una forma de ejecutar una acción de un Servicio de datos de WCF.  A la hora de implementar IDataServiceInvokable, es responsable de 3 cosas:  
  
1.  Capturar y posiblemente calcular las referencias de los parámetros  
  
2.  Enviar los parámetros al código que implementa realmente la acción cuando se llama a Invoke\(\)  
  
3.  Almacenar los resultados de Invoke\(\) para que se puedan recuperar mediante GetResult\(\)  
  
 Los parámetros se pueden pasar como tokens.  Esto se debe a que es posible escribir un proveedor de servicios de datos que funcione con tokens que representan recursos; en este caso, quizás necesite convertir \(calcular las referencias\) estos tokens en recursos reales antes de enviarlos a la acción real.  Una vez calculadas las referencias del parámetro, este debe estar en un estado editable para que se guarde y se escriba en disco cualquier cambio realizado en el recurso cuando se invoque la acción.  
  
 Esta interfaz necesita dos métodos: Invoke y GetResult.  Invoke invoca el delegado que implementa el comportamiento de la acción y GetResult devuelve el resultado de la acción.  
  
## Invocar una acción de un Servicio de datos de WCF  
 Las acciones se invocan mediante una solicitud POST HTTP.  La dirección URL especifica el recurso seguido del nombre de la acción.  Los parámetros se pasan en el cuerpo de la solicitud.  Por ejemplo, suponga que hay un servicio denominado MovieService que expone una acción denominada Rate.  Puede usar la dirección URL siguiente para invocar la acción Rate en una película concreta:  
  
 http:\/\/MovieServer\/MovieService.svc\/Movies\(1\)\/Rate  
  
 Movies\(1\) especifica la película que desea valorar y Rate especifica la acción Rate.  El valor real de la valoración estará en el cuerpo de la solicitud HTTP como se muestra en el ejemplo siguiente:  
  
```  
POST http://MovieServer/MoviesService.svc/Movies(1)/Rate HTTP/1.1   
Content-Type: application/json   
Content-Length: 20   
Host: localhost:15238  
{   
   "rating": 4   
}  
  
```  
  
> [!WARNING]
>  El código muestra anterior solo funcionará con WCF Data Services 5.2 y versiones posteriores que admitan JSON ligero.  Si emplea una versión anterior de WCF Data Services, debe especificar el content\-type detallado de json de la manera siguiente: `application/json;odata=verbose`.  
  
 O bien, puede invocar una acción mediante el Cliente de WCF Data Services como se muestra en el fragmento de código siguiente.  
  
```  
MoviesModel context = new MoviesModel (new Uri("http://MyServer/MoviesService.svc/"));  
            //...  
            context.Execute(new Uri("http://MyServer/MoviesService.svc/Movies(1)/Rate"), "POST", new BodyOperationParameter("rating",4) );           
```  
  
 En el fragmento de código anterior, la clase `MoviesModel` se generaba usando Visual Studio para Agregar referencia de servicio a un Servicio de datos de WCF.  
  
## Vea también  
 [WCF Data Services 4.5](../../../../docs/framework/data/wcf/index.md)   
 [Definir WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Desarrollar e implementar WCF Data Services](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)   
 [Proveedores de servicios de datos personalizados](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)