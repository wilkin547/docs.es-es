---
title: El bloque de creación de administración de estado de DAPR
description: Una descripción del bloque de creación de la administración de estado, sus características, ventajas y cómo aplicarla.
author: amolenk
ms.date: 02/17/2021
ms.reviewer: robvet
ms.openlocfilehash: 67b7f839ccbe24752281fb537b0473d4984d9e37
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623933"
---
# <a name="the-dapr-state-management-building-block"></a><span data-ttu-id="56344-103">El bloque de creación de administración de estado de DAPR</span><span class="sxs-lookup"><span data-stu-id="56344-103">The Dapr state management building block</span></span>

<span data-ttu-id="56344-104">Las aplicaciones distribuidas se componen de servicios independientes.</span><span class="sxs-lookup"><span data-stu-id="56344-104">Distributed applications are composed of independent services.</span></span> <span data-ttu-id="56344-105">Aunque cada servicio no debe tener estado, algunos servicios deben hacer un seguimiento del estado para completar las operaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="56344-105">While each service should be stateless, some services must track state to complete business operations.</span></span> <span data-ttu-id="56344-106">Considere la posibilidad de usar un servicio de cesta de la compra para un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="56344-106">Consider a shopping basket service for an e-Commerce site.</span></span> <span data-ttu-id="56344-107">Si el servicio no puede realizar un seguimiento del estado, el cliente podría perder el contenido de la cesta de la compra abandonando el sitio web, lo que da lugar a una venta perdida y una experiencia descontento del cliente.</span><span class="sxs-lookup"><span data-stu-id="56344-107">If the service can't track state, the customer could loose the shopping basket content by leaving the website, resulting in a lost sale and an unhappy customer experience.</span></span> <span data-ttu-id="56344-108">En estos casos, el estado debe conservarse en un almacén de estado distribuido.</span><span class="sxs-lookup"><span data-stu-id="56344-108">For these scenarios, state needs to be persisted to a distributed state store.</span></span> <span data-ttu-id="56344-109">El [bloque de creación de administración de estado de DAPR](https://docs.dapr.io/developing-applications/building-blocks/state-management/) simplifica el seguimiento de estado y ofrece características avanzadas en varios almacenes de datos.</span><span class="sxs-lookup"><span data-stu-id="56344-109">The [Dapr state management building block](https://docs.dapr.io/developing-applications/building-blocks/state-management/) simplifies state tracking and offers advanced features across various data stores.</span></span>

