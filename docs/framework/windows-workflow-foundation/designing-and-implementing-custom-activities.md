---
title: Diseñar e implementar actividades personalizadas
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bafa54764ba8b02dd05cadd65c3f3cbc64c4b081
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="designing-and-implementing-custom-activities"></a>Diseñar e implementar actividades personalizadas
Las actividades personalizadas en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se crean mediante el ensamblado de actividades proporcionadas por el sistema en actividades compuestas o mediante la creación de nuevos tipos que se deriven de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>. En esta sección se describe cómo crear actividades personalizadas con cualquier método.  
  
> [!IMPORTANT]
>  Las actividades personalizadas se muestran de forma predeterminada en el diseñador de flujo de trabajo como un simple rectángulo con el nombre de la actividad. Para proporcionar una representación visual personalizada de la actividad en el diseñador de flujo de trabajo también debe crear un diseñador personalizado. Para obtener más información, consulte [utilizando diseñadores de actividad personalizados y plantillas de](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Opciones de creación de actividades](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 Trata los estilos de creación disponibles en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].  
  
 [Uso de una actividad personalizada](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 Describe cómo agregar una actividad personalizada a un proyecto de flujo de trabajo.  
  
  [Creación de actividades asincrónicas](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 Describe cómo crear actividades asincrónicas.  
  
 [Configuración de la validación de actividades](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 Describe cómo se puede usar la validación de la actividad para identificar y notificar los errores en la configuración de actividad antes de su ejecución.  
  
 [Creación de una actividad en el tiempo de ejecución](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 Describe cómo crear actividades en runtime mediante <xref:System.Activities.DynamicActivity>.  
  
 [Propiedades de ejecución de flujos de trabajo](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 Describe cómo usar propiedades de ejecución del flujo de trabajo para agregar propiedades específicas del contexto al entorno de una actividad.  
  
 [Uso de delegados de actividad](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 Describe cómo crear y usar actividades que contienen delegados de actividad.  
  
 [Adaptación de actividades](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 Describe cómo usar la localización de recursos de cadena en actividades.  
  
 [Uso de extensiones de actividad](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 Describe cómo crear y usar extensión de actividad.  
  
 [Uso de fuentes de OData en un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 Describe varios métodos para llamar a un servicio de datos de WCF desde un flujo de trabajo.  
  
 [Ámbito y visibilidad de la definición de actividad](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 Describe las opciones y las reglas para definir el ámbito de los datos y la visibilidad de los miembros para actividades.
