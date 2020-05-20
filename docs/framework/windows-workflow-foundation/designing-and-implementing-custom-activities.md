---
title: Diseñar e implementar actividades personalizadas
description: En este artículo se proporcionan recursos para crear actividades personalizadas en Workflow Foundation mediante la creación de actividades compuestas o la creación de nuevos tipos de actividad.
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 9c184bff9518bb5581f3bf4cd408db224736192b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419998"
---
# <a name="designing-and-implementing-custom-activities"></a>Diseñar e implementar actividades personalizadas
Las actividades personalizadas en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se crean mediante el ensamblado de actividades proporcionadas por el sistema en actividades compuestas o mediante la creación de nuevos tipos que se deriven de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>. En esta sección se describe cómo crear actividades personalizadas con cualquier método.  
  
> [!IMPORTANT]
> Las actividades personalizadas se muestran de forma predeterminada en el diseñador de flujo de trabajo como un simple rectángulo con el nombre de la actividad. Para proporcionar una representación visual personalizada de la actividad en el diseñador de flujo de trabajo también debe crear un diseñador personalizado. Para obtener más información, vea [uso de plantillas y diseñadores de actividad personalizados](using-custom-activity-designers-and-templates.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Opciones de creación de actividades](activity-authoring-options-in-wf.md)  
 Trata los estilos de creación disponibles en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].  
  
 [Usar una actividad personalizada](using-a-custom-activity.md)  
 Describe cómo agregar una actividad personalizada a un proyecto de flujo de trabajo.  
  
  [Creación de actividades asincrónicas](creating-asynchronous-activities-in-wf.md)  
 Describe cómo crear actividades asincrónicas.  
  
 [Configurar la validación de actividades](configuring-activity-validation.md)  
 Describe cómo se puede usar la validación de la actividad para identificar y notificar los errores en la configuración de actividad antes de su ejecución.  
  
 [Creación de una actividad en el tiempo de ejecución](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 Describe cómo crear actividades en runtime mediante <xref:System.Activities.DynamicActivity>.  
  
 [Propiedades de ejecución del flujo de trabajo](workflow-execution-properties.md)  
 Describe cómo usar propiedades de ejecución del flujo de trabajo para agregar propiedades específicas del contexto al entorno de una actividad.  
  
 [Usar delegados de actividad](using-activity-delegates.md)  
 Describe cómo crear y usar actividades que contienen delegados de actividad.
  
 [Utilizar extensiones de actividad](using-activity-extensions.md)  
 Describe cómo crear y usar extensiones de actividad.  
  
 [Usar fuentes de OData en un flujo de trabajo](consuming-odata-feeds-from-a-workflow.md)  
 Describe varios métodos para llamar a un servicio de datos de WCF desde un flujo de trabajo.  
  
 [Ámbito y visibilidad de la definición de actividad](activity-definition-scoping-and-visibility.md)  
 Describe las opciones y las reglas para definir el ámbito de los datos y la visibilidad de los miembros para actividades.