<span data-ttu-id="56344-110">Para probar el bloque de creación de la administración de estado, consulte el [ejemplo de aplicación Counter en el capítulo 3](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="56344-110">To try out the state management building block, have a look at the [counter application sample in chapter 3](getting-started.md).</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="56344-111">Qué resuelve</span><span class="sxs-lookup"><span data-stu-id="56344-111">What it solves</span></span>

<span data-ttu-id="56344-112">El estado de seguimiento en una aplicación distribuida puede ser desafiante.</span><span class="sxs-lookup"><span data-stu-id="56344-112">Tracking state in a distributed application can be challenging.</span></span> <span data-ttu-id="56344-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="56344-113">For example:</span></span>

- <span data-ttu-id="56344-114">La aplicación puede requerir distintos tipos de almacenes de datos.</span><span class="sxs-lookup"><span data-stu-id="56344-114">The application may require different types of data stores.</span></span>
- <span data-ttu-id="56344-115">Pueden requerirse diferentes niveles de coherencia para obtener acceso a los datos y actualizarlos.</span><span class="sxs-lookup"><span data-stu-id="56344-115">Different consistency levels may be required for accessing and updating data.</span></span>
- <span data-ttu-id="56344-116">Varios usuarios pueden actualizar los datos al mismo tiempo, lo que requiere una resolución de conflictos.</span><span class="sxs-lookup"><span data-stu-id="56344-116">Multiple users may update data at the same time, requiring  conflict resolution.</span></span>
- <span data-ttu-id="56344-117">Los servicios deben Reintentar cualquier [error transitorio](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) de corta duración que se produzca al interactuar con el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="56344-117">Services must retry any short-lived [transient errors](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) that  occur while interacting with the data store.</span></span>

<span data-ttu-id="56344-118">El bloque de creación de administración de estado de DAPR aborda estos desafíos.</span><span class="sxs-lookup"><span data-stu-id="56344-118">The Dapr state management building block addresses these challenges.</span></span> <span data-ttu-id="56344-119">Optimiza el estado de seguimiento sin dependencias ni con una curva de aprendizaje en SDK de almacenamiento de terceros.</span><span class="sxs-lookup"><span data-stu-id="56344-119">It streamlines tracking state without dependencies or a learning curve on third-party storage SDKs.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56344-120">La administración de estado de DAPR ofrece una API de [clave/valor](/azure/architecture/guide/technology-choices/data-store-overview#keyvalue-stores) .</span><span class="sxs-lookup"><span data-stu-id="56344-120">Dapr state management offers a [key/value](/azure/architecture/guide/technology-choices/data-store-overview#keyvalue-stores) API.</span></span> <span data-ttu-id="56344-121">La característica no admite el almacenamiento de datos relacionales o de gráficos.</span><span class="sxs-lookup"><span data-stu-id="56344-121">The feature doesn't support relational or graph data storage.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="56344-122">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="56344-122">How it works</span></span>

<span data-ttu-id="56344-123">La aplicación interactúa con un sidecar de DAPR para almacenar y recuperar datos de clave/valor.</span><span class="sxs-lookup"><span data-stu-id="56344-123">The application interacts with a Dapr sidecar to store and retrieve key/value data.</span></span> <span data-ttu-id="56344-124">En el capó, la API sidecar consume un componente de almacén de estado configurable para conservar los datos.</span><span class="sxs-lookup"><span data-stu-id="56344-124">Under the hood, the sidecar API consumes a configurable state store component to persist data.</span></span> <span data-ttu-id="56344-125">Los desarrolladores pueden elegir entre una creciente colección de [almacenes de Estados compatibles](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/) que incluyen Azure Cosmos DB, SQL Server y Cassandra.</span><span class="sxs-lookup"><span data-stu-id="56344-125">Developers can choose from a growing collection of [supported state stores](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/) that include Azure Cosmos DB, SQL Server, and Cassandra.</span></span>

<span data-ttu-id="56344-126">Se puede llamar a la API con HTTP o gRPC.</span><span class="sxs-lookup"><span data-stu-id="56344-126">The API can be called with either HTTP or gRPC.</span></span> <span data-ttu-id="56344-127">Use la siguiente dirección URL para llamar a la API HTTP:</span><span class="sxs-lookup"><span data-stu-id="56344-127">Use the following URL to call the HTTP API:</span></span>

```http
http://localhost:<dapr-port>/v1.0/state/<store-name>/
```

- <span data-ttu-id="56344-128">`<dapr-port>`: el puerto HTTP en el que escucha DAPR.</span><span class="sxs-lookup"><span data-stu-id="56344-128">`<dapr-port>`: the HTTP port that Dapr listens on.</span></span>
- <span data-ttu-id="56344-129">`<store-name>`: nombre del componente de almacén de estado que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="56344-129">`<store-name>`: the name of the state store component to use.</span></span>

<span data-ttu-id="56344-130">En la figura 5-1 se muestra cómo un servicio de cesta de la compra habilitado para DAPR almacena un par clave-valor mediante el componente de almacén de estado DAPR denominado `statestore` .</span><span class="sxs-lookup"><span data-stu-id="56344-130">Figure 5-1 shows how a Dapr-enabled shopping basket service stores a key/value pair using the Dapr state store component named `statestore`.</span></span>

![Diagrama de almacenamiento de un par clave-valor en un almacén de estado de DAPR.](media/state-management/state-management-flow.png)

<span data-ttu-id="56344-132">**Figura 5-1**.</span><span class="sxs-lookup"><span data-stu-id="56344-132">**Figure 5-1**.</span></span> <span data-ttu-id="56344-133">Almacenar un par clave-valor en un almacén de estado de DAPR.</span><span class="sxs-lookup"><span data-stu-id="56344-133">Storing a key/value pair in a Dapr state store.</span></span>

<span data-ttu-id="56344-134">Tenga en cuenta los pasos de la ilustración anterior:</span><span class="sxs-lookup"><span data-stu-id="56344-134">Note the steps in the previous figure:</span></span>

1. <span data-ttu-id="56344-135">El servicio de cesta llama a la API de administración de estado en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="56344-135">The basket service calls the state management API on the Dapr sidecar.</span></span> <span data-ttu-id="56344-136">El cuerpo de la solicitud incluye una matriz JSON que puede contener varios pares clave-valor.</span><span class="sxs-lookup"><span data-stu-id="56344-136">The body of the request encloses a JSON array that can contain multiple key/value pairs.</span></span>
1. <span data-ttu-id="56344-137">El sidecar de DAPR determina el almacén de estado en función del archivo de configuración de componentes.</span><span class="sxs-lookup"><span data-stu-id="56344-137">The Dapr sidecar determines the state store based on the component configuration file.</span></span> <span data-ttu-id="56344-138">En este caso, es un almacén de estado de caché en Redis.</span><span class="sxs-lookup"><span data-stu-id="56344-138">In this case, it's a Redis cache state store.</span></span>
1. <span data-ttu-id="56344-139">El sidecar conserva los datos en la caché en Redis.</span><span class="sxs-lookup"><span data-stu-id="56344-139">The sidecar persists the data to the Redis cache.</span></span>

<span data-ttu-id="56344-140">La recuperación de los datos almacenados es una llamada de API similar.</span><span class="sxs-lookup"><span data-stu-id="56344-140">Retrieving the stored data is a similar API call.</span></span> <span data-ttu-id="56344-141">En el ejemplo siguiente, un comando de *rizo* recupera los datos mediante una llamada a la API de DAPR sidecar:</span><span class="sxs-lookup"><span data-stu-id="56344-141">In the example below, a *curl* command retrieves the data by calling the Dapr sidecar API:</span></span>

```console
curl http://localhost:3500/v1.0/state/statestore/basket1
```

<span data-ttu-id="56344-142">El comando devuelve el estado almacenado en el cuerpo de la respuesta:</span><span class="sxs-lookup"><span data-stu-id="56344-142">The command returns the stored state in the response body:</span></span>

```json
{
  "items": [
    {
      "itemId": "DaprHoodie",
      "quantity": 1
    }
  ],
  "customerId": 1
}
```

<span data-ttu-id="56344-143">En las secciones siguientes se explica cómo usar las características más avanzadas del bloque de creación de la administración de estado.</span><span class="sxs-lookup"><span data-stu-id="56344-143">The following sections explain how to use the more advanced features of the state management building block.</span></span>

### <a name="consistency"></a><span data-ttu-id="56344-144">Coherencia</span><span class="sxs-lookup"><span data-stu-id="56344-144">Consistency</span></span>

<span data-ttu-id="56344-145">El [teorema Cap](https://en.wikipedia.org/wiki/CAP_theorem) es un conjunto de principios que se aplican a los sistemas distribuidos que almacenan el estado.</span><span class="sxs-lookup"><span data-stu-id="56344-145">The [CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem) is a set of principles that apply to distributed systems that store state.</span></span> <span data-ttu-id="56344-146">En la figura 5-2 se muestran las tres propiedades del CAP teorema.</span><span class="sxs-lookup"><span data-stu-id="56344-146">Figure 5-2 shows the three properties of the CAP theorem.</span></span>

![Teorema CAP.](media/state-management/cap-theorem.png)

<span data-ttu-id="56344-148">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="56344-148">**Figure 5-2**.</span></span> <span data-ttu-id="56344-149">Teorema CAP.</span><span class="sxs-lookup"><span data-stu-id="56344-149">The CAP theorem.</span></span>

<span data-ttu-id="56344-150">Teorema indica que los sistemas de datos distribuidos ofrecen un equilibrio entre coherencia, disponibilidad y tolerancia de particiones.</span><span class="sxs-lookup"><span data-stu-id="56344-150">The theorem states that distributed data systems offer a trade-off between consistency, availability, and partition tolerance.</span></span> <span data-ttu-id="56344-151">Y, que cualquier almacén *de la propiedad solo puede garantizar dos de las tres propiedades*:</span><span class="sxs-lookup"><span data-stu-id="56344-151">And, that any datastore can only *guarantee two of the three properties*:</span></span>

- <span data-ttu-id="56344-152">*Consistency* (**C**).</span><span class="sxs-lookup"><span data-stu-id="56344-152">*Consistency* (**C**).</span></span> <span data-ttu-id="56344-153">Cada nodo del clúster responde con los datos más recientes, incluso si el sistema debe bloquear la solicitud hasta que se actualicen todas las réplicas.</span><span class="sxs-lookup"><span data-stu-id="56344-153">Every node in the cluster responds with the most recent data, even if the system must block the request until all replicas update.</span></span> <span data-ttu-id="56344-154">Si consulta un "sistema coherente" para un elemento que se está actualizando actualmente, no obtendrá una respuesta hasta que todas las réplicas se actualicen correctamente.</span><span class="sxs-lookup"><span data-stu-id="56344-154">If you query a "consistent system" for an item that is currently updating, you won't get a response until all replicas successfully update.</span></span> <span data-ttu-id="56344-155">Sin embargo, siempre recibirá los datos más actuales.</span><span class="sxs-lookup"><span data-stu-id="56344-155">However, you'll always receive the most current data.</span></span>

- <span data-ttu-id="56344-156">*Disponibilidad* (**A**).</span><span class="sxs-lookup"><span data-stu-id="56344-156">*Availability* (**A**).</span></span> <span data-ttu-id="56344-157">Cada nodo devuelve una respuesta inmediata, incluso si esa respuesta no es los datos más recientes.</span><span class="sxs-lookup"><span data-stu-id="56344-157">Every node returns an immediate response, even if that response isn't the most recent data.</span></span> <span data-ttu-id="56344-158">Si consulta un "sistema disponible" para un elemento que se está actualizando, obtendrá la mejor respuesta posible que el servicio pueda proporcionar en ese momento.</span><span class="sxs-lookup"><span data-stu-id="56344-158">If you query an "available system" for an item that is updating, you'll get the best possible answer the service can provide at that moment.</span></span>

- <span data-ttu-id="56344-159">*Tolerancia de partición* (**P**).</span><span class="sxs-lookup"><span data-stu-id="56344-159">*Partition Tolerance* (**P**).</span></span> <span data-ttu-id="56344-160">Garantiza que el sistema siga funcionando incluso si se produce un error en un nodo de datos replicado o se pierde la conectividad con otros nodos de datos replicados.</span><span class="sxs-lookup"><span data-stu-id="56344-160">Guarantees the system continues to operate even if a replicated data node fails or loses connectivity with other replicated data nodes.</span></span>

<span data-ttu-id="56344-161">Las aplicaciones distribuidas deben controlar la propiedad **P** .</span><span class="sxs-lookup"><span data-stu-id="56344-161">Distributed applications must handle the **P** property.</span></span> <span data-ttu-id="56344-162">A medida que los servicios se comunican entre sí con llamadas de red, se producirá una interrupción de la red (**P**).</span><span class="sxs-lookup"><span data-stu-id="56344-162">As services communicate among each other with network calls, network disruptions (**P**) will occur.</span></span> <span data-ttu-id="56344-163">Teniendo esto en cuenta, las aplicaciones distribuidas deben ser de tipo **AP** o **CP**.</span><span class="sxs-lookup"><span data-stu-id="56344-163">With that in mind, distributed applications must either be **AP** or **CP**.</span></span>

<span data-ttu-id="56344-164">Las aplicaciones de **AP** eligen la disponibilidad a través de la coherencia.</span><span class="sxs-lookup"><span data-stu-id="56344-164">**AP** applications choose availability over consistency.</span></span> <span data-ttu-id="56344-165">DAPR admite esta opción con su estrategia de **coherencia eventual** .</span><span class="sxs-lookup"><span data-stu-id="56344-165">Dapr supports this choice with its **eventual consistency** strategy.</span></span> <span data-ttu-id="56344-166">Considere la posibilidad de un almacén de datos subyacente, como Azure CosmosDB, que almacena datos redundantes en varias réplicas.</span><span class="sxs-lookup"><span data-stu-id="56344-166">Consider an underlying data store, such as Azure CosmosDB, which stores redundant data on multiple replicas.</span></span> <span data-ttu-id="56344-167">Con coherencia final, el almacén de estado escribe la actualización en una réplica y completa la solicitud de escritura con el cliente.</span><span class="sxs-lookup"><span data-stu-id="56344-167">With eventual consistency, the state store writes the update to one replica and completes the write request with the client.</span></span> <span data-ttu-id="56344-168">Después de este tiempo, el almacén actualizará de forma asincrónica sus réplicas.</span><span class="sxs-lookup"><span data-stu-id="56344-168">After this time, the store will asynchronously update its replicas.</span></span> <span data-ttu-id="56344-169">Las solicitudes de lectura pueden devolver datos de cualquiera de las réplicas, incluidas las réplicas que aún no han recibido la actualización más reciente.</span><span class="sxs-lookup"><span data-stu-id="56344-169">Read requests can return data from any of the replicas, including those replicas that haven't yet received the latest update.</span></span>

<span data-ttu-id="56344-170">Las aplicaciones de **CP** eligen la coherencia con respecto a la disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="56344-170">**CP** applications choose consistency over availability.</span></span> <span data-ttu-id="56344-171">DAPR admite esta opción con su estrategia de **coherencia fuerte** .</span><span class="sxs-lookup"><span data-stu-id="56344-171">Dapr supports this choice with its **strong consistency** strategy.</span></span> <span data-ttu-id="56344-172">En este escenario, el almacén de estado actualizará de forma sincrónica *todos* (o, en algunos casos, un *cuórum* de) las réplicas necesarias *antes* de completar la solicitud de escritura.</span><span class="sxs-lookup"><span data-stu-id="56344-172">In this scenario, the state store will synchronously update *all* (or, in some cases, a *quorum* of) required replicas *before* completing the write request.</span></span> <span data-ttu-id="56344-173">Las operaciones de lectura devolverán los datos más actualizados de forma coherente en las réplicas.</span><span class="sxs-lookup"><span data-stu-id="56344-173">Read operations will return the most up-to-date data consistently across replicas.</span></span>

<span data-ttu-id="56344-174">El nivel de coherencia de una operación de estado se especifica mediante la Asociación de una *sugerencia de coherencia* a la operación.</span><span class="sxs-lookup"><span data-stu-id="56344-174">The consistency level for a state operation is specified by attaching a *consistency hint* to the operation.</span></span> <span data-ttu-id="56344-175">El siguiente comando de *rizo* escribe un `Hello=World` par clave-valor en un almacén de estado mediante una sugerencia de coherencia fuerte:</span><span class="sxs-lookup"><span data-stu-id="56344-175">The following *curl* command writes a `Hello=World` key/value pair to a state store using a strong consistency hint:</span></span>

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name> \
  -H "Content-Type: application/json" \
  -d '[
        {
          "key": "Hello",
          "value": "World",
          "options": {
            "consistency": "strong"
          }
        }
      ]'
```

> [!IMPORTANT]
> <span data-ttu-id="56344-176">Depende del componente de almacén de estado de DAPR para satisfacer la sugerencia de coherencia asociada a la operación.</span><span class="sxs-lookup"><span data-stu-id="56344-176">It is up to the Dapr state store component to fulfill the consistency hint attached to the operation.</span></span> <span data-ttu-id="56344-177">No todos los almacenes de datos admiten ambos niveles de coherencia.</span><span class="sxs-lookup"><span data-stu-id="56344-177">Not all data stores support both consistency levels.</span></span> <span data-ttu-id="56344-178">Si no se establece ninguna sugerencia de coherencia, el comportamiento predeterminado es **eventual**.</span><span class="sxs-lookup"><span data-stu-id="56344-178">If no consistency hint is set, the default behavior is **eventual**.</span></span>

### <a name="concurrency"></a><span data-ttu-id="56344-179">Simultaneidad</span><span class="sxs-lookup"><span data-stu-id="56344-179">Concurrency</span></span>

<span data-ttu-id="56344-180">En una aplicación de varios usuarios, existe la posibilidad de que varios usuarios actualicen los mismos datos simultáneamente (al mismo tiempo).</span><span class="sxs-lookup"><span data-stu-id="56344-180">In a multi-user application, there's a chance that multiple users will update the same data concurrently (at the same time).</span></span> <span data-ttu-id="56344-181">DAPR admite el control de simultaneidad optimista (OCC) para administrar los conflictos.</span><span class="sxs-lookup"><span data-stu-id="56344-181">Dapr supports optimistic concurrency control (OCC) to manage conflicts.</span></span> <span data-ttu-id="56344-182">OCC se basa en una suposición de que los conflictos de actualización son infrecuentes, ya que los usuarios trabajan en diferentes partes de los datos.</span><span class="sxs-lookup"><span data-stu-id="56344-182">OCC is based on an assumption that update conflicts are uncommon because users work on different parts of the data.</span></span> <span data-ttu-id="56344-183">Es más eficaz suponer que una actualización se realizará correctamente y volverá a intentarlo si no lo hace.</span><span class="sxs-lookup"><span data-stu-id="56344-183">It's more efficient to assume an update will succeed and retry if it doesn't.</span></span> <span data-ttu-id="56344-184">La alternativa, implementar el bloqueo pesimista, puede afectar al rendimiento con el bloqueo de ejecución prolongada que produce la contención de datos.</span><span class="sxs-lookup"><span data-stu-id="56344-184">The alternative, implementing pessimistic locking, can affect performance with long-running locking causing data contention.</span></span>

<span data-ttu-id="56344-185">DAPR admite el control de simultaneidad optimista (OCC) mediante ETags.</span><span class="sxs-lookup"><span data-stu-id="56344-185">Dapr supports optimistic concurrency control (OCC) using ETags.</span></span> <span data-ttu-id="56344-186">Una ETag es un valor asociado a una versión específica de un par clave-valor almacenado.</span><span class="sxs-lookup"><span data-stu-id="56344-186">An ETag is a value associated with a specific version of a stored key/value pair.</span></span> <span data-ttu-id="56344-187">Cada vez que se actualiza un par clave-valor, el valor ETag también se actualiza.</span><span class="sxs-lookup"><span data-stu-id="56344-187">Each time a key/value pair updates, the ETag value updates as well.</span></span> <span data-ttu-id="56344-188">Cuando un cliente recupera un par clave-valor, la respuesta incluye el valor ETag actual.</span><span class="sxs-lookup"><span data-stu-id="56344-188">When a client retrieves a key/value pair, the response includes the current ETag value.</span></span> <span data-ttu-id="56344-189">Cuando un cliente actualiza o elimina un par clave-valor, debe devolver el valor de ETag en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="56344-189">When a client updates or deletes a key/value pair, it must send that ETag value back in the request body.</span></span> <span data-ttu-id="56344-190">Si otro cliente ha actualizado los datos mientras tanto, el ETags no coincidirá y se producirá un error en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="56344-190">If another client has updated the data in the meantime, the ETags won't match and the request will fail.</span></span> <span data-ttu-id="56344-191">En este momento, el cliente debe recuperar los datos actualizados, volver a realizar el cambio y volver a enviar la actualización.</span><span class="sxs-lookup"><span data-stu-id="56344-191">At this point, the client must retrieve the updated data, make the change again, and resubmit the update.</span></span> <span data-ttu-id="56344-192">Esta estrategia se denomina **First-Write-WINS**.</span><span class="sxs-lookup"><span data-stu-id="56344-192">This strategy is called **first-write-wins**.</span></span>

<span data-ttu-id="56344-193">DAPR también admite una estrategia de **última escritura-WINS** .</span><span class="sxs-lookup"><span data-stu-id="56344-193">Dapr also supports a **last-write-wins** strategy.</span></span> <span data-ttu-id="56344-194">Con este enfoque, el cliente no adjunta un ETag a la solicitud de escritura.</span><span class="sxs-lookup"><span data-stu-id="56344-194">With this approach, the client doesn't attach an ETag to the write request.</span></span> <span data-ttu-id="56344-195">El componente almacén de estado siempre permitirá la actualización, incluso si el valor subyacente ha cambiado durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="56344-195">The state store component will always allow the update, even if the underlying value has changed during the session.</span></span> <span data-ttu-id="56344-196">Last-Write-WINS es útil para escenarios de escritura de alto rendimiento con poca contención de datos.</span><span class="sxs-lookup"><span data-stu-id="56344-196">Last-write-wins is useful for high-throughput write scenarios with low data contention.</span></span> <span data-ttu-id="56344-197">Además, se puede tolerar la sobrescritura de una actualización de usuario ocasional.</span><span class="sxs-lookup"><span data-stu-id="56344-197">As well, overwriting an occasional user update can be tolerated.</span></span>

### <a name="transactions"></a><span data-ttu-id="56344-198">Transacciones</span><span class="sxs-lookup"><span data-stu-id="56344-198">Transactions</span></span>

<span data-ttu-id="56344-199">DAPR puede escribir *cambios de varios elementos* en un almacén de datos como una operación única implementada como una transacción.</span><span class="sxs-lookup"><span data-stu-id="56344-199">Dapr can write *multi-item changes* to a data store as a single operation implemented as a transaction.</span></span> <span data-ttu-id="56344-200">Esta funcionalidad solo está disponible para los almacenes de datos que admiten transacciones [acid](https://en.wikipedia.org/wiki/ACID) .</span><span class="sxs-lookup"><span data-stu-id="56344-200">This functionality is only available for data stores that support [ACID](https://en.wikipedia.org/wiki/ACID) transactions.</span></span> <span data-ttu-id="56344-201">En el momento de redactar este documento, estos almacenes incluyen Redis, MongoDB, PostgreSQL, SQL Server y Azure CosmosDB.</span><span class="sxs-lookup"><span data-stu-id="56344-201">At the time of this writing, these stores include Redis, MongoDB, PostgreSQL, SQL Server, and Azure CosmosDB.</span></span>

<span data-ttu-id="56344-202">En el ejemplo siguiente, se envía una operación de varios elementos al almacén de estado en una única transacción.</span><span class="sxs-lookup"><span data-stu-id="56344-202">In the example below, a multi-item operation is sent to the state store in a single transaction.</span></span> <span data-ttu-id="56344-203">Todas las operaciones deben realizarse correctamente para que la transacción se confirme.</span><span class="sxs-lookup"><span data-stu-id="56344-203">All operations must succeed for the transaction to commit.</span></span> <span data-ttu-id="56344-204">Si se produce un error en una o varias de las operaciones, se revierte toda la transacción.</span><span class="sxs-lookup"><span data-stu-id="56344-204">If one or more of the operations fail, the entire transaction rolls back.</span></span>

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name>/transaction \
  -H "Content-Type: application/json" \
  -d '{
        "operations": [
          {
            "operation": "upsert",
            "request": { "key": "Key1", "value": "Value1"
            }
          },
          {
            "operation": "delete",
            "request": { "key": "Key2" }
          }
        ]
      }'
```

<span data-ttu-id="56344-205">En el caso de los almacenes de datos que no admiten transacciones, se pueden enviar varias claves como una única solicitud.</span><span class="sxs-lookup"><span data-stu-id="56344-205">For data stores that don't support transactions, multiple keys can still be sent as a single request.</span></span> <span data-ttu-id="56344-206">En el ejemplo siguiente se muestra una operación de escritura **masiva** :</span><span class="sxs-lookup"><span data-stu-id="56344-206">The following example shows a **bulk** write operation:</span></span>

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name> \
  -H "Content-Type: application/json" \
  -d '[
        { "key": "Key1", "value": "Value1" },
        { "key": "Key2", "value": "Value2" }
      ]'
