---
description: Más información acerca de cómo extender el hospedaje mediante ServiceHostFactory
title: Extensión del hospedaje mediante ServiceHostFactory
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: cd7749a153f23586bbf570eaf97f5ae849fc522d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735145"
---
# <a name="extending-hosting-using-servicehostfactory"></a><span data-ttu-id="aff67-103">Extensión del hospedaje mediante ServiceHostFactory</span><span class="sxs-lookup"><span data-stu-id="aff67-103">Extending Hosting Using ServiceHostFactory</span></span>

<span data-ttu-id="aff67-104">La <xref:System.ServiceModel.ServiceHost> API estándar para hospedar servicios en Windows Communication Foundation (WCF) es un punto de extensibilidad en la arquitectura de WCF.</span><span class="sxs-lookup"><span data-stu-id="aff67-104">The standard <xref:System.ServiceModel.ServiceHost> API for hosting services in Windows Communication Foundation (WCF) is an extensibility point in the WCF architecture.</span></span> <span data-ttu-id="aff67-105">Los usuarios pueden derivar sus propias clases de host a partir de <xref:System.ServiceModel.ServiceHost>, normalmente para invalidar <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> para utilizar <xref:System.ServiceModel.Description.ServiceDescription> para agregar extremos predeterminados de manera imperativa o modificar comportamientos, antes de abrir el servicio.</span><span class="sxs-lookup"><span data-stu-id="aff67-105">Users can derive their own host classes from <xref:System.ServiceModel.ServiceHost>, usually to override <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> to use <xref:System.ServiceModel.Description.ServiceDescription> to add default endpoints imperatively or modify behaviors, prior to opening the service.</span></span>  
  
 <span data-ttu-id="aff67-106">En el entorno de autohospedaje, no tiene que crear un <xref:System.ServiceModel.ServiceHost> personalizado, puesto que escribe el código que crea instancias del host y, a continuación, llama al método <xref:System.ServiceModel.ICommunicationObject.Open> en él después de haber creado instancias de él.</span><span class="sxs-lookup"><span data-stu-id="aff67-106">In the self-host environment, you do not have to create a custom <xref:System.ServiceModel.ServiceHost> because you write the code that instantiates the host and then call <xref:System.ServiceModel.ICommunicationObject.Open> on it after you instantiate it.</span></span> <span data-ttu-id="aff67-107">Entre esos dos pasos puede hacer lo que quiera.</span><span class="sxs-lookup"><span data-stu-id="aff67-107">Between those two steps you can do whatever you want.</span></span> <span data-ttu-id="aff67-108">Podría, por ejemplo, agregar un nuevo <xref:System.ServiceModel.Description.IServiceBehavior>:</span><span class="sxs-lookup"><span data-stu-id="aff67-108">You could, for example, add a new <xref:System.ServiceModel.Description.IServiceBehavior>:</span></span>  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="aff67-109">Este enfoque no es reutilizable.</span><span class="sxs-lookup"><span data-stu-id="aff67-109">This approach is not reusable.</span></span> <span data-ttu-id="aff67-110">El código que manipula la descripción está codificado en el programa host (en este caso, la función Main()), por lo que es difícil reutilizar esa lógica en otros contextos.</span><span class="sxs-lookup"><span data-stu-id="aff67-110">The code that manipulates the description is coded into the host program (in this case, the Main() function), so it is difficult to reuse that logic in other contexts.</span></span> <span data-ttu-id="aff67-111">Hay también otras maneras de agregar un <xref:System.ServiceModel.Description.IServiceBehavior> que no requieren código imperativo.</span><span class="sxs-lookup"><span data-stu-id="aff67-111">There are also other ways of adding an <xref:System.ServiceModel.Description.IServiceBehavior> that do not require imperative code.</span></span> <span data-ttu-id="aff67-112">Puede derivar un atributo a partir de <xref:System.ServiceModel.ServiceBehaviorAttribute> y colocarlo en su tipo de implementación de servicio o puede crear un comportamiento personalizado configurable y componerlo dinámicamente mediante configuración.</span><span class="sxs-lookup"><span data-stu-id="aff67-112">You can derive an attribute from <xref:System.ServiceModel.ServiceBehaviorAttribute> and put that on your service implementation type or you can make a custom behavior configurable and compose it dynamically using configuration.</span></span>  
  
 <span data-ttu-id="aff67-113">Sin embargo, también se puede utilizar una pequeña variación del ejemplo para resolver este problema.</span><span class="sxs-lookup"><span data-stu-id="aff67-113">However, a slight variation of the example can also be used to solve this problem.</span></span> <span data-ttu-id="aff67-114">Un enfoque es sacar el código que agrega el ServiceBehavior fuera de `Main()` y meterlo en el método <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> de una derivada personalizada de <xref:System.ServiceModel.ServiceHost>:</span><span class="sxs-lookup"><span data-stu-id="aff67-114">One approach is to move the code that adds the ServiceBehavior out of `Main()` and into the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method of a custom derivative of <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```csharp
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
  
 <span data-ttu-id="aff67-115">A continuación, dentro de `Main()` puede utilizar:</span><span class="sxs-lookup"><span data-stu-id="aff67-115">Then, inside of `Main()` you can use:</span></span>  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="aff67-116">Ahora ha encapsulado la lógica personalizada en una abstracción limpia que se puede reutilizar con facilidad en muchas aplicaciones ejecutables diferentes de host.</span><span class="sxs-lookup"><span data-stu-id="aff67-116">Now you have encapsulated the custom logic into a clean abstraction that can be easily reused across many different host executables.</span></span>  
  
 <span data-ttu-id="aff67-117">El uso de este <xref:System.ServiceModel.ServiceHost> personalizado desde dentro de Internet Information Services (IIS) o Windows Process Activation Service (WAS) no es totalmente obvio.</span><span class="sxs-lookup"><span data-stu-id="aff67-117">It is not immediately obvious how to use this custom <xref:System.ServiceModel.ServiceHost> from inside of Internet Information Services (IIS) or Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="aff67-118">Esos entornos son diferentes del entorno de autohospedaje, porque el entorno de hospedaje es el que está creando instancias del <xref:System.ServiceModel.ServiceHost> en nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aff67-118">Those environments are different than the self-host environment, because the hosting environment is the one instantiating the <xref:System.ServiceModel.ServiceHost> on behalf of the application.</span></span> <span data-ttu-id="aff67-119">La infraestructura de hospedaje de IIS y WAS no sabe nada sobre su derivado de <xref:System.ServiceModel.ServiceHost> personalizado.</span><span class="sxs-lookup"><span data-stu-id="aff67-119">The IIS and WAS hosting infrastructure does not know anything about your custom <xref:System.ServiceModel.ServiceHost> derivative.</span></span>  
  
 <span data-ttu-id="aff67-120"><xref:System.ServiceModel.Activation.ServiceHostFactory> se diseñó para resolver este problema de tener acceso a su <xref:System.ServiceModel.ServiceHost> personalizado desde dentro de IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="aff67-120">The <xref:System.ServiceModel.Activation.ServiceHostFactory> was designed to solve this problem of accessing your custom <xref:System.ServiceModel.ServiceHost> from within IIS or WAS.</span></span> <span data-ttu-id="aff67-121">Dado que un host personalizado que se deriva a partir de <xref:System.ServiceModel.ServiceHost> se configura dinámicamente y es probablemente de varios tipos, el entorno de hospedaje nunca crea instancias de él directamente.</span><span class="sxs-lookup"><span data-stu-id="aff67-121">Because a custom host that is derived from <xref:System.ServiceModel.ServiceHost> is dynamically configured and potentially of various types, the hosting environment never instantiates it directly.</span></span> <span data-ttu-id="aff67-122">En su lugar, WCF usa un patrón de fábrica para proporcionar una capa de direccionamiento indirecto entre el entorno de hospedaje y el tipo concreto del servicio.</span><span class="sxs-lookup"><span data-stu-id="aff67-122">Instead, WCF uses a factory pattern to provide a layer of indirection between the hosting environment and the concrete type of the service.</span></span> <span data-ttu-id="aff67-123">A menos que indique lo contrario, utiliza una implementación predeterminada de <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve una instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="aff67-123">Unless you tell it otherwise, it uses a default implementation of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="aff67-124">Pero también puede proporcionar su propio generador que devuelve el host derivado especificando el nombre de tipo de CLR de la implementación de fábrica en la @ServiceHost Directiva.</span><span class="sxs-lookup"><span data-stu-id="aff67-124">But you can also provide your own factory that returns your derived host by specifying the CLR type name of your factory implementation in the @ServiceHost directive.</span></span>  
  
 <span data-ttu-id="aff67-125">El propósito es que para los casos básicos, la implementación de su propio generador debería ser un ejercicio sencillo.</span><span class="sxs-lookup"><span data-stu-id="aff67-125">The intent is that for basic cases, implementing your own factory should be a straight forward exercise.</span></span> <span data-ttu-id="aff67-126">Por ejemplo, aquí hay un <xref:System.ServiceModel.Activation.ServiceHostFactory> personalizado que devuelve un <xref:System.ServiceModel.ServiceHost>derivado:</span><span class="sxs-lookup"><span data-stu-id="aff67-126">For example, here is a custom <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns a derived <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```csharp
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 <span data-ttu-id="aff67-127">Para usar este generador en lugar del generador predeterminado, proporcione el nombre de tipo en la @ServiceHost Directiva de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="aff67-127">To use this factory instead of the default factory, provide the type name in the @ServiceHost directive as follows:</span></span>  
  
