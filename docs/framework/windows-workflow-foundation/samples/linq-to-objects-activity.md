---
title: Actividad de LINQ to Objects
ms.date: 03/30/2017
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
ms.openlocfilehash: fca4a94a951c9713a61914de6ef33e0cbb74f75e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43552773"
---
# <a name="linq-to-objects-activity"></a><span data-ttu-id="4a6e7-102">Actividad de LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="4a6e7-102">LINQ to Objects Activity</span></span>
<span data-ttu-id="4a6e7-103">En este ejemplo se muestra cómo crear una actividad para utilizar LINQ to Objects para consultar elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-103">This sample demonstrates how to create an activity to use LINQ to Objects to query elements in a collection.</span></span>  
  
## <a name="activity-details-for-findincollection"></a><span data-ttu-id="4a6e7-104">Detalles de la actividad FindInCollection</span><span class="sxs-lookup"><span data-stu-id="4a6e7-104">Activity Details for FindInCollection</span></span>  
 <span data-ttu-id="4a6e7-105">Esta actividad permite a los usuarios consultar elementos de las colecciones en memoria mediante LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-105">This activity allows users to query elements from collections in memory using LINQ to Objects.</span></span> <span data-ttu-id="4a6e7-106">Debe proporcionar un predicado de LINQ en forma de una expresión lambda para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-106">You must provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="4a6e7-107">Esta actividad se puede utilizar junto con las actividades <xref:System.Activities.Statements.AddToCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-107">This activity can be used in conjunction with <xref:System.Activities.Statements.AddToCollection%601> activities.</span></span>  
  
 <span data-ttu-id="4a6e7-108">En la siguiente tabla se detallan las propiedades y los valores devueltos de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-108">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="4a6e7-109">Propiedad o valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4a6e7-109">Property or Return Value</span></span>|<span data-ttu-id="4a6e7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a6e7-110">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="4a6e7-111">Propiedad `Collection`</span><span class="sxs-lookup"><span data-stu-id="4a6e7-111">`Collection` property</span></span>|<span data-ttu-id="4a6e7-112">Propiedad necesaria que especifica la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-112">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="4a6e7-113">Propiedad `Predicate`</span><span class="sxs-lookup"><span data-stu-id="4a6e7-113">`Predicate` property</span></span>|<span data-ttu-id="4a6e7-114">Propiedad necesaria que especifica el filtro para la colección en forma de expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-114">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="4a6e7-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4a6e7-115">Return Value</span></span>|<span data-ttu-id="4a6e7-116">La colección filtrada.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-116">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="4a6e7-117">Ejemplo de código que utiliza la actividad personalizada</span><span class="sxs-lookup"><span data-stu-id="4a6e7-117">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="4a6e7-118">El siguiente ejemplo de código utiliza la actividad personalizada `FindInCollection` para localizar todas las filas de una colección de empleados que tienen una propiedad `Role` establecida en `Manager` y la propiedad `Location` establecida en `Redmond`.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-118">The following code example uses the `FindInCollection` custom activity to find all rows in a collection of employees that have a `Role` property set to `Manager` and the `Location` property set to `Redmond`.</span></span>  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 <span data-ttu-id="4a6e7-119">El siguiente código muestra cómo crear un programa de flujo de trabajo que utiliza actividad FindInCollection personalizada, las actividades <xref:System.Activities.Statements.AddToCollection%601> y <xref:System.Activities.Statements.ForEach%601> para rellenar una colección con empleados, localizar todos los empleados que tienen roles de desarrollador y se encuentran en Redmond y, a continuación, recorrer en iteración la lista resultante.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-119">The following code shows how to create a workflow program that uses the custom FindInCollection activity, <xref:System.Activities.Statements.AddToCollection%601>, and <xref:System.Activities.Statements.ForEach%601> activities to populate a collection with employees, find all the employees that have developer roles and are located in Redmond, and then iterate through the resulting list.</span></span>  
  
```csharp  
// Create the Linq predicate for the find expression  
  
Func<Employee, bool> predicate = e => e.Role == "DEV" && e.Location.Equals("Redmond");  
  
// Create workflow program  
Activity sampleWorkflow = new Sequence  
{  
    Variables = { employees, devsFromRedmond },  
    Activities =  
    {  
        new Assign<IList<Employee>>  
        {  
            To = employees,  
            Value = new LambdaValue<IList<Employee>>(c => new List<Employee>())  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(1, "Employee 1", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(2, "Employee 2", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(3, "Employee 3", "PM", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(4, "Employee 4", "PM", "China"))  
        },  
        new FindInCollection<Employee>  
        {  
            Collections = new InArgument<IEnumerable<Employee>>(employees),  
            Predicate = new LambdaValue<Func<Employee, bool>>(c => predicate),  
            Result = new OutArgument<IList<Employee>>(devsFromRedmond)  
        },  
        new ForEach<Employee>  
        {  
            Values = new InArgument<IEnumerable<Employee>>(devsFromRedmond),  
            Body = new ActivityAction<Employee>  
            {  
                Argument = iterationVariable,  
                Handler = new WriteLine  
                {  
                    Text = new InArgument<string>(env => iterationVariable.Get(env).ToString())  
                }  
            }  
        }  
    }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4a6e7-120">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a6e7-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="4a6e7-121">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LinqToObjects.sln.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-121">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToObjects.sln solution file.</span></span>  
  
2.  <span data-ttu-id="4a6e7-122">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-122">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4a6e7-123">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-123">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4a6e7-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4a6e7-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4a6e7-126">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4a6e7-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="4a6e7-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a><span data-ttu-id="4a6e7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a6e7-128">See Also</span></span>  
 [<span data-ttu-id="4a6e7-129">Expresiones lambda (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4a6e7-129">Lambda Expressions (C# Programming Guide)</span></span>](https://go.microsoft.com/fwlink/?LinkId=150381)  
 [<span data-ttu-id="4a6e7-130">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="4a6e7-130">LINQ to Objects</span></span>](https://go.microsoft.com/fwlink/?LinkID=150380)