```

<span data-ttu-id="56344-207">En el caso de las operaciones masivas, DAPR enviará cada actualización del par clave-valor como una solicitud independiente al almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="56344-207">For bulk operations, Dapr will submit each key/value pair update as a separate request to the data store.</span></span>

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="56344-208">Uso del SDK de .NET para DAPR</span><span class="sxs-lookup"><span data-stu-id="56344-208">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="56344-209">El SDK de .NET para DAPR proporciona compatibilidad específica del lenguaje para la plataforma .NET Core.</span><span class="sxs-lookup"><span data-stu-id="56344-209">The Dapr .NET SDK provides language-specific support for .NET Core platform.</span></span> <span data-ttu-id="56344-210">Los desarrolladores pueden usar la `DaprClient` clase presentada en el [capítulo 3](getting-started.md) para leer y escribir datos.</span><span class="sxs-lookup"><span data-stu-id="56344-210">Developers can use the `DaprClient` class introduced in [chapter 3](getting-started.md) to read and write data.</span></span> <span data-ttu-id="56344-211">En el ejemplo siguiente se muestra cómo utilizar el `DaprClient.GetStateAsync<TValue>` método para leer los datos de un almacén de estado.</span><span class="sxs-lookup"><span data-stu-id="56344-211">The following example shows how to use the `DaprClient.GetStateAsync<TValue>` method to read data from a state store.</span></span> <span data-ttu-id="56344-212">El método espera el nombre de almacén, `statestore` , y la clave, `AMS` , como parámetros:</span><span class="sxs-lookup"><span data-stu-id="56344-212">The method expects the store name, `statestore`, and key, `AMS`, as parameters:</span></span>

```csharp
var weatherForecast = await daprClient.GetStateAsync<WeatherForecast>("statestore", "AMS");
```

<span data-ttu-id="56344-213">Si el almacén de estado no contiene ningún dato para `AMS` la clave, el resultado será `default(WeatherForecast)` .</span><span class="sxs-lookup"><span data-stu-id="56344-213">If the state store contains no data for key `AMS`, the result will be `default(WeatherForecast)`.</span></span>

<span data-ttu-id="56344-214">Para escribir datos en el almacén de datos, use el `DaprClient.SaveStateAsync<TValue>` método:</span><span class="sxs-lookup"><span data-stu-id="56344-214">To write data to the data store, use the `DaprClient.SaveStateAsync<TValue>` method:</span></span>

```csharp
daprClient.SaveStateAsync("statestore", "AMS", weatherForecast);
```

<span data-ttu-id="56344-215">En el ejemplo se usa la estrategia **Last-Write-WINS** , ya que no se pasa un valor ETag al componente almacén de estado.</span><span class="sxs-lookup"><span data-stu-id="56344-215">The example uses the **last-write-wins** strategy as an ETag value isn't passed to the state store component.</span></span> <span data-ttu-id="56344-216">Para usar el control de simultaneidad optimista (OCC) con una estrategia **First-Write-WINS** , primero recupere el ETag actual mediante el `DaprClient.GetStateAndETagAsync` método.</span><span class="sxs-lookup"><span data-stu-id="56344-216">To use optimistic concurrency control (OCC) with a **first-write-wins** strategy, first retrieve the current ETag using the `DaprClient.GetStateAndETagAsync` method.</span></span> <span data-ttu-id="56344-217">A continuación, escriba el valor actualizado y pase a lo largo de la ETag recuperada mediante el `DaprClient.TrySaveStateAsync` método.</span><span class="sxs-lookup"><span data-stu-id="56344-217">Then write the updated value and pass along the retrieved ETag using the `DaprClient.TrySaveStateAsync` method.</span></span>

```csharp
var (weatherForecast, etag) = await daprClient.GetStateAndETagAsync<WeatherForecast>("statestore", city);

