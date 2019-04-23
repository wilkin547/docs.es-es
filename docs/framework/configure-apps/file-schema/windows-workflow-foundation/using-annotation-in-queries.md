---
title: Usar la anotación en las consultas
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: fd2d98852ca44e3485ddcf4be29d505b39011698
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208649"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="c32e4-102">Usar la anotación en las consultas</span><span class="sxs-lookup"><span data-stu-id="c32e4-102">Using Annotation in Queries</span></span>
<span data-ttu-id="c32e4-103">Las anotaciones le permiten etiquetar de forma arbitraria registros de seguimiento con un valor que se puede configurar después de la compilación.</span><span class="sxs-lookup"><span data-stu-id="c32e4-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="c32e4-104">Por ejemplo, es posible que desee varios registros de seguimiento a través de varios flujos de trabajo se etiqueten con "Mail Server" == "Mail Server1".</span><span class="sxs-lookup"><span data-stu-id="c32e4-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="c32e4-105">De esta forma, se facilita la búsqueda de todos los registros con esta etiqueta cuando se realizan consultas de registros de seguimiento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="c32e4-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="c32e4-106">Agregar anotaciones</span><span class="sxs-lookup"><span data-stu-id="c32e4-106">Adding Annotations</span></span>  
 <span data-ttu-id="c32e4-107">Se puede agregar una anotación en una consulta de seguimiento del modo que se indica en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c32e4-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="c32e4-108">Estos elementos de consulta de seguimiento se pueden usar para crear un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c32e4-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="c32e4-109">Puede crearse un perfil de seguimiento en la configuración o mediante código.</span><span class="sxs-lookup"><span data-stu-id="c32e4-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c32e4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c32e4-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="c32e4-111">\<participants></span><span class="sxs-lookup"><span data-stu-id="c32e4-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)
- [<span data-ttu-id="c32e4-112">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c32e4-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c32e4-113">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c32e4-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
