---
title: Registro con pila elástica
description: Registro con la pila elástica, Logstash y Kibana
ms.date: 02/05/2020
ms.openlocfilehash: 6863c66b63854fe3ecaabe2919beded2926ea64c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448932"
---
# <a name="logging-with-elastic-stack"></a>Registro con pila elástica

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Existen muchas herramientas de registro centralizadas y varían en lo que se refiere a las herramientas gratuitas de código abierto y a opciones más costosas. En muchos casos, las herramientas gratuitas son tan buenas como o mejores que las ofertas de pago. Una de estas herramientas es una combinación de tres componentes de código abierto: búsqueda elástica, Logstash y Kibana.

Colectivamente, estas herramientas se conocen como la pila elástica o la pila de ELK.

## <a name="elastic-stack"></a>Pila elástica

La pila elástica es una opción eficaz para recopilar información de un clúster de Kubernetes. Kubernetes admite el envío de registros a un punto de conexión de Elasticsearch y, en su [mayor parte](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), todo lo que necesita para empezar es establecer las variables de entorno como se muestra en la figura 7-5:

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

**Figura 7-5**. Variables de configuración para Kubernetes

Con esto se instalará Elasticsearch en el clúster y se le enviarán todos los registros de clúster.

![un ejemplo de un panel de Kibana que muestra los resultados de una consulta en los registros ingeridos de Kubernetes](./media/kibana-dashboard.png)
**figura 7-6**. Un ejemplo de un panel de Kibana que muestra los resultados de una consulta en los registros que se introducen en Kubernetes

## <a name="what-are-the-advantages-of-elastic-stack"></a>¿Cuáles son las ventajas de la pila elástica?

La pila elástica proporciona un registro centralizado en una manera de bajo costo, escalable y fácil de administrar. Su interfaz de usuario simplifica el análisis de datos, por lo que puede dedicar su tiempo a recopilar información de sus datos en lugar de luchar con una interfaz inadecuadas. Admite una amplia variedad de entradas, por lo que la aplicación distribuida abarca más y diferentes tipos de servicios, por lo que se puede esperar seguir pudiendo proporcionar datos de registro y métricas en el sistema. La pila elástica también admite búsquedas rápidas incluso en conjuntos de datos grandes, lo que permite incluso que las aplicaciones de gran tamaño registren datos detallados y sigan pudiendo tener visibilidad en el mismo de forma eficaz.

## <a name="logstash"></a>Logstash

El primer componente es [Logstash](https://www.elastic.co/products/logstash). Esta herramienta se usa para recopilar información de registro de una gran variedad de orígenes diferentes. Por ejemplo, Logstash puede leer registros del disco y recibir también mensajes de bibliotecas de registro como [Serilog](https://serilog.net/). Logstash puede realizar algunas tareas de filtrado y expansión básicas en los registros a medida que llegan. Por ejemplo, si los registros contienen direcciones IP, Logstash puede configurarse para realizar una búsqueda geográfica y obtener un país o incluso una ciudad de origen para ese mensaje.

Serilog es una biblioteca de registro para los lenguajes .NET, que permite el registro con parámetros. En lugar de generar un mensaje de registro de texto que incrusta campos, los parámetros se mantienen separados. Esto permite realizar búsquedas y filtrados más inteligentes. En la figura 7-7 se muestra una configuración de Serilog de ejemplo para escribir en Logstash.

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

**Figura 7-7**. Configuración de Serilog para escribir información de registro directamente en logstash a través de HTTP

Logstash usaría una configuración como la que se muestra en la figura 7-8.

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

**Figura 7-8.** Una configuración de Logstash para consumir registros de Serilog

En escenarios en los que no se necesita una manipulación de registros extensa, hay una alternativa a Logstash conocidas como [latidos](https://www.elastic.co/products/beats). Laters es una familia de herramientas que puede recopilar una gran variedad de datos de registros a datos de red e información de tiempo de actividad. Muchas aplicaciones usarán Logstash y las pulsaciones.

Una vez que los registros se han recopilado por Logstash, necesita algún lugar para colocarlos. Aunque Logstash admite muchas salidas diferentes, una de las más interesantes es la búsqueda elástica.

## <a name="elastic-search"></a>Búsqueda elástica

La búsqueda elástica es un eficaz motor de búsqueda que puede indexar los registros a medida que llegan. Facilita la ejecución de consultas en los registros. La búsqueda elástica puede controlar grandes cantidades de registros y, en casos extremos, se puede escalar horizontalmente a través de varios nodos.

Los mensajes de registro que se han diseñado para contener parámetros o que han tenido parámetros divididos de ellos a través del procesamiento de Logstash, se pueden consultar directamente, ya que Elasticsearch conserva esta información.

En la figura 7-9 se muestra una consulta que busca las 10 páginas principales visitadas por `jill@example.com`.

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

**Figura 7-9**. Una consulta de Elasticsearch para buscar las 10 páginas principales visitadas por un usuario

## <a name="visualizing-information-with-kibana-web-dashboards"></a>Visualización de información con los paneles Web de Kibana

El componente final de la pila es Kibana. Esta herramienta se usa para proporcionar visualizaciones interactivas en un panel Web. Los paneles pueden estar diseñados incluso por usuarios que no son técnicos. La mayoría de los datos que residen en el índice de Elasticsearch se pueden incluir en los paneles de Kibana. Los usuarios individuales pueden tener un panel distinto y Kibana permiten esta personalización a través de los paneles específicos del usuario.

## <a name="installing-elastic-stack-on-azure"></a>Instalación de la pila elástica en Azure

La pila elástica se puede instalar en Azure de varias maneras. Como siempre, es posible [aprovisionar máquinas virtuales e instalar la pila elástica en ellas directamente](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch). Algunos usuarios experimentados prefieren esta opción, ya que ofrece el mayor grado de personalización. La implementación en la infraestructura como servicio presenta una sobrecarga importante en la administración que obliga a quienes toman esa ruta de acceso a tomar posesión de todas las tareas asociadas a la infraestructura como servicio, como la protección de las máquinas y la actualización de las revisiones.

Una opción con menos sobrecarga es usar uno de los muchos contenedores de Docker en los que ya se ha configurado la pila elástica. Estos contenedores pueden colocarse en un clúster de Kubernetes existente y ejecutarse junto al código de la aplicación. El contenedor [sebp/Elk](https://elk-docker.readthedocs.io/) es un contenedor de pila elástica bien documentado y probado.

Otra opción es una [oferta de Elk como servicio anunciada recientemente](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).

## <a name="references"></a>Referencias

- [Instalación de la pila elástica en Azure](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
>[Anterior](observability-patterns.md)
>[Siguiente](monitoring-azure-kubernetes.md)