// ... make some changes to the retrieved weather forecast

var result = await daprClient.TrySaveStateAsync("statestore", city, weatherForecast, etag);
```

<span data-ttu-id="56344-218">El `DaprClient.TrySaveStateAsync` método genera un error cuando se han cambiado los datos (y la ETag asociada) en el almacén de estado después de recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="56344-218">The `DaprClient.TrySaveStateAsync` method fails when the data (and associated ETag) has been changed in the state store after the data was retrieved.</span></span> <span data-ttu-id="56344-219">El método devuelve un valor booleano para indicar si la llamada se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="56344-219">The method returns a boolean value to indicate whether the call succeeded.</span></span> <span data-ttu-id="56344-220">Una estrategia para controlar el error es simplemente volver a cargar los datos actualizados desde el almacén de estado, realizar el cambio de nuevo y volver a enviar la actualización.</span><span class="sxs-lookup"><span data-stu-id="56344-220">A strategy to handle the failure is to simply reload the updated data from the state store, make the change again, and resubmit the update.</span></span>

<span data-ttu-id="56344-221">Si siempre desea que una escritura se realice correctamente independientemente de otros cambios en los datos, use la estrategia **Last-Write-WINS** .</span><span class="sxs-lookup"><span data-stu-id="56344-221">If you always want a write to succeed regardless of other changes to the data, use the **last-write-wins** strategy.</span></span>

<span data-ttu-id="56344-222">El SDK proporciona otros métodos para recuperar datos en masa, eliminar datos y ejecutar transacciones.</span><span class="sxs-lookup"><span data-stu-id="56344-222">The SDK provides other methods to retrieve data in bulk, delete data, and execute transactions.</span></span> <span data-ttu-id="56344-223">Para obtener más información, vea el [repositorio del SDK de .net de DAPR](https://github.com/dapr/dotnet-sdk).</span><span class="sxs-lookup"><span data-stu-id="56344-223">For more information, see the [Dapr .NET SDK repository](https://github.com/dapr/dotnet-sdk).</span></span>

### <a name="aspnet-core-integration"></a><span data-ttu-id="56344-224">Integración de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="56344-224">ASP.NET Core integration</span></span>

<span data-ttu-id="56344-225">DAPR también admite ASP.NET Core, un marco multiplataforma para compilar modernas aplicaciones web basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="56344-225">Dapr also supports ASP.NET Core, a cross-platform framework for building modern cloud-based web applications.</span></span> <span data-ttu-id="56344-226">El SDK de DAPR integra las capacidades de administración de estado directamente en las capacidades de [enlace del modelo de ASP.net Core](/aspnet/core/mvc/models/model-binding) .</span><span class="sxs-lookup"><span data-stu-id="56344-226">The Dapr SDK integrates state management capabilities directly into the [ASP.NET Core model binding](/aspnet/core/mvc/models/model-binding) capabilities.</span></span> <span data-ttu-id="56344-227">La configuración es sencilla.</span><span class="sxs-lookup"><span data-stu-id="56344-227">Configuration is simple.</span></span> <span data-ttu-id="56344-228">Agregue el `IMVCBuilder.AddDapr` anexando el `.AddDapr` método de extensión en la `Startup.cs` clase tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56344-228">Add the `IMVCBuilder.AddDapr` by appending the `.AddDapr` extension method in your `Startup.cs` class as shown in the next example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddControllers().AddDapr();
}
```

