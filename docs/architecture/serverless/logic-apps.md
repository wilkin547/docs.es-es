---
title: 'Azure Logic Apps: Aplicaciones sin servidor'
description: Azure Logic Apps permite compilar flujos de trabajo escalables automatizados que integran aplicaciones y datos en los servicios en la nube y los sistemas locales.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 11fdf5b5f176eb0d66eee6dde7638d3eae1e1f55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171850"
---
# <a name="azure-logic-apps"></a>Azure Logic Apps

[Azure Logic Apps](/azure/logic-apps) proporciona un motor sin servidor para compilar flujos de trabajo automatizados que integran aplicaciones y datos entre los servicios en la nube y los sistemas locales. Puede crear flujos de trabajo mediante un diseñador visual. Puede desencadenar flujos de trabajo basados en eventos o temporizadores, y aprovechar los conectores para integrar aplicaciones y facilitar la comunicación de negocio a negocio (B2B). Logic Apps se integra sin problemas con Azure Functions.

![Logotipo de Azure Logic Apps](./media/logic-apps-logo.png)

Logic Apps puede hacer más cosas que simplemente conectar los servicios en la nube (como las funciones) con recursos en la nube (como colas y bases de datos). También puede orquestar los flujos de trabajo locales con la puerta de enlace local. Por ejemplo, puede usar la aplicación lógica para desencadenar un procedimiento almacenado de SQL local en respuesta a un evento basado en la nube o a una lógica condicional en el flujo de trabajo. Para más información, consulte [Conexión a orígenes de datos locales con la puerta de enlace de datos local de Azure](/azure/analysis-services/analysis-services-gateway).

![Arquitectura de Logic Apps](./media/logic-apps-architecture.png)

Al igual que Azure Functions, puede iniciar flujos de trabajo de Logic Apps con un desencadenador. Hay muchos desencadenadores entre los que puede elegir. En la captura siguiente se muestran solo algunos de los más populares de entre los cientos que están disponibles.

![Desencadenadores de Logic Apps](./media/logic-app-triggers.png)

Una vez que se desencadena la aplicación, puede usar el diseñador visual para crear pasos, bucles, condiciones y acciones. Los datos ingeridos en un paso anterior están disponibles para su uso en los pasos posteriores. El siguiente flujo de trabajo carga las direcciones URL desde una base de datos de CosmosDB. Busca los que tienen un host de `t.co` y luego los busca en Twitter. Si encuentra tweets correspondientes, actualiza los documentos con los tweets relacionados mediante una llamada a una función.

![Flujo de trabajo de Logic Apps](./media/logic-app-workflow.png)

En el panel de Logic Apps se muestra el historial de ejecución de los flujos de trabajo y si cada ejecución se completó correctamente o no. Puede ir a cualquier ejecución concreta e inspeccionar los datos que se usaron en cada paso para solucionar problemas. Logic Apps también proporciona plantillas ya existentes que puede editar y que son adecuadas para flujos de trabajo empresariales complejos.

Para más información, consulte [Azure Logic Apps](/azure/logic-apps).

>[!div class="step-by-step"]
>[Anterior](application-insights.md)
>[Siguiente](event-grid.md)
