---
title: Directiva simple
ms.date: 03/30/2017
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
ms.openlocfilehash: 7f189e4d1811cb0b7dd9138b944bfd0552481690
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561269"
---
# <a name="simple-policy"></a><span data-ttu-id="a5bcf-102">Directiva simple</span><span class="sxs-lookup"><span data-stu-id="a5bcf-102">Simple Policy</span></span>
<span data-ttu-id="a5bcf-103">En este ejemplo se muestra cómo utilizar una actividad <xref:System.Workflow.Activities.PolicyActivity> en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="a5bcf-104">El flujo de trabajo secuencial de este ejemplo se crea utilizando una actividad <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="a5bcf-105">El flujo de trabajo define campos `orderValue`, `customerType`  y `discount` que se utilizan para definir un flujo de trabajo de descuento de productos.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="a5bcf-106">Las reglas definidas en los archivos de reglas establecen un valor de descuento basado en los campos `orderValue` y `customerType`.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="a5bcf-107">`orderValue` y `customerType` se establecen en la definición de clase `SimplePolicyWorkflow` y se pueden cambiar para modificar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="a5bcf-108">El descuento resultante se escribe en la consola el controlador de eventos <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> que se define en la clase `SimplePolicyWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="a5bcf-109">Para compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5bcf-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="a5bcf-110">Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5bcf-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="a5bcf-111">Compile la solución presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a5bcf-112">Ejecute la solución sin depuración presionando CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="a5bcf-113">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5bcf-113">To run the sample</span></span>  
  
-   <span data-ttu-id="a5bcf-114">En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta SimplePolicy\bin\debug (o la carpeta SimplePolicy\bin para la versión de Visual Basic del ejemplo), que se encuentra debajo de la carpeta principal del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a5bcf-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a5bcf-116">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="a5bcf-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a5bcf-117">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a5bcf-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a5bcf-118">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="a5bcf-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="a5bcf-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5bcf-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="a5bcf-120">Directiva avanzada</span><span class="sxs-lookup"><span data-stu-id="a5bcf-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
