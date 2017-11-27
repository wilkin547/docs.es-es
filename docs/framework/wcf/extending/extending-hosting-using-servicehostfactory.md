---
title: "Extensión del hospedaje mediante ServiceHostFactory"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06859e8f12f96f964054817bac553f6534d5960e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="extending-hosting-using-servicehostfactory"></a>Extensión del hospedaje mediante ServiceHostFactory
La API <xref:System.ServiceModel.ServiceHost> estándar para hospedar servicios en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es un punto de extensibilidad en la arquitectura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Los usuarios pueden derivar sus propias clases de host a partir de <xref:System.ServiceModel.ServiceHost>, normalmente para invalidar <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> para utilizar <xref:System.ServiceModel.Description.ServiceDescription> para agregar extremos predeterminados de manera imperativa o modificar comportamientos, antes de abrir el servicio.  
  
 En el entorno de autohospedaje, no tiene que crear un <xref:System.ServiceModel.ServiceHost> personalizado, puesto que escribe el código que crea instancias del host y, a continuación, llama al método <xref:System.ServiceModel.ICommunicationObject.Open> en él después de haber creado instancias de él. Entre esos dos pasos puede hacer lo que quiera. Podría, por ejemplo, agregar un nuevo <xref:System.ServiceModel.Description.IServiceBehavior>:  
  
```  
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 Este enfoque no es reutilizable. El código que manipula la descripción está codificado en el programa host (en este caso, la función Main()), por lo que es difícil reutilizar esa lógica en otros contextos. Hay también otras maneras de agregar un <xref:System.ServiceModel.Description.IServiceBehavior> que no requieren código imperativo. Puede derivar un atributo a partir de <xref:System.ServiceModel.ServiceBehaviorAttribute> y colocarlo en su tipo de implementación de servicio o puede crear un comportamiento personalizado configurable y componerlo dinámicamente mediante configuración.  
  
 Sin embargo, también se puede utilizar una pequeña variación del ejemplo para resolver este problema. Un enfoque es sacar el código que agrega el ServiceBehavior fuera de `Main()` y meterlo en el método <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> de una derivada personalizada de <xref:System.ServiceModel.ServiceHost>:  
  
```  
public class DerivedHost : ServiceHost  
{  
   public DerivedHost( Type t, params Uri baseAddresses ) :  
      base( t, baseAddresses ) {}  
  
   public override void OnOpening()  
   {  
  this.Description.Add( new MyServiceBehavior() );  
   }  
}  
```  
  
 A continuación, dentro de `Main()` puede utilizar:  
  
```  
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 Ahora ha encapsulado la lógica personalizada en una abstracción limpia que se puede reutilizar con facilidad en muchas aplicaciones ejecutables diferentes de host.  
  
 El uso de este <xref:System.ServiceModel.ServiceHost> personalizado desde dentro de Internet Information Services (IIS) o Windows Process Activation Service (WAS) no es totalmente obvio. Esos entornos son diferentes del entorno de autohospedaje, porque el entorno de hospedaje es el que está creando instancias del <xref:System.ServiceModel.ServiceHost> en nombre de la aplicación. La infraestructura de hospedaje de IIS y WAS no sabe nada sobre su derivado de <xref:System.ServiceModel.ServiceHost> personalizado.  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory> se diseñó para resolver este problema de tener acceso a su <xref:System.ServiceModel.ServiceHost> personalizado desde dentro de IIS o WAS. Dado que un host personalizado que se deriva a partir de <xref:System.ServiceModel.ServiceHost> se configura dinámicamente y es probablemente de varios tipos, el entorno de hospedaje nunca crea instancias de él directamente. En su lugar, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza un patrón de generador para proporcionar una capa de direccionamiento indirecto entre el entorno de hospedaje y el tipo concreto del servicio. A menos que indique lo contrario, utiliza una implementación predeterminada de <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve una instancia de <xref:System.ServiceModel.ServiceHost>. Pero también puede proporcionar su propio generador que devuelva su host derivado especificando el nombre del tipo CLR de la implementación del generador en el @ServiceHost directiva.  
  
 El propósito es que para los casos básicos, la implementación de su propio generador debería ser un ejercicio sencillo. Por ejemplo, aquí hay un <xref:System.ServiceModel.Activation.ServiceHostFactory> personalizado que devuelve un <xref:System.ServiceModel.ServiceHost>derivado:  
  
```  
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 Para utilizar este generador en lugar del generador predeterminado, proporcione el nombre de tipo en el @ServiceHost directiva como se indica a continuación:  
  
```  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Mientras no haya ningún límite técnico para hacer lo que desea al <xref:System.ServiceModel.ServiceHost> que devuelve desde <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, sugerimos que mantenga sus implementaciones de generador lo más simple posible. Si tiene mucha lógica personalizada, es mejor colocar esa lógica dentro de su host en lugar de dentro del generador, para que pueda reutilizarse.  
  
 Hay una capa más en la API de hospedaje que se debe mencionar aquí. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también tiene <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, de los que <xref:System.ServiceModel.ServiceHost> y <xref:System.ServiceModel.Activation.ServiceHostFactory> derivan respectivamente. Existen para escenarios más avanzados donde debe intercambiar grandes partes del sistema de metadatos con sus propias creaciones personalizadas.
