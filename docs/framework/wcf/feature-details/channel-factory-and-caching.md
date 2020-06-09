---
title: Generador de canales y almacenamiento en memoria caché
ms.date: 03/30/2017
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
ms.openlocfilehash: 5b8348a98b484ca08e3dbeba141dc49825c8c071
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587370"
---
# <a name="channel-factory-and-caching"></a><span data-ttu-id="4ed89-102">Generador de canales y almacenamiento en memoria caché</span><span class="sxs-lookup"><span data-stu-id="4ed89-102">Channel Factory and Caching</span></span>

<span data-ttu-id="4ed89-103">Las aplicaciones cliente de WCF usan la clase <xref:System.ServiceModel.ChannelFactory%601> para crear un canal de comunicación con un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="4ed89-103">WCF client applications use the <xref:System.ServiceModel.ChannelFactory%601> class to create a communication channel with a WCF service.</span></span>  <span data-ttu-id="4ed89-104">La crear de instancias de <xref:System.ServiceModel.ChannelFactory%601> genera sobrecarga porque implica las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="4ed89-104">Creating <xref:System.ServiceModel.ChannelFactory%601> instances incurs some overhead because it involves the following operations:</span></span>

- <span data-ttu-id="4ed89-105">Construir el árbol <xref:System.ServiceModel.Description.ContractDescription></span><span class="sxs-lookup"><span data-stu-id="4ed89-105">Constructing the <xref:System.ServiceModel.Description.ContractDescription> tree</span></span>

- <span data-ttu-id="4ed89-106">Reflejar todos los tipos de CLR necesarios</span><span class="sxs-lookup"><span data-stu-id="4ed89-106">Reflecting all of the required CLR types</span></span>

- <span data-ttu-id="4ed89-107">Construir la pila del canal</span><span class="sxs-lookup"><span data-stu-id="4ed89-107">Constructing the channel stack</span></span>

- <span data-ttu-id="4ed89-108">Desechar recursos</span><span class="sxs-lookup"><span data-stu-id="4ed89-108">Disposing of resources</span></span>

<span data-ttu-id="4ed89-109">Para ayudar a reducir esta sobrecarga, WCF puede almacenar en caché los generadores de canal cuando se usa un proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="4ed89-109">To help minimize this overhead, WCF can cache channel factories when you are using a WCF client proxy.</span></span>

> [!TIP]
> <span data-ttu-id="4ed89-110">Tiene el control directo sobre la creación del generador de canales cuando usa la clase <xref:System.ServiceModel.ChannelFactory%601> directamente.</span><span class="sxs-lookup"><span data-stu-id="4ed89-110">You have direct control over channel factory creation when you use the <xref:System.ServiceModel.ChannelFactory%601> class directly.</span></span>

<span data-ttu-id="4ed89-111">Los proxies de cliente de WCF generados con la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) se derivan de <xref:System.ServiceModel.ClientBase%601> .</span><span class="sxs-lookup"><span data-stu-id="4ed89-111">WCF client proxies generated with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) are derived from <xref:System.ServiceModel.ClientBase%601>.</span></span> <span data-ttu-id="4ed89-112"><xref:System.ServiceModel.ClientBase%601> define una propiedad <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> estática que define el comportamiento de almacenamiento en memoria caché del generador de canales.</span><span class="sxs-lookup"><span data-stu-id="4ed89-112"><xref:System.ServiceModel.ClientBase%601> defines a static <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property that defines channel factory caching behavior.</span></span> <span data-ttu-id="4ed89-113">Los valores de la memoria caché se crean para un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="4ed89-113">Cache settings are made for a specific type.</span></span> <span data-ttu-id="4ed89-114">Por ejemplo, si `ClientBase<ITest>.CacheSettings` se establece en uno de los valores que se definen a continuación, solo afectará a esos proxy o ClientBase de tipo `ITest` .</span><span class="sxs-lookup"><span data-stu-id="4ed89-114">For example, setting  `ClientBase<ITest>.CacheSettings` to one of the values defined below will affect only those proxy/ClientBase of type `ITest`.</span></span> <span data-ttu-id="4ed89-115">La configuración de almacenamiento en memoria caché para un <xref:System.ServiceModel.ClientBase%601> determinado es inmutable en cuanto se crea la primera instancia de proxy/ClientBase.</span><span class="sxs-lookup"><span data-stu-id="4ed89-115">The cache setting for a particular <xref:System.ServiceModel.ClientBase%601> is immutable as soon as the first proxy/ClientBase instance is created.</span></span>

## <a name="specifying-caching-behavior"></a><span data-ttu-id="4ed89-116">Especificar el comportamiento de almacenamiento en memoria caché</span><span class="sxs-lookup"><span data-stu-id="4ed89-116">Specifying Caching Behavior</span></span>

<span data-ttu-id="4ed89-117">El comportamiento de almacenamiento en memoria caché se especifica estableciendo la propiedad <xref:System.ServiceModel.ClientBase%601.CacheSetting> en uno de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="4ed89-117">Caching behavior is specified by setting the <xref:System.ServiceModel.ClientBase%601.CacheSetting> property to one of the following values.</span></span>