`<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>`  
  
 <span data-ttu-id="aff67-128">Mientras no haya ningún límite técnico para hacer lo que desea al <xref:System.ServiceModel.ServiceHost> que devuelve desde <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, sugerimos que mantenga sus implementaciones de generador lo más simple posible.</span><span class="sxs-lookup"><span data-stu-id="aff67-128">While there is no technical limit on doing what you want to the <xref:System.ServiceModel.ServiceHost> you return from <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, we suggest that you keep your factory implementations as simple as possible.</span></span> <span data-ttu-id="aff67-129">Si tiene una gran cantidad de lógica personalizada, es mejor colocar esa lógica dentro de su host en lugar de dentro del generador para que se pueda volver a usar.</span><span class="sxs-lookup"><span data-stu-id="aff67-129">If you have lots of custom logic, it is better to put that logic inside of your host instead of inside the factory so that it can be reusable.</span></span>  
  
 <span data-ttu-id="aff67-130">Hay una capa más en la API de hospedaje que se debe mencionar aquí.</span><span class="sxs-lookup"><span data-stu-id="aff67-130">There is one more layer to the hosting API that should be mentioned here.</span></span> <span data-ttu-id="aff67-131">WCF también tiene <xref:System.ServiceModel.ServiceHostBase> y <xref:System.ServiceModel.Activation.ServiceHostFactoryBase> , de los cuales <xref:System.ServiceModel.ServiceHost> y, <xref:System.ServiceModel.Activation.ServiceHostFactory> respectivamente, derivan.</span><span class="sxs-lookup"><span data-stu-id="aff67-131">WCF also has <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, from which <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.Activation.ServiceHostFactory> respectively derive.</span></span> <span data-ttu-id="aff67-132">Existen para escenarios más avanzados donde debe intercambiar grandes partes del sistema de metadatos con sus propias creaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="aff67-132">Those exist for more advanced scenarios where you must swap out large parts of the metadata system with your own customized creations.</span></span>
