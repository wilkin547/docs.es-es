---
title: Registro con pila elástica
description: Registro con la pila elástica, Logstash y Kibana
ms.date: 01/19/2021
ms.openlocfilehash: ebe7eef16d3b1a73d0fd3a010a509bbaf7be3fd5
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99505822"
---
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="9cf2f-103">Registro con pila elástica</span><span class="sxs-lookup"><span data-stu-id="9cf2f-103">Logging with Elastic Stack</span></span>

<span data-ttu-id="9cf2f-104">Existen muchas herramientas de registro centralizadas y varían en lo que se refiere a las herramientas gratuitas de código abierto y a opciones más costosas.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="9cf2f-105">En muchos casos, las herramientas gratuitas son tan buenas como o mejores que las ofertas de pago.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="9cf2f-106">Una de estas herramientas es una combinación de tres componentes de código abierto: búsqueda elástica, Logstash y Kibana.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>

<span data-ttu-id="9cf2f-107">Colectivamente, estas herramientas se conocen como la pila elástica o la pila de ELK.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="9cf2f-108">Pila elástica</span><span class="sxs-lookup"><span data-stu-id="9cf2f-108">Elastic Stack</span></span>

<span data-ttu-id="9cf2f-109">La pila elástica es una opción eficaz para recopilar información de un clúster de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-109">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="9cf2f-110">Kubernetes admite el envío de registros a un punto de conexión de Elasticsearch y, en su [mayor parte](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), todo lo que necesita para empezar es establecer las variables de entorno como se muestra en la figura 7-5:</span><span class="sxs-lookup"><span data-stu-id="9cf2f-110">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="9cf2f-111">**Figura 7-5**.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-111">**Figure 7-5**.</span></span> <span data-ttu-id="9cf2f-112">Variables de configuración para Kubernetes</span><span class="sxs-lookup"><span data-stu-id="9cf2f-112">Configuration variables for Kubernetes</span></span>

<span data-ttu-id="9cf2f-113">En este paso se instalará Elasticsearch en el clúster y se le enviará un destino que le envíe todos los registros del clúster.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-113">This step will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="9cf2f-114">![Un ejemplo de un panel de Kibana que muestra los resultados de una consulta en los registros ingeridos de la ](./media/kibana-dashboard.png)
 **figura 7-6** de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-114">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="9cf2f-115">Un ejemplo de un panel de Kibana que muestra los resultados de una consulta en los registros que se introducen en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="9cf2f-115">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="9cf2f-116">¿Cuáles son las ventajas de la pila elástica?</span><span class="sxs-lookup"><span data-stu-id="9cf2f-116">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="9cf2f-117">La pila elástica proporciona un registro centralizado en una manera de bajo costo, escalable y fácil de administrar.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-117">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="9cf2f-118">Su interfaz de usuario simplifica el análisis de datos, por lo que puede dedicar su tiempo a recopilar información de sus datos en lugar de luchar con una interfaz inadecuadas.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-118">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="9cf2f-119">Admite una amplia variedad de entradas, por lo que la aplicación distribuida abarca más y diferentes tipos de servicios, por lo que se puede esperar seguir pudiendo proporcionar datos de registro y métricas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-119">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="9cf2f-120">La pila elástica también admite búsquedas rápidas incluso en conjuntos de datos grandes, lo que permite incluso que las aplicaciones de gran tamaño registren datos detallados y sigan pudiendo tener visibilidad en el mismo de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-120">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="9cf2f-121">Logstash</span><span class="sxs-lookup"><span data-stu-id="9cf2f-121">Logstash</span></span>

