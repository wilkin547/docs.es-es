---
description: 'Más información acerca de: seguimiento de variables y argumentos'
title: Seguimiento de variable y argumento
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: f2663e585ca280739f9c4ec176c31cf1d7c30657
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754984"
---
# <a name="variable-and-argument-tracking"></a><span data-ttu-id="c69c5-103">Seguimiento de variable y argumento</span><span class="sxs-lookup"><span data-stu-id="c69c5-103">Variable and Argument Tracking</span></span>

<span data-ttu-id="c69c5-104">Al realizar el seguimiento de la ejecución de un flujo de trabajo, a menudo resulta útil extraer los datos.</span><span class="sxs-lookup"><span data-stu-id="c69c5-104">When tracking the execution of a workflow, it is often useful to extract data.</span></span> <span data-ttu-id="c69c5-105">Esto proporciona contexto adicional al tener acceso a un registro de seguimiento posterior a la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c69c5-105">This provides additional context when accessing a tracking record post execution.</span></span> <span data-ttu-id="c69c5-106">En [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], puede extraer cualquier variable o argumento visibles dentro del ámbito de cualquier actividad en un flujo de trabajo que use el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c69c5-106">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], you can extract any visible variable or argument within the scope of any activity in a workflow using tracking.</span></span> <span data-ttu-id="c69c5-107">Los perfiles de seguimiento facilitan la extracción de datos.</span><span class="sxs-lookup"><span data-stu-id="c69c5-107">Tracking profiles make it easy to extract data.</span></span>  
  
## <a name="variables-and-arguments"></a><span data-ttu-id="c69c5-108">Variables y argumentos</span><span class="sxs-lookup"><span data-stu-id="c69c5-108">Variables and Arguments</span></span>  

 <span data-ttu-id="c69c5-109">Las variables y los argumentos se extraen cuando una actividad emite ActivityStateRecord.</span><span class="sxs-lookup"><span data-stu-id="c69c5-109">Variables and arguments are extracted when an activity emits an ActivityStateRecord.</span></span>  <span data-ttu-id="c69c5-110">Una variable solo está disponible para la extracción si se encuentra dentro del ámbito de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c69c5-110">A variable is available for extraction only if it is within the scope of the activity.</span></span> <span data-ttu-id="c69c5-111">Una variable que se va a extraer de una actividad se especifica de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c69c5-111">A variable to be extracted within an activity is specified in the following manner:</span></span>  
  
- <span data-ttu-id="c69c5-112">Si el nombre de variable especifica una variable, el seguimiento busca la variable en la actividad actual a la que se está realizando el seguimiento y en las actividades primarias.</span><span class="sxs-lookup"><span data-stu-id="c69c5-112">If a variable is specified by the variable name, then tracking looks for the variable within the current activity being tracked and in parent activities.</span></span> <span data-ttu-id="c69c5-113">Se busca la variable en el ámbito de actividad actual y en el ámbito primario.</span><span class="sxs-lookup"><span data-stu-id="c69c5-113">The variable is searched in current activity scope and in parent scope.</span></span>  
  
- <span data-ttu-id="c69c5-114">Si las variables que se van a extraer se especifican mediante name = " \* ", se extraerán todas las variables dentro de la actividad actual de la que se realiza el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c69c5-114">If variables to be extracted are specified by using name="\*", then all variables within the current activity being tracked are extracted.</span></span> <span data-ttu-id="c69c5-115">En este caso, las variables que estén dentro del ámbito pero que estén definidas en actividades primarias no se extraen.</span><span class="sxs-lookup"><span data-stu-id="c69c5-115">In this case variables that are in scope but defined in parent activities are not extracted.</span></span>  
  
 <span data-ttu-id="c69c5-116">Al extraer los argumentos, los argumentos extraídos dependen del estado de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c69c5-116">When extracting arguments, the arguments extracted depend on the state of the activity.</span></span> <span data-ttu-id="c69c5-117">Cuando el estado de una actividad es Executing, solo están disponibles para su extracción `InArguments`.</span><span class="sxs-lookup"><span data-stu-id="c69c5-117">When the state of an activity is Executing, then only the `InArguments` are available for extraction.</span></span> <span data-ttu-id="c69c5-118">Para cualquier otro estado de actividad (Closed, Faulted, Canceled), todos los argumentos, tanto InArguments como OutArguments, estarán disponibles para la extracción.</span><span class="sxs-lookup"><span data-stu-id="c69c5-118">For any other activity state (Closed, Faulted, Canceled), all arguments, both InArguments and OutArguments, are available for extraction.</span></span>  
  
 <span data-ttu-id="c69c5-119">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="c69c5-119">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="c69c5-120">Los argumentos y las variables solo se pueden extraer con <xref:System.Activities.Tracking.ActivityStateRecord> y, por tanto, se suscriben en un perfil de seguimiento con <xref:System.Activities.Tracking.ActivityStateQuery>.</span><span class="sxs-lookup"><span data-stu-id="c69c5-120">Variables and arguments can be extracted only with an <xref:System.Activities.Tracking.ActivityStateRecord> and thus are subscribed to within a tracking profile using <xref:System.Activities.Tracking.ActivityStateQuery>.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a><span data-ttu-id="c69c5-121">Proteger la información almacenada dentro de variables y argumentos</span><span class="sxs-lookup"><span data-stu-id="c69c5-121">Protecting Information Stored Within Variables and Arguments</span></span>  

 <span data-ttu-id="c69c5-122">El tiempo de ejecución de WF hace visible de manera predeterminada a la variable o argumento a los que se ha realizado el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c69c5-122">A tracked variable or argument is by default made visible by the WF runtime.</span></span> <span data-ttu-id="c69c5-123">Un desarrollador de software del flujo de trabajo puede evitar el acceso si da los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c69c5-123">A workflow developer can protect it from being accessed by taking the following steps:</span></span>  
  
1. <span data-ttu-id="c69c5-124">Cifre el valor de una variable.</span><span class="sxs-lookup"><span data-stu-id="c69c5-124">Encrypt the value of a variable.</span></span>  
  
2. <span data-ttu-id="c69c5-125">Controle la creación de un perfil de seguimiento para evitar la extracción de una variable o argumento.</span><span class="sxs-lookup"><span data-stu-id="c69c5-125">Control the authoring of a tracking profile to prevent the extraction of a variable or argument.</span></span>  
  
3. <span data-ttu-id="c69c5-126">En el caso de seguimiento personalizado, los participantes se aseguran de que el código WF no divulgue información confidencial que esté almacenada en variables o argumentos.</span><span class="sxs-lookup"><span data-stu-id="c69c5-126">For custom tracking participants ensure that the WF code does not disclose sensitive information that is stored in variables or arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69c5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c69c5-127">See also</span></span>

- <span data-ttu-id="c69c5-128">[Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c69c5-128">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="c69c5-129">[Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c69c5-129">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
