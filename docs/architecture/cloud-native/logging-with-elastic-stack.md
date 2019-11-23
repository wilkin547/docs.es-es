---
title: Registro con pila elástica
description: Registro con la pila elástica, Logstash y Kibana
ms.date: 09/23/2019
ms.openlocfilehash: 989834925bc08541bf484e1a4567a56ac324872f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841742"
---
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="e7137-103">Registro con pila elástica</span><span class="sxs-lookup"><span data-stu-id="e7137-103">Logging with Elastic Stack</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e7137-104">Existen muchas herramientas de registro centralizadas y varían en lo que se refiere a las herramientas gratuitas de código abierto y a opciones más costosas.</span><span class="sxs-lookup"><span data-stu-id="e7137-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="e7137-105">En muchos casos, las herramientas gratuitas son tan buenas como o mejores que las ofertas de pago.</span><span class="sxs-lookup"><span data-stu-id="e7137-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="e7137-106">Una de estas herramientas es una combinación de tres componentes de código abierto: búsqueda elástica, Logstash y Kibana.</span><span class="sxs-lookup"><span data-stu-id="e7137-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>
<span data-ttu-id="e7137-107">Colectivamente, estas herramientas se conocen como la pila elástica o la pila de ELK.</span><span class="sxs-lookup"><span data-stu-id="e7137-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="e7137-108">¿Cuáles son las ventajas de la pila elástica?</span><span class="sxs-lookup"><span data-stu-id="e7137-108">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="e7137-109">La pila elástica proporciona un registro centralizado en una manera de bajo costo, escalable y fácil de administrar.</span><span class="sxs-lookup"><span data-stu-id="e7137-109">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="e7137-110">Su interfaz de usuario simplifica el análisis de datos, por lo que puede dedicar su tiempo a recopilar información de sus datos en lugar de luchar con una interfaz inadecuadas.</span><span class="sxs-lookup"><span data-stu-id="e7137-110">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="e7137-111">Admite una amplia variedad de entradas, por lo que la aplicación distribuida abarca más y diferentes tipos de servicios, por lo que se puede esperar seguir pudiendo proporcionar datos de registro y métricas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="e7137-111">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="e7137-112">La pila elástica también admite búsquedas rápidas incluso en conjuntos de datos grandes, lo que permite incluso que las aplicaciones de gran tamaño registren datos detallados y sigan pudiendo tener visibilidad en el mismo de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="e7137-112">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="e7137-113">Logstash</span><span class="sxs-lookup"><span data-stu-id="e7137-113">Logstash</span></span>

