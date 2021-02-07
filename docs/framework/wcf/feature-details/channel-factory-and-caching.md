---
description: 'Más información acerca de: generador de canales y almacenamiento en caché'
title: Generador de canales y almacenamiento en memoria caché
ms.date: 03/30/2017
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
ms.openlocfilehash: 6922191c2b99dea516d0e85aac9ed7bc12a67b81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705205"
---
# <a name="channel-factory-and-caching"></a><span data-ttu-id="b775c-103">Generador de canales y almacenamiento en memoria caché</span><span class="sxs-lookup"><span data-stu-id="b775c-103">Channel Factory and Caching</span></span>

<span data-ttu-id="b775c-104">Las aplicaciones cliente de WCF usan la clase <xref:System.ServiceModel.ChannelFactory%601> para crear un canal de comunicación con un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="b775c-104">WCF client applications use the <xref:System.ServiceModel.ChannelFactory%601> class to create a communication channel with a WCF service.</span></span>  <span data-ttu-id="b775c-105">La crear de instancias de <xref:System.ServiceModel.ChannelFactory%601> genera sobrecarga porque implica las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="b775c-105">Creating <xref:System.ServiceModel.ChannelFactory%601> instances incurs some overhead because it involves the following operations:</span></span>

- <span data-ttu-id="b775c-106">Construir el árbol <xref:System.ServiceModel.Description.ContractDescription></span><span class="sxs-lookup"><span data-stu-id="b775c-106">Constructing the <xref:System.ServiceModel.Description.ContractDescription> tree</span></span>

- <span data-ttu-id="b775c-107">Reflejar todos los tipos de CLR necesarios</span><span class="sxs-lookup"><span data-stu-id="b775c-107">Reflecting all of the required CLR types</span></span>

- <span data-ttu-id="b775c-108">Construir la pila del canal</span><span class="sxs-lookup"><span data-stu-id="b775c-108">Constructing the channel stack</span></span>

- <span data-ttu-id="b775c-109">Desechar recursos</span><span class="sxs-lookup"><span data-stu-id="b775c-109">Disposing of resources</span></span>

<span data-ttu-id="b775c-110">Para ayudar a reducir esta sobrecarga, WCF puede almacenar en caché los generadores de canal cuando se usa un proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="b775c-110">To help minimize this overhead, WCF can cache channel factories when you are using a WCF client proxy.</span></span>

> [!TIP]
> <span data-ttu-id="b775c-111">Tiene el control directo sobre la creación del generador de canales cuando usa la clase <xref:System.ServiceModel.ChannelFactory%601> directamente.</span><span class="sxs-lookup"><span data-stu-id="b775c-111">You have direct control over channel factory creation when you use the <xref:System.ServiceModel.ChannelFactory%601> class directly.</span></span>

<span data-ttu-id="b775c-112">Los proxies de cliente de WCF generados con la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) se derivan de <xref:System.ServiceModel.ClientBase%601> .</span><span class="sxs-lookup"><span data-stu-id="b775c-112">WCF client proxies generated with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) are derived from <xref:System.ServiceModel.ClientBase%601>.</span></span> <span data-ttu-id="b775c-113"><xref:System.ServiceModel.ClientBase%601> define una propiedad <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> estática que define el comportamiento de almacenamiento en memoria caché del generador de canales.</span><span class="sxs-lookup"><span data-stu-id="b775c-113"><xref:System.ServiceModel.ClientBase%601> defines a static <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property that defines channel factory caching behavior.</span></span> <span data-ttu-id="b775c-114">Los valores de la memoria caché se crean para un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="b775c-114">Cache settings are made for a specific type.</span></span> <span data-ttu-id="b775c-115">Por ejemplo, si  `ClientBase<ITest>.CacheSettings` se establece en uno de los valores que se definen a continuación, solo afectará a esos proxy o ClientBase de tipo `ITest` .</span><span class="sxs-lookup"><span data-stu-id="b775c-115">For example, setting  `ClientBase<ITest>.CacheSettings` to one of the values defined below will affect only those proxy/ClientBase of type `ITest`.</span></span> <span data-ttu-id="b775c-116">La configuración de almacenamiento en memoria caché para un <xref:System.ServiceModel.ClientBase%601> determinado es inmutable en cuanto se crea la primera instancia de proxy/ClientBase.</span><span class="sxs-lookup"><span data-stu-id="b775c-116">The cache setting for a particular <xref:System.ServiceModel.ClientBase%601> is immutable as soon as the first proxy/ClientBase instance is created.</span></span>

