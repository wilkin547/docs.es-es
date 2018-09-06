---
title: Usar actividades de procedimiento
ms.date: 03/30/2017
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
ms.openlocfilehash: bd83f1a0fa9f3af7c22cee73fbc4f984a9ebf53c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804781"
---
# <a name="using-procedural-activities"></a><span data-ttu-id="04e1d-102">Usar actividades de procedimiento</span><span class="sxs-lookup"><span data-stu-id="04e1d-102">Using Procedural Activities</span></span>
<span data-ttu-id="04e1d-103">En el ejemplo se utilizan las actividades <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> y <xref:System.Activities.Statements.WriteLine> para implementar un juego de adivinanzas.</span><span class="sxs-lookup"><span data-stu-id="04e1d-103">The sample uses the <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, and <xref:System.Activities.Statements.WriteLine> activities to implement a guessing game.</span></span> <span data-ttu-id="04e1d-104">La adivinanza selecciona un número aleatorio y el jugador tiene que adivinar el número.</span><span class="sxs-lookup"><span data-stu-id="04e1d-104">The guessing game selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="04e1d-105">Cuando el jugador envía una suposición incorrecta, el flujo de trabajo proporciona una sugerencia para indicar si es mayor o menor.</span><span class="sxs-lookup"><span data-stu-id="04e1d-105">When the player submits an incorrect guess, the workflow provides a hint whether to guess higher or lower.</span></span> <span data-ttu-id="04e1d-106">Si el jugador adivina el número en menos de 7 intentos, se muestra una felicitación especial.</span><span class="sxs-lookup"><span data-stu-id="04e1d-106">If the player guesses the number in less than 7 attempts, a special congratulations is displayed to the user.</span></span>  
  
## <a name="custom-activities-in-this-sample"></a><span data-ttu-id="04e1d-107">Actividades personalizadas de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="04e1d-107">Custom Activities in this Sample</span></span>  
  
### <a name="readline"></a><span data-ttu-id="04e1d-108">ReadLine</span><span class="sxs-lookup"><span data-stu-id="04e1d-108">ReadLine</span></span>  
 <span data-ttu-id="04e1d-109">Lee una línea de texto de la consola.</span><span class="sxs-lookup"><span data-stu-id="04e1d-109">Reads a line of text from the console.</span></span> <span data-ttu-id="04e1d-110">Esta actividad deriva de la clase <xref:System.Activities.NativeActivity> y crea un marcador que la aplicación de consola reanuda cuando se lee una línea.</span><span class="sxs-lookup"><span data-stu-id="04e1d-110">This activity derives from the <xref:System.Activities.NativeActivity> class and creates a bookmark that is resumed by the console application when a line is read.</span></span>  
  
### <a name="promptint"></a><span data-ttu-id="04e1d-111">PromptInt</span><span class="sxs-lookup"><span data-stu-id="04e1d-111">PromptInt</span></span>  
 <span data-ttu-id="04e1d-112">Solicita al usuario que escriba un número y, a continuación, lo lee de una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="04e1d-112">Prompts the user to type in a number and then reads it from a console window.</span></span> <span data-ttu-id="04e1d-113">La actividad deriva de <xref:System.Activities.Activity%601> y utiliza las actividades <xref:System.Activities.Statements.WriteLine> y `ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="04e1d-113">The activity derives from <xref:System.Activities.Activity%601> and uses the <xref:System.Activities.Statements.WriteLine> and `ReadLine` activities.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="04e1d-114">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="04e1d-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="04e1d-115">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución GuessingGame.sln.</span><span class="sxs-lookup"><span data-stu-id="04e1d-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the GuessingGame.sln solution file.</span></span>  
  
2.  <span data-ttu-id="04e1d-116">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="04e1d-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="04e1d-117">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="04e1d-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="04e1d-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="04e1d-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="04e1d-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="04e1d-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="04e1d-120">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="04e1d-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="04e1d-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="04e1d-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`