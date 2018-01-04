---
title: Actividad CommentOut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 900f6647eadb04a783fe0a3a143a71d9c766a48c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="commentout-activity"></a><span data-ttu-id="445ba-102">Actividad CommentOut</span><span class="sxs-lookup"><span data-stu-id="445ba-102">CommentOut Activity</span></span>
<span data-ttu-id="445ba-103">En este ejemplo se muestra cómo escribir una actividad personalizada que quita otras actividades de la ruta de acceso de ejecución, marcándolas como comentario.</span><span class="sxs-lookup"><span data-stu-id="445ba-103">This sample demonstrates how to write a custom activity that removes other activities from the path of execution, effectively commenting them out.</span></span>  
  
## <a name="the-commentout-activity"></a><span data-ttu-id="445ba-104">Actividad CommentOut</span><span class="sxs-lookup"><span data-stu-id="445ba-104">The CommentOut Activity</span></span>  
 <span data-ttu-id="445ba-105">Para lograr su objetivo, la actividad CommentOut deriva de la clase base <xref:System.Activities.CodeActivity> e implementa un método <xref:System.Activities.CodeActivity.Execute%2A> vacío.</span><span class="sxs-lookup"><span data-stu-id="445ba-105">To achieve its goal, the CommentOut activity derives from the <xref:System.Activities.CodeActivity> base class and implements an empty <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 <span data-ttu-id="445ba-106">La clase se declara tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="445ba-106">The class is declared as shown in the following example.</span></span>  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 <span data-ttu-id="445ba-107">El atributo `Designer` especifica la clase que implementa la interfaz visual de la actividad en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="445ba-107">The `Designer` attribute specifies the class that implements the visual interface of the activity at design time.</span></span> <span data-ttu-id="445ba-108">El atributo `ContentProperty` declara que la propiedad `"Body"` se puede omitir en la representación de XAML de una instancia de esta actividad.</span><span class="sxs-lookup"><span data-stu-id="445ba-108">The `ContentProperty` attribute declares that the `"Body"` property can be skipped in the XAML representation of an instance of this activity.</span></span>  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 <span data-ttu-id="445ba-109">En la clase de diseñador, XAML se usa para crear una representación visual personalizada de la actividad.</span><span class="sxs-lookup"><span data-stu-id="445ba-109">In the designer class, XAML is used to create a custom visual representation of the activity.</span></span> <span data-ttu-id="445ba-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> es una clase que proporciona el editor visual.</span><span class="sxs-lookup"><span data-stu-id="445ba-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> is a class that provides the visual editor.</span></span>  
  
 <span data-ttu-id="445ba-111">En la superficie de la actividad `CommentOut` solamente se puede colocar una única actividad.</span><span class="sxs-lookup"><span data-stu-id="445ba-111">A single activity can be dropped onto the `CommentOut` activity surface.</span></span> <span data-ttu-id="445ba-112">Si desea agregar varias actividades a esta superficie, arrastre una actividad de secuencia primero.</span><span class="sxs-lookup"><span data-stu-id="445ba-112">If you want to add multiple activities to this surface, drag a sequence activity here first.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="445ba-113">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="445ba-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="445ba-114">Abra CommentOut.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="445ba-114">Open CommentOut.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="445ba-115">Compile la solución presionando CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="445ba-115">Compile the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="445ba-116">Inicie el ejemplo sin depuración presionando CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="445ba-116">Start the sample without debugging by pressing CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="445ba-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="445ba-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="445ba-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="445ba-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="445ba-119">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="445ba-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="445ba-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="445ba-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
