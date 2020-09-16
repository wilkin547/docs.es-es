---
title: Seguimiento de variable y argumento
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: af5c21b75f3238546acac0755ec4e6149ee50d95
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552497"
---
# <a name="variable-and-argument-tracking"></a><span data-ttu-id="5149b-102">Seguimiento de variable y argumento</span><span class="sxs-lookup"><span data-stu-id="5149b-102">Variable and Argument Tracking</span></span>
<span data-ttu-id="5149b-103">Al realizar el seguimiento de la ejecución de un flujo de trabajo, a menudo resulta útil extraer los datos.</span><span class="sxs-lookup"><span data-stu-id="5149b-103">When tracking the execution of a workflow, it is often useful to extract data.</span></span> <span data-ttu-id="5149b-104">Esto proporciona contexto adicional al tener acceso a un registro de seguimiento posterior a la ejecución.</span><span class="sxs-lookup"><span data-stu-id="5149b-104">This provides additional context when accessing a tracking record post execution.</span></span> <span data-ttu-id="5149b-105">En [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], puede extraer cualquier variable o argumento visibles dentro del ámbito de cualquier actividad en un flujo de trabajo que use el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5149b-105">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], you can extract any visible variable or argument within the scope of any activity in a workflow using tracking.</span></span> <span data-ttu-id="5149b-106">Los perfiles de seguimiento facilitan la extracción de datos.</span><span class="sxs-lookup"><span data-stu-id="5149b-106">Tracking profiles make it easy to extract data.</span></span>  
  
## <a name="variables-and-arguments"></a><span data-ttu-id="5149b-107">Variables y argumentos</span><span class="sxs-lookup"><span data-stu-id="5149b-107">Variables and Arguments</span></span>  
 <span data-ttu-id="5149b-108">Las variables y los argumentos se extraen cuando una actividad emite ActivityStateRecord.</span><span class="sxs-lookup"><span data-stu-id="5149b-108">Variables and arguments are extracted when an activity emits an ActivityStateRecord.</span></span>  <span data-ttu-id="5149b-109">Una variable solo está disponible para la extracción si se encuentra dentro del ámbito de la actividad.</span><span class="sxs-lookup"><span data-stu-id="5149b-109">A variable is available for extraction only if it is within the scope of the activity.</span></span> <span data-ttu-id="5149b-110">Una variable que se va a extraer de una actividad se especifica de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="5149b-110">A variable to be extracted within an activity is specified in the following manner:</span></span>  
  
- <span data-ttu-id="5149b-111">Si el nombre de variable especifica una variable, el seguimiento busca la variable en la actividad actual a la que se está realizando el seguimiento y en las actividades primarias.</span><span class="sxs-lookup"><span data-stu-id="5149b-111">If a variable is specified by the variable name, then tracking looks for the variable within the current activity being tracked and in parent activities.</span></span> <span data-ttu-id="5149b-112">Se busca la variable en el ámbito de actividad actual y en el ámbito primario.</span><span class="sxs-lookup"><span data-stu-id="5149b-112">The variable is searched in current activity scope and in parent scope.</span></span>  
  
- <span data-ttu-id="5149b-113">Si las variables que se van a extraer se especifican mediante name = " \* ", se extraerán todas las variables dentro de la actividad actual de la que se realiza el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5149b-113">If variables to be extracted are specified by using name="\*", then all variables within the current activity being tracked are extracted.</span></span> <span data-ttu-id="5149b-114">En este caso, las variables que estén dentro del ámbito pero que estén definidas en actividades primarias no se extraen.</span><span class="sxs-lookup"><span data-stu-id="5149b-114">In this case variables that are in scope but defined in parent activities are not extracted.</span></span>  
  
 <span data-ttu-id="5149b-115">Al extraer los argumentos, los argumentos extraídos dependen del estado de la actividad.</span><span class="sxs-lookup"><span data-stu-id="5149b-115">When extracting arguments, the arguments extracted depend on the state of the activity.</span></span> <span data-ttu-id="5149b-116">Cuando el estado de una actividad es Executing, solo están disponibles para su extracción `InArguments`.</span><span class="sxs-lookup"><span data-stu-id="5149b-116">When the state of an activity is Executing, then only the `InArguments` are available for extraction.</span></span> <span data-ttu-id="5149b-117">Para cualquier otro estado de actividad (Closed, Faulted, Canceled), todos los argumentos, tanto InArguments como OutArguments, estarán disponibles para la extracción.</span><span class="sxs-lookup"><span data-stu-id="5149b-117">For any other activity state (Closed, Faulted, Canceled), all arguments, both InArguments and OutArguments, are available for extraction.</span></span>  
  
 <span data-ttu-id="5149b-118">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="5149b-118">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="5149b-119">Los argumentos y las variables solo se pueden extraer con <xref:System.Activities.Tracking.ActivityStateRecord> y, por tanto, se suscriben en un perfil de seguimiento con <xref:System.Activities.Tracking.ActivityStateQuery>.</span><span class="sxs-lookup"><span data-stu-id="5149b-119">Variables and arguments can be extracted only with an <xref:System.Activities.Tracking.ActivityStateRecord> and thus are subscribed to within a tracking profile using <xref:System.Activities.Tracking.ActivityStateQuery>.</span></span>  
  
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
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a><span data-ttu-id="5149b-120">Proteger la información almacenada dentro de variables y argumentos</span><span class="sxs-lookup"><span data-stu-id="5149b-120">Protecting Information Stored Within Variables and Arguments</span></span>  
 <span data-ttu-id="5149b-121">El tiempo de ejecución de WF hace visible de manera predeterminada a la variable o argumento a los que se ha realizado el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5149b-121">A tracked variable or argument is by default made visible by the WF runtime.</span></span> <span data-ttu-id="5149b-122">Un desarrollador de software del flujo de trabajo puede evitar el acceso si da los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5149b-122">A workflow developer can protect it from being accessed by taking the following steps:</span></span>  
  
1. <span data-ttu-id="5149b-123">Cifre el valor de una variable.</span><span class="sxs-lookup"><span data-stu-id="5149b-123">Encrypt the value of a variable.</span></span>  
  
2. <span data-ttu-id="5149b-124">Controle la creación de un perfil de seguimiento para evitar la extracción de una variable o argumento.</span><span class="sxs-lookup"><span data-stu-id="5149b-124">Control the authoring of a tracking profile to prevent the extraction of a variable or argument.</span></span>  
  
3. <span data-ttu-id="5149b-125">En el caso de seguimiento personalizado, los participantes se aseguran de que el código WF no divulgue información confidencial que esté almacenada en variables o argumentos.</span><span class="sxs-lookup"><span data-stu-id="5149b-125">For custom tracking participants ensure that the WF code does not disclose sensitive information that is stored in variables or arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5149b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5149b-126">See also</span></span>

- <span data-ttu-id="5149b-127">[Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5149b-127">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="5149b-128">[Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5149b-128">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
