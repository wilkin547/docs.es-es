---
title: 'Azure Logic Apps: aplicaciones sin servidor'
description: Azure Logic Apps permiten crear flujos de trabajo escalables automatizados que integran aplicaciones y servicios de datos a través de la nube y los sistemas locales.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638799"
---
# <a name="azure-logic-apps"></a>Azure Logic Apps

[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) proporciona un motor para crear flujos de trabajo automatizados para integrar las aplicaciones y los datos entre servicios en la nube sin servidor y sistemas locales. Crear flujos de trabajo mediante un diseñador visual. Puede desencadenar flujos de trabajo basados en eventos o los temporizadores y aproveche los conectores para aplicaciones de integración y facilitar la comunicación de negocio a negocio (B2B). Logic Apps se integra perfectamente con Azure Functions.

![Logotipo de Azure Logic Apps](./media/logic-apps-logo.png)

Logic Apps puede hacer más de los servicios en la nube (por ejemplo, las funciones), conecte con los recursos de nube (por ejemplo, colas y las bases de datos). También puede organizar los flujos de trabajo de forma local con la puerta de enlace local. Por ejemplo, puede usar la aplicación lógica para desencadenar la lógica condicional en el flujo de trabajo o un procedimiento almacenado de SQL de un entorno local en respuesta a un evento basado en la nube. Obtenga más información sobre [conectarse a orígenes de datos locales con puerta de enlace de datos de Azure local](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).

![Arquitectura de aplicaciones lógicas](./media/logic-apps-architecture.png)

Como las funciones de Azure, iniciar flujos de trabajo de aplicación lógica con un desencadenador. Hay muchos desencadenadores para que pueda elegir. La siguiente captura muestra algunas de las otras fuera de cientos más populares que están disponibles.

![Desencadenadores de aplicaciones lógicas](./media/logic-app-triggers.png)

Una vez que se desencadena la aplicación, puede usar el diseñador visual para crear pasos, bucles, condiciones y acciones. Los datos que ingiera en un paso anterior están disponibles para su uso en los siguientes pasos. El siguiente flujo de trabajo carga las direcciones URL de una base de datos de CosmosDB. Encuentra las aplicaciones con un host de `t.co` , a continuación, buscará en Twitter. Si encuentra tweets correspondientes, actualiza los documentos con los tweets relacionados mediante una llamada a una función.

![Flujo de trabajo de aplicación lógica](./media/logic-app-workflow.png)

El panel de aplicaciones lógicas muestra el historial de ejecución de los flujos de trabajo y si cada ejecución completada correctamente o no. Puede navegar por una ejecución específica e inspeccionar los datos utilizados por cada paso para solucionar problemas. Logic Apps también proporciona plantillas existentes, puede editar y se adapta perfectamente a los flujos de trabajo empresariales complejas.

Para obtener más información, consulte [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).

>[!div class="step-by-step"]
>[Anterior](application-insights.md)
>[Siguiente](event-grid.md)
