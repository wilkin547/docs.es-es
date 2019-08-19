---
title: Aplicaciones sin servidor Azure Logic Apps
description: Azure Logic Apps permiten crear flujos de trabajo escalables automatizados que integren aplicaciones y datos en servicios en la nube y sistemas locales.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577458"
---
# <a name="azure-logic-apps"></a>Azure Logic Apps

[Azure Logic apps](https://docs.microsoft.com/azure/logic-apps) proporciona un motor sin servidor para crear flujos de trabajo automatizados para integrar aplicaciones y datos entre servicios en la nube y sistemas locales. Los flujos de trabajo se crean mediante un diseñador visual. Puede desencadenar flujos de trabajo basados en eventos o temporizadores y aprovechar conectores para aplicaciones de integración y facilitar la comunicación de negocio a negocio (B2B). Logic Apps se integra sin problemas con Azure Functions.

![Azure Logic Apps logotipo](./media/logic-apps-logo.png)

Logic Apps puede hacer más que simplemente conectar los servicios en la nube (como las funciones) con recursos en la nube (como las colas y las bases de datos). También puede orquestar los flujos de trabajo locales con la puerta de enlace local. Por ejemplo, puede usar la aplicación lógica para desencadenar un procedimiento almacenado de SQL local en respuesta a un evento basado en la nube o a una lógica condicional en el flujo de trabajo. Más información sobre cómo [conectarse a orígenes de datos locales con la puerta de enlace de datos local de Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).

![Arquitectura de Logic Apps](./media/logic-apps-architecture.png)

Como Azure Functions, se inician flujos de trabajo de aplicaciones lógicas con un desencadenador. Hay muchos desencadenadores para elegir. En la captura siguiente se muestran solo algunos de los más populares de cientos que están disponibles.

![Desencadenadores Logic Apps](./media/logic-app-triggers.png)

Una vez que se desencadena la aplicación, puede usar el diseñador visual para crear pasos, bucles, condiciones y acciones. Los datos ingeridos en un paso anterior están disponibles para su uso en pasos posteriores. El siguiente flujo de trabajo carga las direcciones URL de una base de datos CosmosDB. Busca los que tienen un host `t.co` y los busca en Twitter. Si encuentra tweets correspondientes, actualiza los documentos con los tweets relacionados mediante una llamada a una función.

![Flujo de trabajo de aplicación lógica](./media/logic-app-workflow.png)

En el panel de Logic Apps se muestra el historial de ejecución de los flujos de trabajo y si cada ejecución se completó correctamente o no. Puede navegar a cualquier ejecución determinada e inspeccionar los datos que usa cada paso para solucionar problemas. Logic Apps también proporciona plantillas existentes que puede editar y que son adecuadas para flujos de trabajo empresariales complejos.

Para obtener más información, consulte [Azure Logic apps](https://docs.microsoft.com/azure/logic-apps).

>[!div class="step-by-step"]
>[Anterior](application-insights.md)
>[Siguiente](event-grid.md)