<span data-ttu-id="56344-229">Una vez configurado, DAPR puede inyectar un par clave-valor directamente en una acción del controlador mediante el `FromState` atributo ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="56344-229">Once configured, Dapr can inject a key/value pair directly into a controller action using the ASP.NET Core `FromState` attribute.</span></span> <span data-ttu-id="56344-230">Ya no es necesario hacer referencia al `DaprClient` objeto.</span><span class="sxs-lookup"><span data-stu-id="56344-230">Referencing the `DaprClient` object is no longer necessary.</span></span> <span data-ttu-id="56344-231">En el ejemplo siguiente se muestra una API Web que devuelve el Pronóstico meteorológico de una ciudad determinada:</span><span class="sxs-lookup"><span data-stu-id="56344-231">The next example shows a Web API that returns the weather forecast for a given city:</span></span>

```csharp
[HttpGet("{city}")]
public ActionResult<WeatherForecast> Get([FromState("statestore", "city")] StateEntry<WeatherForecast> forecast)
{
    if (forecast.Value == null)
    {
      return NotFound();
    }

    return forecast.Value;
}
```

<span data-ttu-id="56344-232">En el ejemplo, el controlador carga la previsión meteorológica mediante el `FromState` atributo.</span><span class="sxs-lookup"><span data-stu-id="56344-232">In the example, the controller loads the weather forecast using the `FromState` attribute.</span></span> <span data-ttu-id="56344-233">El primer parámetro de atributo es el almacén de estado, `statestore` .</span><span class="sxs-lookup"><span data-stu-id="56344-233">The first attribute parameter is the state store, `statestore`.</span></span> <span data-ttu-id="56344-234">El segundo parámetro de atributo, `city` , es el nombre de la variable de [plantilla de ruta](/aspnet/core/mvc/controllers/routing#route-templates) para obtener la clave de estado.</span><span class="sxs-lookup"><span data-stu-id="56344-234">The second attribute parameter, `city`, is the name of the [route template](/aspnet/core/mvc/controllers/routing#route-templates) variable to get the state key.</span></span> <span data-ttu-id="56344-235">Si omite el segundo parámetro, se usa el nombre del parámetro de método enlazado ( `forecast` ) para buscar la variable de plantilla de ruta.</span><span class="sxs-lookup"><span data-stu-id="56344-235">If you omit the second parameter, the name of the bound method parameter (`forecast`) is used to look up the route template variable.</span></span>

<span data-ttu-id="56344-236">La `StateEntry` clase contiene las propiedades de toda la información que se recupera para un par clave-valor único: `StoreName` , `Key` , `Value` y `ETag` .</span><span class="sxs-lookup"><span data-stu-id="56344-236">The `StateEntry` class contains properties for all the information that is retrieved for a single key/value pair: `StoreName`, `Key`, `Value`, and `ETag`.</span></span> <span data-ttu-id="56344-237">La ETag es útil para implementar la estrategia de control de simultaneidad optimista (OCC).</span><span class="sxs-lookup"><span data-stu-id="56344-237">The ETag is useful for implementing optimistic concurrency control (OCC) strategy.</span></span> <span data-ttu-id="56344-238">La clase también proporciona métodos para eliminar o actualizar los datos de clave y valor recuperados sin necesidad de una `DaprClient` instancia de.</span><span class="sxs-lookup"><span data-stu-id="56344-238">The class also provides methods to delete or update retrieved key/value data without requiring a `DaprClient` instance.</span></span> <span data-ttu-id="56344-239">En el ejemplo siguiente, el `TrySaveAsync` método se utiliza para actualizar la previsión meteorológica recuperada mediante OCC.</span><span class="sxs-lookup"><span data-stu-id="56344-239">In the next example, the `TrySaveAsync` method is used to update the retrieved weather forecast using OCC.</span></span>

```csharp
[HttpPut("{city}")]
public async Task Put(WeatherForecast updatedForecast, [FromState("statestore", "city")] StateEntry<WeatherForecast> currentForecast)
{
    // update cached current forecast with updated forecast passed into service endpoint
    currentForecast.Value = updatedForecast;

    // update state store
    var success = await currentForecast.TrySaveAsync();

    // ... check result
}
```

## <a name="state-store-components"></a><span data-ttu-id="56344-240">Componentes del almacén de estado</span><span class="sxs-lookup"><span data-stu-id="56344-240">State store components</span></span>

<span data-ttu-id="56344-241">En el momento de redactar este documento, DAPR proporciona compatibilidad para los siguientes almacenes de estado transaccionales:</span><span class="sxs-lookup"><span data-stu-id="56344-241">At the time of this writing, Dapr provides support for the following transactional state stores:</span></span>

- <span data-ttu-id="56344-242">Azure CosmosDB</span><span class="sxs-lookup"><span data-stu-id="56344-242">Azure CosmosDB</span></span>
- <span data-ttu-id="56344-243">Azure SQL Server</span><span class="sxs-lookup"><span data-stu-id="56344-243">Azure SQL Server</span></span>
- <span data-ttu-id="56344-244">MongoDB</span><span class="sxs-lookup"><span data-stu-id="56344-244">MongoDB</span></span>
- <span data-ttu-id="56344-245">PostgreSQL</span><span class="sxs-lookup"><span data-stu-id="56344-245">PostgreSQL</span></span>
- <span data-ttu-id="56344-246">Redis</span><span class="sxs-lookup"><span data-stu-id="56344-246">Redis</span></span>

<span data-ttu-id="56344-247">DAPR también incluye compatibilidad con almacenes de estado que admiten operaciones CRUD, pero no capacidades transaccionales:</span><span class="sxs-lookup"><span data-stu-id="56344-247">Dapr also includes support for state stores that support CRUD operations, but not transactional capabilities:</span></span>

- <span data-ttu-id="56344-248">Aerospike</span><span class="sxs-lookup"><span data-stu-id="56344-248">Aerospike</span></span>
- <span data-ttu-id="56344-249">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="56344-249">Azure Blob Storage</span></span>
- <span data-ttu-id="56344-250">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="56344-250">Azure Table Storage</span></span>
- <span data-ttu-id="56344-251">Cassandra</span><span class="sxs-lookup"><span data-stu-id="56344-251">Cassandra</span></span>
- <span data-ttu-id="56344-252">Cloudstate</span><span class="sxs-lookup"><span data-stu-id="56344-252">Cloudstate</span></span>
- <span data-ttu-id="56344-253">Couchbase</span><span class="sxs-lookup"><span data-stu-id="56344-253">Couchbase</span></span>
- <span data-ttu-id="56344-254">etcd</span><span class="sxs-lookup"><span data-stu-id="56344-254">etcd</span></span>
- <span data-ttu-id="56344-255">Google Cloud FireStore</span><span class="sxs-lookup"><span data-stu-id="56344-255">Google Cloud Firestore</span></span>
- <span data-ttu-id="56344-256">Hashicorp Consul</span><span class="sxs-lookup"><span data-stu-id="56344-256">Hashicorp Consul</span></span>
- <span data-ttu-id="56344-257">Hazelcast</span><span class="sxs-lookup"><span data-stu-id="56344-257">Hazelcast</span></span>
- <span data-ttu-id="56344-258">Memcached</span><span class="sxs-lookup"><span data-stu-id="56344-258">Memcached</span></span>
- <span data-ttu-id="56344-259">Zookeeper</span><span class="sxs-lookup"><span data-stu-id="56344-259">Zookeeper</span></span>

### <a name="configuration"></a><span data-ttu-id="56344-260">Configuración</span><span class="sxs-lookup"><span data-stu-id="56344-260">Configuration</span></span>

<span data-ttu-id="56344-261">Cuando se inicializa para el desarrollo local y autohospedado, DAPR registra Redis como el almacén de estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="56344-261">When initialized for local, self-hosted development, Dapr registers Redis as the default state store.</span></span> <span data-ttu-id="56344-262">Este es un ejemplo de la configuración predeterminada del almacén de estado.</span><span class="sxs-lookup"><span data-stu-id="56344-262">Here's an example of the default state store configuration.</span></span> <span data-ttu-id="56344-263">Anote el nombre predeterminado, `statestore` :</span><span class="sxs-lookup"><span data-stu-id="56344-263">Note the default name, `statestore`:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
```

 > [!NOTE]
 > <span data-ttu-id="56344-264">Muchos almacenes de Estados se pueden registrar en una sola aplicación con un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="56344-264">Many state stores can be registered to a single application each with a different name.</span></span>

<span data-ttu-id="56344-265">El almacén de estado de Redis requiere los `redisHost` `redisPassword` metadatos y para conectarse a la instancia de Redis.</span><span class="sxs-lookup"><span data-stu-id="56344-265">The Redis state store requires `redisHost` and `redisPassword` metadata to connect to the Redis instance.</span></span> <span data-ttu-id="56344-266">En el ejemplo anterior, la contraseña de REDIS (que es una cadena vacía de forma predeterminada) se almacena como una cadena sin formato.</span><span class="sxs-lookup"><span data-stu-id="56344-266">In the example above, the Redis password (which is an empty string by default) is stored as a plain string.</span></span> <span data-ttu-id="56344-267">El procedimiento recomendado es evitar cadenas de texto no cifrado y usar siempre referencias secretas.</span><span class="sxs-lookup"><span data-stu-id="56344-267">The best practice is to avoid clear-text strings and always use secret references.</span></span> <span data-ttu-id="56344-268">Para obtener más información acerca de la administración de secretos, consulte el [capítulo 10](secrets.md).</span><span class="sxs-lookup"><span data-stu-id="56344-268">To learn more about secret management, see [chapter 10](secrets.md).</span></span>

<span data-ttu-id="56344-269">El otro campo de metadatos, `actorStateStore` , indica si el almacén de estado puede ser utilizado por el bloque de creación de actores.</span><span class="sxs-lookup"><span data-stu-id="56344-269">The other metadata field, `actorStateStore`, indicates whether the state store can be consumed by the actors building block.</span></span>

### <a name="key-prefix-strategies"></a><span data-ttu-id="56344-270">Estrategias de prefijo de clave</span><span class="sxs-lookup"><span data-stu-id="56344-270">Key prefix strategies</span></span>

<span data-ttu-id="56344-271">Los componentes del almacén de estado permiten diferentes estrategias para almacenar pares clave-valor en el almacén subyacente.</span><span class="sxs-lookup"><span data-stu-id="56344-271">State store components enable different strategies to store key/value pairs in the underlying store.</span></span> <span data-ttu-id="56344-272">Recuerde el ejemplo anterior de un servicio de cesta de la compra que almacena los artículos que un cliente desea comprar:</span><span class="sxs-lookup"><span data-stu-id="56344-272">Recall the earlier example of a shopping basket service storing items a customer wishes to purchase:</span></span>

```console
curl -X POST http://localhost:3500/v1.0/state/statestore \
  -H "Content-Type: application/json" \
  -d '[{
        "key": "basket1",
        "value": {
          "customerId": 1,
          "items": [
            { "itemId": "DaprHoodie", "quantity": 1 }
          ]
        }
     }]'
