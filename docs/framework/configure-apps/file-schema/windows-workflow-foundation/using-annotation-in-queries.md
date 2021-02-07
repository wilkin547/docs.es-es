---
description: 'Más información sobre: usar la anotación en las consultas'
title: Usar la anotación en las consultas
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 97423fe8ea7d90522a5f469adda5f645aa7e4485
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698029"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="5f137-103">Usar la anotación en las consultas</span><span class="sxs-lookup"><span data-stu-id="5f137-103">Using Annotation in Queries</span></span>

<span data-ttu-id="5f137-104">Las anotaciones le permiten etiquetar de forma arbitraria registros de seguimiento con un valor que se puede configurar después de la compilación.</span><span class="sxs-lookup"><span data-stu-id="5f137-104">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="5f137-105">Por ejemplo, puede que desee etiquetar varios registros de seguimiento en varios flujos de trabajo con "servidor de correo" = = "mail server1".</span><span class="sxs-lookup"><span data-stu-id="5f137-105">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="5f137-106">De esta forma, se facilita la búsqueda de todos los registros con esta etiqueta cuando se realizan consultas de registros de seguimiento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="5f137-106">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="5f137-107">Agregar anotaciones</span><span class="sxs-lookup"><span data-stu-id="5f137-107">Adding Annotations</span></span>  

 <span data-ttu-id="5f137-108">Se puede agregar una anotación en una consulta de seguimiento del modo que se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5f137-108">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="5f137-109">Estos elementos de consulta de seguimiento se pueden usar para crear un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5f137-109">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="5f137-110">Puede crearse un perfil de seguimiento en la configuración o mediante código.</span><span class="sxs-lookup"><span data-stu-id="5f137-110">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f137-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f137-111">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [<span data-ttu-id="5f137-112">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f137-112">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5f137-113">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5f137-113">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
