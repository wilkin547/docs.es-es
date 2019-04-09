---
title: Usar la anotación en las consultas
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: fd2d98852ca44e3485ddcf4be29d505b39011698
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208649"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="4185c-102">Usar la anotación en las consultas</span><span class="sxs-lookup"><span data-stu-id="4185c-102">Using Annotation in Queries</span></span>
<span data-ttu-id="4185c-103">Las anotaciones le permiten etiquetar de forma arbitraria registros de seguimiento con un valor que se puede configurar después de la compilación.</span><span class="sxs-lookup"><span data-stu-id="4185c-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="4185c-104">Por ejemplo, es posible que desee varios registros de seguimiento a través de varios flujos de trabajo se etiqueten con "Mail Server" == "Mail Server1".</span><span class="sxs-lookup"><span data-stu-id="4185c-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="4185c-105">De esta forma, se facilita la búsqueda de todos los registros con esta etiqueta cuando se realizan consultas de registros de seguimiento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4185c-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="4185c-106">Agregar anotaciones</span><span class="sxs-lookup"><span data-stu-id="4185c-106">Adding Annotations</span></span>  
 <span data-ttu-id="4185c-107">Se puede agregar una anotación en una consulta de seguimiento del modo que se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4185c-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="4185c-108">Estos elementos de consulta de seguimiento se pueden usar para crear un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4185c-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="4185c-109">Puede crearse un perfil de seguimiento en la configuración o mediante código.</span><span class="sxs-lookup"><span data-stu-id="4185c-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4185c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4185c-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="4185c-111">\<participants></span><span class="sxs-lookup"><span data-stu-id="4185c-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)
- [<span data-ttu-id="4185c-112">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4185c-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4185c-113">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4185c-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
