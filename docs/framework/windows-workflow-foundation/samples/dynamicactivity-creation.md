---
title: "Creación de DynamicActivity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 43f39d5c78e59925ad73fe7277300848877f83f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="dynamicactivity-creation"></a><span data-ttu-id="5018a-102">Creación de DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="5018a-102">DynamicActivity Creation</span></span>
<span data-ttu-id="5018a-103">En este ejemplo se muestran dos maneras diferentes de crear una actividad en tiempo de ejecución utilizando la actividad <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="5018a-103">This sample demonstrates two different ways to create an activity at runtime using the <xref:System.Activities.DynamicActivity> activity.</span></span>  
  
 <span data-ttu-id="5018a-104">En este ejemplo, se crea una actividad en tiempo de ejecución con un cuerpo que contiene una actividad <xref:System.Activities.Statements.Sequence> que incluye las actividades <xref:System.Activities.Statements.ForEach%601> y <xref:System.Activities.Statements.Assign%601>.</span><span class="sxs-lookup"><span data-stu-id="5018a-104">In this sample, an activity is created at runtime with a body that contains a <xref:System.Activities.Statements.Sequence> activity that contains <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.Assign%601> activities.</span></span> <span data-ttu-id="5018a-105">Se pasa una lista de entrada de enteros a la actividad y se establece como una propiedad.</span><span class="sxs-lookup"><span data-stu-id="5018a-105">An input list of integers is passed into the activity and set as a property.</span></span> <span data-ttu-id="5018a-106">A continuación, la actividad <xref:System.Activities.Statements.ForEach%601> recorre en iteración la lista de valores y la acumula.</span><span class="sxs-lookup"><span data-stu-id="5018a-106">The <xref:System.Activities.Statements.ForEach%601> activity then iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="5018a-107">En la actividad <xref:System.Activities.Statements.Assign%601>, el valor medio se calcula dividiendo el acumulador por el número de elementos en la lista y asignándolo a la media.</span><span class="sxs-lookup"><span data-stu-id="5018a-107">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assign it to the average.</span></span>  
  
 <span data-ttu-id="5018a-108">En el ejemplo se muestra el uso de una actividad <xref:System.Activities.DynamicActivity> que pasa variables como argumentos de entrada y devuelve valores como argumentos de salida.</span><span class="sxs-lookup"><span data-stu-id="5018a-108">The sample demonstrates the usage of a <xref:System.Activities.DynamicActivity> activity that flows in variables as input arguments and returning values as output arguments.</span></span> <span data-ttu-id="5018a-109">La actividad tiene un argumento de entrada denominado `Numbers` que es una lista de enteros.</span><span class="sxs-lookup"><span data-stu-id="5018a-109">The activity has one input argument named `Numbers` that is a list of integers.</span></span> <span data-ttu-id="5018a-110">La actividad <xref:System.Activities.Statements.ForEach%601> recorre en iteración la lista de valores y la acumula.</span><span class="sxs-lookup"><span data-stu-id="5018a-110">The <xref:System.Activities.Statements.ForEach%601> activity iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="5018a-111">En la actividad <xref:System.Activities.Statements.Assign%601>, el valor medio se calcula dividiendo el acumulador por el número de elementos en la lista y asignándolo a la media.</span><span class="sxs-lookup"><span data-stu-id="5018a-111">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assigning it to the average.</span></span> <span data-ttu-id="5018a-112">La media se devuelve como un argumento de salida denominado `Average`.</span><span class="sxs-lookup"><span data-stu-id="5018a-112">The average is returned as an output argument named `Average`.</span></span>  
  
 <span data-ttu-id="5018a-113">Cuando se crea la actividad dinámica mediante programación, la entrada y la salida se declaran como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="5018a-113">When the dynamic activity is created programmatically, the input and output are declared as shown in the following code example.</span></span>  
  
```csharp  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
};  
```  
  
 <span data-ttu-id="5018a-114">El siguiente ejemplo de código muestra la definición completa de `DynamicActivity` que calcula la media de los valores de una lista.</span><span class="sxs-lookup"><span data-stu-id="5018a-114">The following code example shows the complete definition of the `DynamicActivity` that computes the average of the values in a list.</span></span>  
  