```

<span data-ttu-id="56344-273">Con la herramienta de la consola de Redis, mire dentro de la caché en Redis para ver cómo el componente del almacén de estado de Redis conserva los datos:</span><span class="sxs-lookup"><span data-stu-id="56344-273">Using the Redis Console tool, look inside the Redis cache to see how the Redis state store component persisted the data:</span></span>

```
127.0.0.1:6379> KEYS *
1) "basketservice||basket1"

127.0.0.1:6379> HGETALL basketservice||basket1
1) "data"
2) "{\"items\":[{\"itemId\":\"DaprHoodie\",\"quantity\":1}],\"customerId\":1}"
3) "version"
4) "1"
```

<span data-ttu-id="56344-274">La salida muestra la **clave** de Redis completa de los datos como `basketservice||basket1` .</span><span class="sxs-lookup"><span data-stu-id="56344-274">The output shows the full Redis **key** for the data as `basketservice||basket1`.</span></span> <span data-ttu-id="56344-275">De forma predeterminada, DAPR usa la `application id` de la instancia de DAPR ( `basketservice` ) como prefijo para la clave.</span><span class="sxs-lookup"><span data-stu-id="56344-275">By default, Dapr uses the `application id` of the Dapr instance (`basketservice`) as a prefix for the key.</span></span> <span data-ttu-id="56344-276">Esta Convención de nomenclatura permite que varias instancias de DAPR compartan el mismo almacén de datos sin colisiones de nombre de clave.</span><span class="sxs-lookup"><span data-stu-id="56344-276">This naming convention enables multiple Dapr instances to share the same data store without key name collisions.</span></span> <span data-ttu-id="56344-277">En el caso del desarrollador, es importante especificar siempre el mismo `application id` cuando se ejecuta la aplicación con DAPR.</span><span class="sxs-lookup"><span data-stu-id="56344-277">For the developer, it's critical always to specify the same `application id` when running the application with Dapr.</span></span> <span data-ttu-id="56344-278">Si se omite, DAPR generará un identificador de aplicación único.</span><span class="sxs-lookup"><span data-stu-id="56344-278">If omitted, Dapr will generate a unique application ID.</span></span> <span data-ttu-id="56344-279">Si `application id` cambia, la aplicación ya no puede tener acceso al estado almacenado con el prefijo de clave anterior.</span><span class="sxs-lookup"><span data-stu-id="56344-279">If the `application id` changes, the application can no longer access the state stored with the previous key prefix.</span></span>

<span data-ttu-id="56344-280">Dicho esto, es posible configurar un *valor constante* para el prefijo de clave en el `keyPrefix` campo de metadatos del archivo de componente del almacén de estado.</span><span class="sxs-lookup"><span data-stu-id="56344-280">That said, it's possible to configure a *constant value* for the key prefix in the `keyPrefix` metadata field in the state store component file.</span></span> <span data-ttu-id="56344-281">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56344-281">Consider the following example:</span></span>

```yaml
spec:
  metadata:
  - name: keyPrefix
  - value: MyPrefix