## <a name="specifying-caching-behavior"></a><span data-ttu-id="b775c-117">Especificar el comportamiento de almacenamiento en memoria caché</span><span class="sxs-lookup"><span data-stu-id="b775c-117">Specifying Caching Behavior</span></span>

<span data-ttu-id="b775c-118">El comportamiento de almacenamiento en memoria caché se especifica estableciendo la propiedad <xref:System.ServiceModel.ClientBase%601.CacheSetting> en uno de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="b775c-118">Caching behavior is specified by setting the <xref:System.ServiceModel.ClientBase%601.CacheSetting> property to one of the following values.</span></span>

|<span data-ttu-id="b775c-119">Valor de configuración de caché</span><span class="sxs-lookup"><span data-stu-id="b775c-119">Cache Setting Value</span></span>|<span data-ttu-id="b775c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b775c-120">Description</span></span>|
|-------------------------|-----------------|
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|<span data-ttu-id="b775c-121">Todas las instancias de <xref:System.ServiceModel.ClientBase%601> dentro del dominio de aplicación pueden participar en el almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b775c-121">All instances of <xref:System.ServiceModel.ClientBase%601> within the app-domain can participate in caching.</span></span> <span data-ttu-id="b775c-122">El desarrollador ha determinado que no hay implicaciones adversas de seguridad para almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b775c-122">The developer has determined that there are no adverse security implications to caching.</span></span> <span data-ttu-id="b775c-123">El almacenamiento en caché no se desactivará aunque se tenga acceso a las propiedades "sensibles a la seguridad" en <xref:System.ServiceModel.ClientBase%601> .</span><span class="sxs-lookup"><span data-stu-id="b775c-123">Caching will not be turned off even if "security-sensitive" properties on <xref:System.ServiceModel.ClientBase%601> are accessed.</span></span> <span data-ttu-id="b775c-124">Las propiedades "sensibles a la seguridad" de <xref:System.ServiceModel.ClientBase%601> son <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> , <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> y <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A> .</span><span class="sxs-lookup"><span data-stu-id="b775c-124">The "security-sensitive" properties of <xref:System.ServiceModel.ClientBase%601> are <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> and <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span></span>|
|<xref:System.ServiceModel.CacheSetting.Default>|<span data-ttu-id="b775c-125">Solo las instancias de <xref:System.ServiceModel.ClientBase%601> creadas desde extremos definidos en archivos de configuración participan en el almacenamiento en memoria caché dentro del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b775c-125">Only instances of <xref:System.ServiceModel.ClientBase%601> created from endpoints defined in configuration files participate in caching within the app-domain.</span></span> <span data-ttu-id="b775c-126">Cualquier instancia de <xref:System.ServiceModel.ClientBase%601> creada mediante programación dentro de ese dominio de aplicación no participará en el almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b775c-126">Any instances of <xref:System.ServiceModel.ClientBase%601> created programmatically within that app-domain will not participate in caching.</span></span> <span data-ttu-id="b775c-127">Además, el almacenamiento en caché se deshabilitará para una instancia de <xref:System.ServiceModel.ClientBase%601> una vez que se tenga acceso a cualquiera de sus propiedades "con seguridad".</span><span class="sxs-lookup"><span data-stu-id="b775c-127">Also, caching will be disabled for an instance of <xref:System.ServiceModel.ClientBase%601> once any of its "security-sensitive" properties is accessed.</span></span>|
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|<span data-ttu-id="b775c-128">El almacenamiento en caché está desactivado para todas las instancias de <xref:System.ServiceModel.ClientBase%601> de un tipo determinado dentro del dominio de aplicación en cuestión.</span><span class="sxs-lookup"><span data-stu-id="b775c-128">Caching is turned off for all instances of <xref:System.ServiceModel.ClientBase%601> of a particular type within the app-domain in question.</span></span>|

