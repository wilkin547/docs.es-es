---
title: IfElse con reglas
ms.date: 03/30/2017
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
ms.openlocfilehash: 31906f04149a0ca7659201965ca565c7fa2af305
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500534"
---
# <a name="ifelse-with-rules"></a><span data-ttu-id="f4ef9-102">IfElse con reglas</span><span class="sxs-lookup"><span data-stu-id="f4ef9-102">IfElse With Rules</span></span>
<span data-ttu-id="f4ef9-103">En este ejemplo se muestra el uso de una condición de regla con una actividad <xref:System.Workflow.Activities.IfElseActivity>.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-103">This sample shows the use of a rule condition with an <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span>  
  
 <span data-ttu-id="f4ef9-104">En el ejemplo se pasa un parámetro `OrderValue` del host.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-104">The sample passes in an `OrderValue` parameter from the host.</span></span> <span data-ttu-id="f4ef9-105">El valor del parámetro se utiliza en una condición de regla en la primera bifurcación de la actividad <xref:System.Workflow.Activities.IfElseActivity>.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-105">The value of the parameter is used in a rule condition on the first branch of the <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span> <span data-ttu-id="f4ef9-106">Si el valor es menor que 10.000, se ejecuta la primera bifurcación y el <xref:System.Workflow.Activities.CodeActivity> actividad en la primera bifurcación imprime **Get Manager Approval** en la consola.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-106">If the value is less than 10,000, the first branch executes, and the <xref:System.Workflow.Activities.CodeActivity> activity in the first branch prints **Get Manager Approval** to the console.</span></span> <span data-ttu-id="f4ef9-107">Si el valor es mayor que 10.000, el <xref:System.Workflow.Activities.CodeActivity> ejecuta de actividad en la segunda bifurcación e imprime **Get VP Approval**.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-107">If the value is greater than 10,000, the <xref:System.Workflow.Activities.CodeActivity> activity in the second branch executes and prints **Get VP Approval**.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="f4ef9-108">Para compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-108">To build the sample</span></span>  
  
1.  <span data-ttu-id="f4ef9-109">Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4ef9-109">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="f4ef9-110">Compile la solución presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-110">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f4ef9-111">Ejecute la solución sin depuración presionando CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-111">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="f4ef9-112">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-112">To run the sample</span></span>  
  
-   <span data-ttu-id="f4ef9-113">En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta IfElseWithRules\bin\debug (o la carpeta IfElseWithRules\bin para la versión de Visual Basic del ejemplo), que se encuentra debajo de la carpeta principal del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-113">In the SDK Command Prompt window, run the .exe file in the IfElseWithRules\bin\debug folder (or the IfElseWithRules\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f4ef9-114">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f4ef9-115">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-115">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f4ef9-116">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f4ef9-117">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-117">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a><span data-ttu-id="f4ef9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4ef9-118">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