```

<span data-ttu-id="56344-282">Un prefijo de clave constante permite el acceso al almacén de estado a través de varias aplicaciones DAPR.</span><span class="sxs-lookup"><span data-stu-id="56344-282">A constant key prefix enables the state store to be accessed across multiple Dapr applications.</span></span> <span data-ttu-id="56344-283">Lo que es más, si `keyPrefix` se establece en, se `none` omite por completo el prefijo.</span><span class="sxs-lookup"><span data-stu-id="56344-283">What's more, setting the `keyPrefix` to `none` omits the prefix completely.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="56344-284">Aplicación de referencia: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="56344-284">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="56344-285">Este libro incluye una aplicación de referencia titulada `eShopOnDapr` .</span><span class="sxs-lookup"><span data-stu-id="56344-285">This book includes a reference application entitled `eShopOnDapr`.</span></span> <span data-ttu-id="56344-286">Se modela a partir de una aplicación de referencia de microservicios de Microsoft anterior, `eShopOnContainers` .</span><span class="sxs-lookup"><span data-stu-id="56344-286">It's modeled from an earlier Microsoft microservices reference application, `eShopOnContainers`.</span></span>

<span data-ttu-id="56344-287">La arquitectura [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) original usaba una `IBasketRepository` interfaz para leer y escribir datos para el servicio de la cesta.</span><span class="sxs-lookup"><span data-stu-id="56344-287">The original [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) architecture used an `IBasketRepository` interface to read and write data for the basket service.</span></span> <span data-ttu-id="56344-288">La `RedisBasketRepository` clase proporcionó la implementación mediante Redis como almacén de datos subyacente:</span><span class="sxs-lookup"><span data-stu-id="56344-288">The `RedisBasketRepository` class provided the implementation using Redis as the underlying data store:</span></span>

```csharp
public class RedisBasketRepository : IBasketRepository
{
    private readonly ConnectionMultiplexer _redis;
    private readonly IDatabase _database;

    public RedisBasketRepository(ConnectionMultiplexer redis)
    {
        _redis = redis;
        _database = redis.GetDatabase();
    }

    public async Task<CustomerBasket> GetBasketAsync(string customerId)
    {
        var data = await _database.StringGetAsync(customerId);

        if (data.IsNullOrEmpty)
        {
            return null;
        }

        return JsonConvert.DeserializeObject<CustomerBasket>(data);
    }

    // ...
}
```

<span data-ttu-id="56344-289">Este código utiliza el paquete de NuGet de terceros `StackExchange.Redis` .</span><span class="sxs-lookup"><span data-stu-id="56344-289">This code uses the third-party `StackExchange.Redis` NuGet package.</span></span> <span data-ttu-id="56344-290">Los pasos siguientes son necesarios para cargar la cesta de la compra de un cliente determinado:</span><span class="sxs-lookup"><span data-stu-id="56344-290">The following steps are required to load the shopping basket for a given customer:</span></span>

1. <span data-ttu-id="56344-291">Inserte un `ConnectionMultiplexer` en el constructor.</span><span class="sxs-lookup"><span data-stu-id="56344-291">Inject a `ConnectionMultiplexer` into the constructor.</span></span> <span data-ttu-id="56344-292">`ConnectionMultiplexer`Se registra con el marco de inserción de dependencias en el `Startup.cs` archivo:</span><span class="sxs-lookup"><span data-stu-id="56344-292">The `ConnectionMultiplexer` is registered with the dependency injection framework in the `Startup.cs` file:</span></span>

   ```csharp
   services.AddSingleton<ConnectionMultiplexer>(sp =>
   {
       var settings = sp.GetRequiredService<IOptions<BasketSettings>>().Value;
       var configuration = ConfigurationOptions.Parse(settings.ConnectionString, true);
       configuration.ResolveDns = true;
       return ConnectionMultiplexer.Connect(configuration);
   });
   ```

1. <span data-ttu-id="56344-293">Utilice `ConnectionMultiplexer` para crear una `IDatabase` instancia de en cada clase de consumo.</span><span class="sxs-lookup"><span data-stu-id="56344-293">Use the `ConnectionMultiplexer` to create an `IDatabase` instance in each consuming class.</span></span>

1. <span data-ttu-id="56344-294">Use la `IDatabase` instancia de para ejecutar una llamada StringGet de Redis usando el especificado `customerId` como clave.</span><span class="sxs-lookup"><span data-stu-id="56344-294">Use the `IDatabase` instance to execute a Redis StringGet call using the given `customerId` as the key.</span></span>

1. <span data-ttu-id="56344-295">Compruebe si los datos se cargan desde Redis; en caso contrario, devuelve `null` .</span><span class="sxs-lookup"><span data-stu-id="56344-295">Check if data is loaded from Redis; if not, return `null`.</span></span>

1. <span data-ttu-id="56344-296">Deserializa los datos de Redis a un `CustomerBasket` objeto y devuelve el resultado.</span><span class="sxs-lookup"><span data-stu-id="56344-296">Deserialize the data from Redis to a `CustomerBasket` object and return the result.</span></span>

<span data-ttu-id="56344-297">En la aplicación de referencia [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) actualizada, una nueva `DaprBasketRepository` clase reemplaza a la `RedisBasketRepository` clase:</span><span class="sxs-lookup"><span data-stu-id="56344-297">In the updated [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) reference application, a new `DaprBasketRepository` class replaces the `RedisBasketRepository` class:</span></span>

```csharp
public class DaprBasketRepository : IBasketRepository
{
    private const string StoreName = "eshop-basket-statestore";