<span data-ttu-id="9cf2f-122">El primer componente es [Logstash](https://www.elastic.co/products/logstash).</span><span class="sxs-lookup"><span data-stu-id="9cf2f-122">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="9cf2f-123">Esta herramienta se usa para recopilar información de registro de una gran variedad de orígenes diferentes.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-123">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="9cf2f-124">Por ejemplo, Logstash puede leer registros del disco y recibir también mensajes de bibliotecas de registro como [Serilog](https://serilog.net/).</span><span class="sxs-lookup"><span data-stu-id="9cf2f-124">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="9cf2f-125">Logstash puede realizar algunas tareas de filtrado y expansión básicas en los registros a medida que llegan.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-125">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="9cf2f-126">Por ejemplo, si los registros contienen direcciones IP, Logstash puede configurarse para realizar una búsqueda geográfica y obtener un país o incluso una ciudad de origen para ese mensaje.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-126">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="9cf2f-127">Serilog es una biblioteca de registro para los lenguajes .NET, que permite el registro con parámetros.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-127">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="9cf2f-128">En lugar de generar un mensaje de registro de texto que incrusta campos, los parámetros se mantienen separados.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-128">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="9cf2f-129">Esta biblioteca permite realizar búsquedas y filtrados más inteligentes.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-129">This library allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="9cf2f-130">En la figura 7-7 se muestra una configuración de Serilog de ejemplo para escribir en Logstash.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-130">A sample Serilog configuration for writing to Logstash appears in Figure 7-7.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="9cf2f-131">**Figura 7-7**.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-131">**Figure 7-7**.</span></span> <span data-ttu-id="9cf2f-132">Configuración de Serilog para escribir información de registro directamente en logstash a través de HTTP</span><span class="sxs-lookup"><span data-stu-id="9cf2f-132">Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="9cf2f-133">Logstash usaría una configuración como la que se muestra en la figura 7-8.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-133">Logstash would use a configuration like the one shown in Figure 7-8.</span></span>

```
input {
    http {
        #default host 0.0.0.0:8080
        codec => json
    }
}

output {
    elasticsearch {
        hosts => "elasticsearch:9200"
        index=>"sales-%{+xxxx.ww}"
    }
}
```

<span data-ttu-id="9cf2f-134">**Figura 7-8.**</span><span class="sxs-lookup"><span data-stu-id="9cf2f-134">**Figure 7-8**.</span></span> <span data-ttu-id="9cf2f-135">Una configuración de Logstash para consumir registros de Serilog</span><span class="sxs-lookup"><span data-stu-id="9cf2f-135">A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="9cf2f-136">En escenarios en los que no se necesita una manipulación de registros extensa, hay una alternativa a Logstash conocidas como [latidos](https://www.elastic.co/products/beats).</span><span class="sxs-lookup"><span data-stu-id="9cf2f-136">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="9cf2f-137">Laters es una familia de herramientas que puede recopilar una gran variedad de datos de registros a datos de red e información de tiempo de actividad.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-137">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="9cf2f-138">Muchas aplicaciones usarán Logstash y las pulsaciones.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-138">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="9cf2f-139">Una vez que los registros se han recopilado por Logstash, necesita algún lugar para colocarlos.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-139">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="9cf2f-140">Aunque Logstash admite muchas salidas diferentes, una de las más interesantes es la búsqueda elástica.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-140">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="9cf2f-141">Búsqueda elástica</span><span class="sxs-lookup"><span data-stu-id="9cf2f-141">Elastic search</span></span>

<span data-ttu-id="9cf2f-142">La búsqueda elástica es un eficaz motor de búsqueda que puede indexar los registros a medida que llegan.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-142">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="9cf2f-143">Facilita la ejecución de consultas en los registros.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-143">It makes running queries against the logs quick.</span></span> <span data-ttu-id="9cf2f-144">La búsqueda elástica puede controlar grandes cantidades de registros y, en casos extremos, se puede escalar horizontalmente a través de varios nodos.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-144">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="9cf2f-145">Los mensajes de registro que se han diseñado para contener parámetros o que han tenido parámetros divididos de ellos a través del procesamiento de Logstash, se pueden consultar directamente, ya que Elasticsearch conserva esta información.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-145">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="9cf2f-146">En la figura 7-9 se muestra una consulta que busca las 10 páginas principales visitadas por `jill@example.com` .</span><span class="sxs-lookup"><span data-stu-id="9cf2f-146">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-9.</span></span>

```json
"query": {
    "match": {
      "user": "jill@example.com"
    }
  },
  "aggregations": {
    "top_10_pages": {
      "terms": {
        "field": "page",
        "size": 10
      }
    }
  }
```

<span data-ttu-id="9cf2f-147">**Figura 7-9**.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-147">**Figure 7-9**.</span></span> <span data-ttu-id="9cf2f-148">Una consulta de Elasticsearch para buscar las 10 páginas principales visitadas por un usuario</span><span class="sxs-lookup"><span data-stu-id="9cf2f-148">An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="9cf2f-149">Visualización de información con los paneles Web de Kibana</span><span class="sxs-lookup"><span data-stu-id="9cf2f-149">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="9cf2f-150">El componente final de la pila es Kibana.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-150">The final component of the stack is Kibana.</span></span> <span data-ttu-id="9cf2f-151">Esta herramienta se usa para proporcionar visualizaciones interactivas en un panel Web.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-151">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="9cf2f-152">Los paneles pueden estar diseñados incluso por usuarios que no son técnicos.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-152">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="9cf2f-153">La mayoría de los datos que residen en el índice de Elasticsearch se pueden incluir en los paneles de Kibana.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-153">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="9cf2f-154">Los usuarios individuales pueden tener un panel distinto y Kibana permiten esta personalización a través de los paneles específicos del usuario.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-154">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="9cf2f-155">Instalación de la pila elástica en Azure</span><span class="sxs-lookup"><span data-stu-id="9cf2f-155">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="9cf2f-156">La pila elástica se puede instalar en Azure de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-156">The Elastic stack can be installed on Azure in many ways.</span></span> <span data-ttu-id="9cf2f-157">Como siempre, es posible [aprovisionar máquinas virtuales e instalar la pila elástica en ellas directamente](/azure/virtual-machines/linux/tutorial-elasticsearch).</span><span class="sxs-lookup"><span data-stu-id="9cf2f-157">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="9cf2f-158">Algunos usuarios experimentados prefieren esta opción, ya que ofrece el mayor grado de personalización.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-158">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="9cf2f-159">La implementación en la infraestructura como servicio presenta una sobrecarga importante en la administración que obliga a quienes toman esa ruta de acceso a tomar posesión de todas las tareas asociadas a la infraestructura como servicio, como la protección de las máquinas y la actualización de las revisiones.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-159">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="9cf2f-160">Una opción con menos sobrecarga es usar uno de los muchos contenedores de Docker en los que ya se ha configurado la pila elástica.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-160">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="9cf2f-161">Estos contenedores pueden colocarse en un clúster de Kubernetes existente y ejecutarse junto al código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-161">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="9cf2f-162">El contenedor [sebp/Elk](https://elk-docker.readthedocs.io/) es un contenedor de pila elástica bien documentado y probado.</span><span class="sxs-lookup"><span data-stu-id="9cf2f-162">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="9cf2f-163">Otra opción es una [oferta de Elk como servicio anunciada recientemente](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span><span class="sxs-lookup"><span data-stu-id="9cf2f-163">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="9cf2f-164">Referencias</span><span class="sxs-lookup"><span data-stu-id="9cf2f-164">References</span></span>

- [<span data-ttu-id="9cf2f-165">Instalación de la pila elástica en Azure</span><span class="sxs-lookup"><span data-stu-id="9cf2f-165">Install Elastic Stack on Azure</span></span>](/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="9cf2f-166">[Anterior](observability-patterns.md)
>[Siguiente](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="9cf2f-166">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
