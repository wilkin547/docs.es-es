---
title: Interoperabilidad con un conjunto de reglas 3.5
ms.date: 03/30/2017
ms.assetid: 969f3295-d874-428c-a9c6-623e3d578e51
ms.openlocfilehash: 5ea5454ef80bfd83611ed20392782d99cd8c0c25
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46324297"
---
# <a name="interop-with-35-rule-set"></a><span data-ttu-id="a2a1f-102">Interoperabilidad con un conjunto de reglas 3.5</span><span class="sxs-lookup"><span data-stu-id="a2a1f-102">Interop with 3.5 Rule Set</span></span>
<span data-ttu-id="a2a1f-103">Este ejemplo muestra el uso de la <xref:System.Activities.Statements.Interop> para la integración con una actividad personalizada en [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] mediante <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` y reglas.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-103">This sample demonstrates the use of the <xref:System.Activities.Statements.Interop> activity to integrate with a custom activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] using <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` and rules.</span></span> <span data-ttu-id="a2a1f-104">Pasa los datos a la actividad personalizada enlazando las variables [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] a las propiedades de dependencia expuestas por la actividad personalizada.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-104">It passes data to the custom activity by binding [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2a1f-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2a1f-105">Requirements</span></span>  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
2.  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
3.  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]  
  
## <a name="demonstrates"></a><span data-ttu-id="a2a1f-106">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="a2a1f-106">Demonstrates</span></span>  
 <span data-ttu-id="a2a1f-107"><xref:System.Activities.Statements.Interop> actividad, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` actividad en [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] con propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="a2a1f-107"><xref:System.Activities.Statements.Interop> activity, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] with dependency properties</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a2a1f-108">Explicación</span><span class="sxs-lookup"><span data-stu-id="a2a1f-108">Discussion</span></span>  
 <span data-ttu-id="a2a1f-109">En el ejemplo se muestra uno de los escenarios de integración para integrar con una actividad de [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2a1f-109">The sample demonstrates one of the integration scenarios for integrating with a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] activity.</span></span> <span data-ttu-id="a2a1f-110">Este ejemplo incluye un [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] actividad personalizada que invoca un <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` actividad.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-110">This sample includes a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] custom activity that invokes a <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity.</span></span>  
  
## <a name="travelrulelibrary"></a><span data-ttu-id="a2a1f-111">TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="a2a1f-111">TravelRuleLibrary</span></span>  
 <span data-ttu-id="a2a1f-112">Al abrir TravelRuleSet.cs en el diseñador, se muestra una actividad secuencial personalizada que contiene una actividad Policy de la siguiente forma</span><span class="sxs-lookup"><span data-stu-id="a2a1f-112">Opening TravelRuleSet.cs in the designer shows a custom sequential activity that contains a Policy activity as follows</span></span>  
  
 <span data-ttu-id="a2a1f-113">![Actividad Interop](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span><span class="sxs-lookup"><span data-stu-id="a2a1f-113">![Interop Activity](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span></span>  
  
 <span data-ttu-id="a2a1f-114">Haga doble clic en el **DiscountPolicy** actividad policy para examinar las reglas.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-114">Double-click the **DiscountPolicy** policy activity to examine the rules.</span></span> <span data-ttu-id="a2a1f-115">Aparece el editor de reglas para mostrar las reglas.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-115">The Rules editor appears to show the rules.</span></span>  
  
 <span data-ttu-id="a2a1f-116">![Editor de conjunto de reglas](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span><span class="sxs-lookup"><span data-stu-id="a2a1f-116">![Rule Set Editor](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span></span>  
  
 <span data-ttu-id="a2a1f-117">Haga clic en el **DiscountPolicy** actividad y seleccione el **ver código** opción para examinar el código lateral código C# que acompaña a esta actividad.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-117">Right-click the **DiscountPolicy** activity and select the **View Code** option to examine the code-beside C# code that goes with this activity.</span></span> <span data-ttu-id="a2a1f-118">Observe el valor de propiedad de dependencia para `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-118">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="a2a1f-119">Es equivalente a un <xref:System.Activities.Argument> en [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2a1f-119">This is equivalent to an <xref:System.Activities.Argument> in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span>  
  
```  
public static DependencyProperty DiscountLevelProperty = DependencyProperty.Register("DiscountLevel", typeof(int), typeof(TravelRuleSet));  
  
[DescriptionAttribute("DiscountLevel")]  
[CategoryAttribute("DiscountLevel Category")]  
[BrowsableAttribute(true)]  
[DesignerSerializationVisibilityAttribute(DesignerSerializationVisibility.Visible)]  
public int DiscountLevel  
{  
   get  
   {  
return ((int)base.GetValue(TravelRuleSet.DiscountLevelProperty)));  
   }  
   set  
   {  
base.SetValue(TravelRuleSet.DiscountLevelProperty, value);  
   }  
}  
```  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="a2a1f-120">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="a2a1f-120">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="a2a1f-121">Es un proyecto de flujo de trabajo secuencial de [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] que utiliza la actividad <xref:System.Activities.Statements.Interop> para integrar con el conjunto de reglas personalizado creado en el proyecto TravelRuleLibrary.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-121">This is a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom rule set created in the TravelRuleLibrary project.</span></span> <span data-ttu-id="a2a1f-122">Las variables se crean en el nivel superior de <xref:System.Activities.Statements.Sequence> como sigue.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-122">Variables are created on the top-level <xref:System.Activities.Statements.Sequence> as follows.</span></span>  
  
 <span data-ttu-id="a2a1f-123">![Las variables](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span><span class="sxs-lookup"><span data-stu-id="a2a1f-123">![Variables](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span></span>  
  
 <span data-ttu-id="a2a1f-124">![El Explorador de soluciones](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span><span class="sxs-lookup"><span data-stu-id="a2a1f-124">![Solution Explorer](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span></span>  
  
 <span data-ttu-id="a2a1f-125">Por último, la actividad <xref:System.Activities.Statements.Interop> se utiliza para integrar con TravelRuleSet.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-125">Lastly, the <xref:System.Activities.Statements.Interop> activity is used to integrate with the TravelRuleSet.</span></span> <span data-ttu-id="a2a1f-126">Las variables que se declararon anteriormente en <xref:System.Activities.Statements.Sequence> se utilizan para enlazar a las propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-126">The variables that were declared earlier on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
 <span data-ttu-id="a2a1f-127">![Tipo de actividad](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span><span class="sxs-lookup"><span data-stu-id="a2a1f-127">![Activity Type](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span></span>  
  
 <span data-ttu-id="a2a1f-128">![Flecha](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span><span class="sxs-lookup"><span data-stu-id="a2a1f-128">![Arrow](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span></span>  
  
 <span data-ttu-id="a2a1f-129">![Propiedades](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span><span class="sxs-lookup"><span data-stu-id="a2a1f-129">![Properties](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a2a1f-130">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a2a1f-131">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a2a1f-132">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a2a1f-133">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a2a1f-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`
