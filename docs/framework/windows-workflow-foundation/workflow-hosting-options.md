---
description: 'Más información sobre: opciones de hospedaje de flujo de trabajo'
title: Opciones de hospedaje de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
ms.openlocfilehash: 64d02decd3a096b4c83555729826c5fc07b13cbf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754893"
---
# <a name="workflow-hosting-options"></a>Opciones de hospedaje de flujo de trabajo

La mayoría de los ejemplos de Windows Workflow Foundation (WF) usan flujos de trabajo que se hospedan en una aplicación de consola, pero no es un escenario realista para los flujos de trabajo del mundo real. Los flujos de trabajo de las aplicaciones empresariales reales se hospedarán en procesos persistentes, ya sea un servicio de Windows creado por el desarrollador o una aplicación de servidor como IIS 7,0 o AppFabric. Las diferencias entre estas aproximaciones son las que se indican a continuación.

## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a>Hospedar flujos de trabajo en IIS con Windows AppFabric

Usar IIS con AppFabric es el host preferido para los flujos de trabajo. Windows Activation Service, que quita la dependencia de HTTP a través de IIS solamente, es la aplicación de host para flujos de trabajo que usan AppFabric.

## <a name="hosting-workflows-in-iis-alone"></a>Hospedar flujos de trabajo solo en IIS

No se recomienda usar IIS 7,0 por sí mismo, ya que existen herramientas de administración y supervisión disponibles con AppFabric que facilitan el mantenimiento de las aplicaciones en ejecución. Los flujos de trabajo solo se deben hospedar en IIS 7,0 solo si hay problemas de infraestructura con el cambio a AppFabric.

> [!WARNING]
> IIS 7,0 recicla los grupos de aplicaciones periódicamente por varias razones. Cuando se recicla un grupo de aplicaciones, IIS deja de aceptar mensajes en el grupo anterior y crea instancias en un grupo de aplicaciones nuevo para aceptar las nuevas solicitudes. Si un flujo de trabajo sigue funcionando después de enviar una respuesta, IIS 7,0 no será consciente del trabajo que se realiza y puede reciclar el grupo de aplicaciones de hospedaje. Si esto ocurre, el flujo de trabajo se anulará y los servicios de seguimiento registrarán un mensaje [1004-WorkflowInstanceAborted](1004-workflowinstanceaborted.md) con un campo motivo vacío.
>
> Si se usa la persistencia, el host debe reiniciar explícitamente las instancias anuladas desde el último punto de persistencia.
>
> Si se usa AppFabric, el servicio de administración de flujo de trabajo reanudará finalmente el flujo de trabajo desde el último punto de persistencia correcto si se usa la persistencia. Si no se usa ninguna persistencia, y el flujo de trabajo realiza operaciones fuera de un patrón de solicitud y respuesta, los datos se perderán cuando se anule el flujo de trabajo.

## <a name="hosting-a-workflow-in-a-custom-windows-service"></a>Hospedar un flujo de trabajo en un servicio de Windows personalizado

Crear un servicio de flujo de trabajo personalizado para hospedar el flujo de trabajo requerirá que el desarrollador duplique muchas de las funcionalidades que AppFabric ha proporcionado de serie, pero permitirá más flexibilidad con las funcionalidades personalizadas. Esta opción solo debe tenerse en cuenta si no es posible AppFabric.