```  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
    Implementation = () =>  
        new Sequence  
        {  
            Variables = { result, accumulator },  
            Activities =  
            {  
                new ForEach<int>  
                {  
                    Values =  new ArgumentValue<IEnumerable<int>> { ArgumentName = "Numbers" },                                  
                    Body = new ActivityAction<int>  
                    {  
                        Argument = iterationVariable,  
                        Handler = new Assign<int>  
                        {  
                            To = accumulator,  
                            Value = new InArgument<int>(env => iterationVariable.Get(env) +  accumulator.Get(env))  
                        }  
                    }  
                },  
  
                // Calculate the average and assign to the output argument.  
                new Assign<double>  
                {  
                    To = new ArgumentReference<double> { ArgumentName = "Average" },  
                    Value = new InArgument<double>(env => accumulator.Get(env) / numbers.Get(env).Count<int>())  
                },  
            }  
        }  
};  
```  
  
 <span data-ttu-id="5018a-115">Cuando se crean en XAML, la entrada y salida se declaran como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5018a-115">When created in XAML, the input and output are declared as shown in the following example.</span></span>  
  
```xml  
<Activity x:Class="Microsoft.Samples.DynamicActivityCreation.FindAverage"  
          xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
          xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Numbers" Type="InArgument(scg:List(x:Int32))" />  
    <x:Property Name="Average" Type="OutArgument(x:Double)" />  
  </x:Members>  
    ...  
    ...  
</Activity>  
```  
  
 <span data-ttu-id="5018a-116">El XAML se puede crear visualmente utilizando [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5018a-116">The XAML can be created visually using the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="5018a-117">Si se incluye en un proyecto de Visual Studio, asegúrese de establecer su "acción de compilación" en "None" para evitar que se está compilando.</span><span class="sxs-lookup"><span data-stu-id="5018a-117">If it is included in a Visual Studio project, be sure to set its "Build Action" to "None" to prevent it from being compiled.</span></span> <span data-ttu-id="5018a-118">El XAML se puede cargar entonces dinámicamente utilizando la siguiente llamada.</span><span class="sxs-lookup"><span data-stu-id="5018a-118">The XAML can then be loaded dynamically using the following call.</span></span>  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 <span data-ttu-id="5018a-119">La instancia de <xref:System.Activities.DynamicActivity> creada mediante programación o a través de la carga de un flujo de trabajo de XAML se puede utilizar como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="5018a-119">The <xref:System.Activities.DynamicActivity> instance created programmatically or through loading a XAML workflow can be used as shown in the following code example.</span></span> <span data-ttu-id="5018a-120">Tenga en cuenta que el "acto" pasado a la `WorkflowInvoker.Invoke` es el "acto" <xref:System.Activities.Activity> definido en el primer ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="5018a-120">Please note that "act" passed to the `WorkflowInvoker.Invoke` is the "act" <xref:System.Activities.Activity> defined in the first code example.</span></span>  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5018a-121">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="5018a-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="5018a-122">Abra el archivo de solución de DynamicActivityCreation.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5018a-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DynamicActivityCreation.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5018a-123">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="5018a-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5018a-124">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="5018a-124">To run the solution, press CTRL+F5.</span></span>  
  
## <a name="command-line-arguments"></a><span data-ttu-id="5018a-125">Argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5018a-125">Command line arguments</span></span>  
 <span data-ttu-id="5018a-126">En este ejemplo se aceptan los argumentos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5018a-126">This sample accepts command line arguments.</span></span> <span data-ttu-id="5018a-127">Los usuarios pueden proporcionar una lista de números para que la actividad calcule su media.</span><span class="sxs-lookup"><span data-stu-id="5018a-127">Users can provide a list of numbers for the activity to calculate their average.</span></span> <span data-ttu-id="5018a-128">La lista de números que se va a utilizar se pasa como una lista de números separados por un espacio.</span><span class="sxs-lookup"><span data-stu-id="5018a-128">The list of numbers to be used is passed as a list of numbers separated by a space.</span></span> <span data-ttu-id="5018a-129">Por ejemplo, para calcular la media de 5, 10 y 32, invoque el ejemplo utilizando la siguiente línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5018a-129">For example, to calculate the average of 5, 10, and 32 invoke the sample using the following command line.</span></span>  
  
 <span data-ttu-id="5018a-130">**DynamicActivityCreation 5 10 32**</span><span class="sxs-lookup"><span data-stu-id="5018a-130">**DynamicActivityCreation 5 10 32**</span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="5018a-131">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5018a-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5018a-132">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5018a-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5018a-133">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5018a-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5018a-134">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5018a-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`