|<span data-ttu-id="4ed89-118">Valor de configuración de caché</span><span class="sxs-lookup"><span data-stu-id="4ed89-118">Cache Setting Value</span></span>|<span data-ttu-id="4ed89-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ed89-119">Description</span></span>|
|-------------------------|-----------------|
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|<span data-ttu-id="4ed89-120">Todas las instancias de <xref:System.ServiceModel.ClientBase%601> dentro del dominio de aplicación pueden participar en el almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4ed89-120">All instances of <xref:System.ServiceModel.ClientBase%601> within the app-domain can participate in caching.</span></span> <span data-ttu-id="4ed89-121">El desarrollador ha determinado que no hay implicaciones adversas de seguridad para almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4ed89-121">The developer has determined that there are no adverse security implications to caching.</span></span> <span data-ttu-id="4ed89-122">El almacenamiento en caché no se desactivará aunque se tenga acceso a las propiedades "sensibles a la seguridad" en <xref:System.ServiceModel.ClientBase%601> .</span><span class="sxs-lookup"><span data-stu-id="4ed89-122">Caching will not be turned off even if "security-sensitive" properties on <xref:System.ServiceModel.ClientBase%601> are accessed.</span></span> <span data-ttu-id="4ed89-123">Las propiedades "sensibles a la seguridad" de <xref:System.ServiceModel.ClientBase%601> son <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> , <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> y <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A> .</span><span class="sxs-lookup"><span data-stu-id="4ed89-123">The "security-sensitive" properties of <xref:System.ServiceModel.ClientBase%601> are <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> and <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span></span>|
|<xref:System.ServiceModel.CacheSetting.Default>|<span data-ttu-id="4ed89-124">Solo las instancias de <xref:System.ServiceModel.ClientBase%601> creadas desde extremos definidos en archivos de configuración participan en el almacenamiento en memoria caché dentro del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ed89-124">Only instances of <xref:System.ServiceModel.ClientBase%601> created from endpoints defined in configuration files participate in caching within the app-domain.</span></span> <span data-ttu-id="4ed89-125">Cualquier instancia de <xref:System.ServiceModel.ClientBase%601> creada mediante programación dentro de ese dominio de aplicación no participará en el almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4ed89-125">Any instances of <xref:System.ServiceModel.ClientBase%601> created programmatically within that app-domain will not participate in caching.</span></span> <span data-ttu-id="4ed89-126">Además, el almacenamiento en caché se deshabilitará para una instancia de <xref:System.ServiceModel.ClientBase%601> una vez que se tenga acceso a cualquiera de sus propiedades "con seguridad".</span><span class="sxs-lookup"><span data-stu-id="4ed89-126">Also, caching will be disabled for an instance of <xref:System.ServiceModel.ClientBase%601> once any of its "security-sensitive" properties is accessed.</span></span>|
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|<span data-ttu-id="4ed89-127">El almacenamiento en caché está desactivado para todas las instancias de <xref:System.ServiceModel.ClientBase%601> de un tipo determinado dentro del dominio de aplicación en cuestión.</span><span class="sxs-lookup"><span data-stu-id="4ed89-127">Caching is turned off for all instances of <xref:System.ServiceModel.ClientBase%601> of a particular type within the app-domain in question.</span></span>|

<span data-ttu-id="4ed89-128">Los fragmentos de código siguientes muestran cómo usar la propiedad <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ed89-128">The following code snippets illustrate how to use the <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property.</span></span>

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

<span data-ttu-id="4ed89-129">En el código anterior, todas las instancias de `TestClient` usarán el mismo generador de canales.</span><span class="sxs-lookup"><span data-stu-id="4ed89-129">In the above code, all instances of `TestClient` will use the same channel factory.</span></span>

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

<span data-ttu-id="4ed89-130">En el ejemplo anterior, todas las instancias de `TestClient` usarían el mismo generador de canales excepto la instancia nº 4.</span><span class="sxs-lookup"><span data-stu-id="4ed89-130">In the example above, all instances of `TestClient` would use the same channel factory except instance #4.</span></span> <span data-ttu-id="4ed89-131">La instancia nº 4 usaría un generador de canales que se crea específicamente para su uso.</span><span class="sxs-lookup"><span data-stu-id="4ed89-131">Instance #4 would use a channel factory that is created specifically for its use.</span></span> <span data-ttu-id="4ed89-132">Este valor funcionaría para escenarios donde un punto de conexión determinado necesita diferentes configuraciones de seguridad que los demás puntos de conexión del mismo tipo de generador de canales (en este caso `ITest`).</span><span class="sxs-lookup"><span data-stu-id="4ed89-132">This setting would work for scenarios where a particular endpoint needs different security settings from the other endpoints of the same channel factory type (in this case `ITest`).</span></span>

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

<span data-ttu-id="4ed89-133">En el ejemplo anterior, todas las instancias de `TestClient` usarían diferentes generadores de canales.</span><span class="sxs-lookup"><span data-stu-id="4ed89-133">In the example above, all instances of `TestClient` would use different channel factories.</span></span> <span data-ttu-id="4ed89-134">Esto es útil cuando cada extremo tiene distintos requisitos de seguridad y no tiene sentido almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4ed89-134">This is useful when each endpoint has different security requirements and it makes no sense to cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ed89-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ed89-135">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601>
- [<span data-ttu-id="4ed89-136">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="4ed89-136">Building Clients</span></span>](../building-clients.md)
- [<span data-ttu-id="4ed89-137">Clientes</span><span class="sxs-lookup"><span data-stu-id="4ed89-137">Clients</span></span>](clients.md)
- [<span data-ttu-id="4ed89-138">Acceso a los servicios mediante un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="4ed89-138">Accessing Services Using a WCF Client</span></span>](../accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="4ed89-139">Procedimiento para usar ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="4ed89-139">How to: Use the ChannelFactory</span></span>](how-to-use-the-channelfactory.md)