<span data-ttu-id="e7137-114">El primer componente es [Logstash](https://www.elastic.co/products/logstash).</span><span class="sxs-lookup"><span data-stu-id="e7137-114">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="e7137-115">Esta herramienta se usa para recopilar información de registro de una gran variedad de orígenes diferentes.</span><span class="sxs-lookup"><span data-stu-id="e7137-115">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="e7137-116">Por ejemplo, Logstash puede leer registros del disco y recibir también mensajes de bibliotecas de registro como [Serilog](https://serilog.net/).</span><span class="sxs-lookup"><span data-stu-id="e7137-116">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="e7137-117">Logstash puede realizar algunas tareas de filtrado y expansión básicas en los registros a medida que llegan.</span><span class="sxs-lookup"><span data-stu-id="e7137-117">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="e7137-118">Por ejemplo, si los registros contienen direcciones IP, Logstash puede configurarse para realizar una búsqueda geográfica y obtener un país o incluso una ciudad de origen para ese mensaje.</span><span class="sxs-lookup"><span data-stu-id="e7137-118">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="e7137-119">Serilog es una biblioteca de registro para los lenguajes .NET, que permite el registro con parámetros.</span><span class="sxs-lookup"><span data-stu-id="e7137-119">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="e7137-120">En lugar de generar un mensaje de registro de texto que incrusta campos, los parámetros se mantienen separados.</span><span class="sxs-lookup"><span data-stu-id="e7137-120">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="e7137-121">Esto permite realizar búsquedas y filtrados más inteligentes.</span><span class="sxs-lookup"><span data-stu-id="e7137-121">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="e7137-122">En la figura 7-2 se muestra una configuración de Serilog de ejemplo para escribir en Logstash.</span><span class="sxs-lookup"><span data-stu-id="e7137-122">A sample Serilog configuration for writing to Logstash appears in Figure 7-2.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="e7137-123">**Figura 7-2** Configuración de Serilog para escribir información de registro directamente en logstash a través de HTTP</span><span class="sxs-lookup"><span data-stu-id="e7137-123">**Figure 7-2** Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="e7137-124">Logstash usaría una configuración como la que se muestra en la figura 7-3.</span><span class="sxs-lookup"><span data-stu-id="e7137-124">Logstash would use a configuration like the one shown in Figure 7-3.</span></span>

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

<span data-ttu-id="e7137-125">**Figura 7-3** : configuración de Logstash para consumir registros de Serilog</span><span class="sxs-lookup"><span data-stu-id="e7137-125">**Figure 7-3** - A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="e7137-126">En escenarios en los que no se necesita una manipulación de registros extensa, hay una alternativa a Logstash conocidas como [latidos](https://www.elastic.co/products/beats).</span><span class="sxs-lookup"><span data-stu-id="e7137-126">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="e7137-127">Laters es una familia de herramientas que puede recopilar una gran variedad de datos de registros a datos de red e información de tiempo de actividad.</span><span class="sxs-lookup"><span data-stu-id="e7137-127">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="e7137-128">Muchas aplicaciones usarán Logstash y las pulsaciones.</span><span class="sxs-lookup"><span data-stu-id="e7137-128">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="e7137-129">Una vez que los registros se han recopilado por Logstash, necesita algún lugar para colocarlos.</span><span class="sxs-lookup"><span data-stu-id="e7137-129">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="e7137-130">Aunque Logstash admite muchas salidas diferentes, una de las más interesantes es la búsqueda elástica.</span><span class="sxs-lookup"><span data-stu-id="e7137-130">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="e7137-131">Búsqueda elástica</span><span class="sxs-lookup"><span data-stu-id="e7137-131">Elastic search</span></span>

<span data-ttu-id="e7137-132">La búsqueda elástica es un eficaz motor de búsqueda que puede indexar los registros a medida que llegan.</span><span class="sxs-lookup"><span data-stu-id="e7137-132">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="e7137-133">Facilita la ejecución de consultas en los registros.</span><span class="sxs-lookup"><span data-stu-id="e7137-133">It makes running queries against the logs quick.</span></span> <span data-ttu-id="e7137-134">La búsqueda elástica puede controlar grandes cantidades de registros y, en casos extremos, se puede escalar horizontalmente a través de varios nodos.</span><span class="sxs-lookup"><span data-stu-id="e7137-134">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="e7137-135">Los mensajes de registro que se han diseñado para contener parámetros o que han tenido parámetros divididos de ellos a través del procesamiento de Logstash, se pueden consultar directamente, ya que Elasticsearch conserva esta información.</span><span class="sxs-lookup"><span data-stu-id="e7137-135">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="e7137-136">En la figura 7-4 se muestra una consulta que busca las 10 páginas principales visitadas por `jill@example.com`.</span><span class="sxs-lookup"><span data-stu-id="e7137-136">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-4.</span></span>

```
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

<span data-ttu-id="e7137-137">**Figura 7-4** : consulta de Elasticsearch para buscar las 10 páginas principales visitadas por un usuario</span><span class="sxs-lookup"><span data-stu-id="e7137-137">**Figure 7-4** - An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="e7137-138">Visualización de información con los paneles Web de Kibana</span><span class="sxs-lookup"><span data-stu-id="e7137-138">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="e7137-139">El componente final de la pila es Kibana.</span><span class="sxs-lookup"><span data-stu-id="e7137-139">The final component of the stack is Kibana.</span></span> <span data-ttu-id="e7137-140">Esta herramienta se usa para proporcionar visualizaciones interactivas en un panel Web.</span><span class="sxs-lookup"><span data-stu-id="e7137-140">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="e7137-141">Los paneles pueden estar diseñados incluso por usuarios que no son técnicos.</span><span class="sxs-lookup"><span data-stu-id="e7137-141">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="e7137-142">La mayoría de los datos que residen en el índice de Elasticsearch se pueden incluir en los paneles de Kibana.</span><span class="sxs-lookup"><span data-stu-id="e7137-142">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="e7137-143">Los usuarios individuales pueden tener un panel distinto y Kibana permiten esta personalización a través de los paneles específicos del usuario.</span><span class="sxs-lookup"><span data-stu-id="e7137-143">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="e7137-144">Instalación de la pila elástica en Azure</span><span class="sxs-lookup"><span data-stu-id="e7137-144">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="e7137-145">La pila elástica se puede instalar en Azure de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="e7137-145">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="e7137-146">Como siempre, es posible [aprovisionar máquinas virtuales e instalar la pila elástica en ellas directamente](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span><span class="sxs-lookup"><span data-stu-id="e7137-146">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="e7137-147">Algunos usuarios experimentados prefieren esta opción, ya que ofrece el mayor grado de personalización.</span><span class="sxs-lookup"><span data-stu-id="e7137-147">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="e7137-148">La implementación en la infraestructura como servicio presenta una sobrecarga importante en la administración que obliga a quienes toman esa ruta de acceso a tomar posesión de todas las tareas asociadas a la infraestructura como servicio, como la protección de las máquinas y la actualización de las revisiones.</span><span class="sxs-lookup"><span data-stu-id="e7137-148">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="e7137-149">Una opción con menos sobrecarga es usar uno de los muchos contenedores de Docker en los que ya se ha configurado la pila elástica.</span><span class="sxs-lookup"><span data-stu-id="e7137-149">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="e7137-150">Estos contenedores pueden colocarse en un clúster de Kubernetes existente y ejecutarse junto al código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e7137-150">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="e7137-151">El contenedor [sebp/Elk](https://elk-docker.readthedocs.io/) es un contenedor de pila elástica bien documentado y probado.</span><span class="sxs-lookup"><span data-stu-id="e7137-151">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="e7137-152">Otra opción es una [oferta de Elk como servicio anunciada recientemente](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span><span class="sxs-lookup"><span data-stu-id="e7137-152">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="e7137-153">Referencias</span><span class="sxs-lookup"><span data-stu-id="e7137-153">References</span></span>

- [<span data-ttu-id="e7137-154">Instalación de la pila elástica en Azure</span><span class="sxs-lookup"><span data-stu-id="e7137-154">Install Elastic Stack on Azure</span></span>](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="e7137-155">[Anterior](observability-patterns.md)
>[Siguiente](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="e7137-155">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