<span data-ttu-id="b775c-129">Los fragmentos de código siguientes muestran cómo usar la propiedad <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>.</span><span class="sxs-lookup"><span data-stu-id="b775c-129">The following code snippets illustrate how to use the <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property.</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase<ITest>.CacheSettings = CacheSettings.AlwaysOn;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient (new BasicHttpBinding(), new EndpointAddress(address)))
         {
            // ...
            proxy.Test(msg);
            // ...
         }
      }
   }
}
// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest { }
```

<span data-ttu-id="b775c-130">En el código anterior, todas las instancias de `TestClient` usarán el mismo generador de canales.</span><span class="sxs-lookup"><span data-stu-id="b775c-130">In the above code, all instances of `TestClient` will use the same channel factory.</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase.CacheSettings = CacheSettings.Default;
      int i = 1;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))
         {
            if (i == 4)
            {
               ServiceEndpoint endpoint = proxy.Endpoint;
               ... // use endpoint in some way
            }
            proxy.Test(msg);
         }
         i++;
   }
}

// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}
```

<span data-ttu-id="b775c-131">En el ejemplo anterior, todas las instancias de `TestClient` usarían el mismo generador de canales excepto la instancia nº 4.</span><span class="sxs-lookup"><span data-stu-id="b775c-131">In the example above, all instances of `TestClient` would use the same channel factory except instance #4.</span></span> <span data-ttu-id="b775c-132">La instancia nº 4 usaría un generador de canales que se crea específicamente para su uso.</span><span class="sxs-lookup"><span data-stu-id="b775c-132">Instance #4 would use a channel factory that is created specifically for its use.</span></span> <span data-ttu-id="b775c-133">Este valor funcionaría para escenarios donde un punto de conexión determinado necesita diferentes configuraciones de seguridad que los demás puntos de conexión del mismo tipo de generador de canales (en este caso `ITest`).</span><span class="sxs-lookup"><span data-stu-id="b775c-133">This setting would work for scenarios where a particular endpoint needs different security settings from the other endpoints of the same channel factory type (in this case `ITest`).</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase.CacheSettings = CacheSettings.AlwaysOff;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))
         {
            proxy.Test(msg);
         }
      }
   }
}

// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}
```

<span data-ttu-id="b775c-134">En el ejemplo anterior, todas las instancias de `TestClient` usarían diferentes generadores de canales.</span><span class="sxs-lookup"><span data-stu-id="b775c-134">In the example above, all instances of `TestClient` would use different channel factories.</span></span> <span data-ttu-id="b775c-135">Esto es útil cuando cada extremo tiene distintos requisitos de seguridad y no tiene sentido almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b775c-135">This is useful when each endpoint has different security requirements and it makes no sense to cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="b775c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b775c-136">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601>
- [<span data-ttu-id="b775c-137">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="b775c-137">Building Clients</span></span>](../building-clients.md)
- [<span data-ttu-id="b775c-138">Clientes</span><span class="sxs-lookup"><span data-stu-id="b775c-138">Clients</span></span>](clients.md)
- [<span data-ttu-id="b775c-139">Acceso a los servicios mediante un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="b775c-139">Accessing Services Using a WCF Client</span></span>](../accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="b775c-140">Procedimiento para usar ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="b775c-140">How to: Use the ChannelFactory</span></span>](how-to-use-the-channelfactory.md)
