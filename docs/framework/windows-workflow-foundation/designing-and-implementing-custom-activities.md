---
title: Diseñar e implementar actividades personalizadas
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: b0d04572c65fd4e3e0ae96241217c9ae9aa0e2c5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915360"
---
# <a name="designing-and-implementing-custom-activities"></a>Diseñar e implementar actividades personalizadas
Las actividades personalizadas en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se crean mediante el ensamblado de actividades proporcionadas por el sistema en actividades compuestas o mediante la creación de nuevos tipos que se deriven de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>. En esta sección se describe cómo crear actividades personalizadas con cualquier método.  
  
> [!IMPORTANT]
> Las actividades personalizadas se muestran de forma predeterminada en el diseñador de flujo de trabajo como un simple rectángulo con el nombre de la actividad. Para proporcionar una representación visual personalizada de la actividad en el diseñador de flujo de trabajo también debe crear un diseñador personalizado. Para obtener más información, vea [uso de plantillas y diseñadores de actividad personalizados](using-custom-activity-designers-and-templates.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Opciones de creación de actividades](activity-authoring-options-in-wf.md)  
 Trata los estilos de creación disponibles en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].  
  
 [Uso de una actividad personalizada](using-a-custom-activity.md)  
 Describe cómo agregar una actividad personalizada a un proyecto de flujo de trabajo.  
  
  [Creación de actividades asincrónicas](creating-asynchronous-activities-in-wf.md)  
 Describe cómo crear actividades asincrónicas.  
  
 [Configuración de la validación de actividades](configuring-activity-validation.md)  
 Describe cómo se puede usar la validación de la actividad para identificar y notificar los errores en la configuración de actividad antes de su ejecución.  
  
 [Creación de una actividad en el tiempo de ejecución](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 Describe cómo crear actividades en runtime mediante <xref:System.Activities.DynamicActivity>.  
  
 [Propiedades de ejecución de flujos de trabajo](workflow-execution-properties.md)  
 Describe cómo usar propiedades de ejecución del flujo de trabajo para agregar propiedades específicas del contexto al entorno de una actividad.  
  
 [Uso de delegados de actividad](using-activity-delegates.md)  
 Describe cómo crear y usar actividades que contienen delegados de actividad.
  
 [Uso de extensiones de actividad](using-activity-extensions.md)  
 Describe cómo crear y usar extensiones de actividad.  
  
 [Uso de fuentes de OData en un flujo de trabajo](consuming-odata-feeds-from-a-workflow.md)  
 Describe varios métodos para llamar a un servicio de datos de WCF desde un flujo de trabajo.  
  
 [Ámbito y visibilidad de la definición de actividad](activity-definition-scoping-and-visibility.md)  
 Describe las opciones y las reglas para definir el ámbito de los datos y la visibilidad de los miembros para actividades.