    private readonly DaprClient _daprClient;

    public DaprBasketRepository(DaprClient daprClient)
    {
        _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));;
    }

    public async Task<CustomerBasket> GetBasketAsync(string customerId)
    {
        return await _daprClient.GetStateAsync<CustomerBasket>(StoreName, customerId);
    }

    // ...
}
```

<span data-ttu-id="56344-298">El código actualizado usa el SDK de .NET de DAPR para leer y escribir datos mediante el bloque de creación de la administración de estado.</span><span class="sxs-lookup"><span data-stu-id="56344-298">The updated code uses the Dapr .NET SDK to read and write data using the state management building block.</span></span> <span data-ttu-id="56344-299">Los nuevos pasos para cargar la cesta de un cliente se han simplificado drásticamente:</span><span class="sxs-lookup"><span data-stu-id="56344-299">The new steps to load the basket for a customer are dramatically simplified:</span></span>

1. <span data-ttu-id="56344-300">Inserte un `DaprClient` en el constructor.</span><span class="sxs-lookup"><span data-stu-id="56344-300">Inject a `DaprClient` into the constructor.</span></span> <span data-ttu-id="56344-301">`DaprClient`Se registra con el marco de inserción de dependencias en el `Startup.cs` archivo.</span><span class="sxs-lookup"><span data-stu-id="56344-301">The `DaprClient` is registered with the dependency injection framework in the `Startup.cs` file.</span></span>
1. <span data-ttu-id="56344-302">Utilice el `DaprClient.GetStateAsync` método para cargar los elementos de la cesta de compras del cliente del almacén de estado configurado y devolver el resultado.</span><span class="sxs-lookup"><span data-stu-id="56344-302">Use the `DaprClient.GetStateAsync` method to load the customer's shopping basket items from the configured state store and return the result.</span></span>

<span data-ttu-id="56344-303">La implementación actualizada todavía usa Redis como almacén de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="56344-303">The updated implementation still uses Redis as the underlying data store.</span></span> <span data-ttu-id="56344-304">Sin embargo, DAPR abstrae las `StackExchange.Redis` referencias y la complejidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="56344-304">But, Dapr abstracts the `StackExchange.Redis` references and complexity from the application.</span></span> <span data-ttu-id="56344-305">Un archivo de configuración de DAPR es todo lo que se necesita:</span><span class="sxs-lookup"><span data-stu-id="56344-305">A Dapr configuration file is all that's needed:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: redisPassword
auth:
  secretStore: eshop-secretstore
```

<span data-ttu-id="56344-306">La implementación de DAPR también simplifica el cambio del almacén de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="56344-306">The Dapr implementation also simplifies changing the underlying data store.</span></span> <span data-ttu-id="56344-307">Por ejemplo, cambiar a Azure Table Storage solo requiere cambiar el contenido del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="56344-307">For example, switching to Azure Table Storage requires only changing the contents of the configuration file.</span></span> <span data-ttu-id="56344-308">No es necesario realizar ningún cambio en el código.</span><span class="sxs-lookup"><span data-stu-id="56344-308">No code changes are necessary.</span></span>

## <a name="summary"></a><span data-ttu-id="56344-309">Resumen</span><span class="sxs-lookup"><span data-stu-id="56344-309">Summary</span></span>

<span data-ttu-id="56344-310">El bloque de creación de administración de estado de DAPR ofrece una API para almacenar datos de clave/valor en varios almacenes de datos.</span><span class="sxs-lookup"><span data-stu-id="56344-310">The Dapr state management building block offers an API for storing key/value data across various data stores.</span></span> <span data-ttu-id="56344-311">La API proporciona compatibilidad con:</span><span class="sxs-lookup"><span data-stu-id="56344-311">The API provides support for:</span></span>

- <span data-ttu-id="56344-312">Operaciones masivas</span><span class="sxs-lookup"><span data-stu-id="56344-312">Bulk operations</span></span>
- <span data-ttu-id="56344-313">Coherencia fuerte y eventual</span><span class="sxs-lookup"><span data-stu-id="56344-313">Strong and eventual consistency</span></span>
- <span data-ttu-id="56344-314">Control de simultaneidad optimista</span><span class="sxs-lookup"><span data-stu-id="56344-314">Optimistic concurrency control</span></span>
- <span data-ttu-id="56344-315">Transacciones de varios elementos</span><span class="sxs-lookup"><span data-stu-id="56344-315">Multi-item transactions</span></span>

<span data-ttu-id="56344-316">El SDK de .NET proporciona compatibilidad específica del lenguaje para .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="56344-316">The .NET SDK provides language-specific support for .NET Core and ASP.NET Core.</span></span> <span data-ttu-id="56344-317">La integración del enlace de modelos simplifica el acceso y la actualización del estado desde ASP.NET Core métodos de acción del controlador.</span><span class="sxs-lookup"><span data-stu-id="56344-317">Model binding integration simplifies accessing and updating state from ASP.NET Core controller action methods.</span></span>

<span data-ttu-id="56344-318">En la aplicación de referencia eShopOnDapr, las ventajas de pasar a la administración de estado de DAPR son claras:</span><span class="sxs-lookup"><span data-stu-id="56344-318">In the eShopOnDapr reference application, the benefits to moving to Dapr state management are clear:</span></span>

1. <span data-ttu-id="56344-319">La nueva implementación utiliza menos líneas de código.</span><span class="sxs-lookup"><span data-stu-id="56344-319">The new implementation uses fewer lines of code.</span></span>
1. <span data-ttu-id="56344-320">Abstrae la complejidad de la API de terceros `StackExchange.Redis` .</span><span class="sxs-lookup"><span data-stu-id="56344-320">It abstracts away the complexity of the third-party `StackExchange.Redis` API.</span></span>
1. <span data-ttu-id="56344-321">Reemplazar la caché en Redis subyacente con un tipo diferente de almacén de datos ahora solo requiere cambios en el archivo de configuración del almacén de estado.</span><span class="sxs-lookup"><span data-stu-id="56344-321">Replacing the underlying Redis cache with a different type of data store now only requires changes to the state store configuration file.</span></span>

### <a name="references"></a><span data-ttu-id="56344-322">Referencias</span><span class="sxs-lookup"><span data-stu-id="56344-322">References</span></span>

- [<span data-ttu-id="56344-323">DAPR almacenes de estado compatibles</span><span class="sxs-lookup"><span data-stu-id="56344-323">Dapr supported state stores</span></span>](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/)

> [!div class="step-by-step"]
> <span data-ttu-id="56344-324">[Anterior](reference-application.md)
> [Siguiente](service-invocation.md)</span><span class="sxs-lookup"><span data-stu-id="56344-324">[Previous](reference-application.md)
[Next](service-invocation.md)</span></span>
