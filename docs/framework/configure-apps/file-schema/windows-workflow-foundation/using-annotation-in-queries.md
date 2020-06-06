---
title: Usar la anotación en las consultas
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 728408e744bc1eca62158fab1a7a17e985fe3b6c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69947283"
---
# <a name="using-annotation-in-queries"></a>Usar la anotación en las consultas
Las anotaciones le permiten etiquetar de forma arbitraria registros de seguimiento con un valor que se puede configurar después de la compilación. Por ejemplo, puede que desee etiquetar varios registros de seguimiento en varios flujos de trabajo con "servidor de correo" = = "mail server1". De esta forma, se facilita la búsqueda de todos los registros con esta etiqueta cuando se realizan consultas de registros de seguimiento posteriormente.  
  
## <a name="adding-annotations"></a>Agregar anotaciones  
 Se puede agregar una anotación en una consulta de seguimiento del modo que se indica en el siguiente ejemplo.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
> Estos elementos de consulta de seguimiento se pueden usar para crear un perfil de seguimiento. Puede crearse un perfil de seguimiento en la configuración o mediante código.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [Seguimiento y traza del flujo de trabajo](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md)
