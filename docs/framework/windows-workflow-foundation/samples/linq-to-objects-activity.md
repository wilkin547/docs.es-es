---
title: Actividad de LINQ to Objects
ms.date: 03/30/2017
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
ms.openlocfilehash: e2c2be52a88d8f9a886f0e59c027e1d6c737497c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="linq-to-objects-activity"></a>Actividad de LINQ to Objects
En este ejemplo se muestra cómo crear una actividad para utilizar LINQ to Objects para consultar elementos de una colección.  
  
## <a name="activity-details-for-findincollection"></a>Detalles de la actividad FindInCollection  
 Esta actividad permite a los usuarios consultar elementos de las colecciones en memoria mediante LINQ to Objects. Debe proporcionar un predicado de LINQ en forma de una expresión lambda para filtrar los resultados. Esta actividad se puede utilizar junto con las actividades <xref:System.Activities.Statements.AddToCollection%601>.  
  
 En la siguiente tabla se detallan las propiedades y los valores devueltos de la actividad.  
  
|Propiedad o valor devuelto|Descripción|  
|------------------------------|-----------------|  
|Propiedad `Collection`|Propiedad necesaria que especifica la colección de origen.|  
|Propiedad `Predicate`|Propiedad necesaria que especifica el filtro para la colección en forma de expresión lambda.|  
|Valor devuelto|La colección filtrada.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>Ejemplo de código que utiliza la actividad personalizada  
 El siguiente ejemplo de código utiliza la actividad personalizada `FindInCollection` para localizar todas las filas de una colección de empleados que tienen una propiedad `Role` establecida en `Manager` y la propiedad `Location` establecida en `Redmond`.  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 El siguiente código muestra cómo crear un programa de flujo de trabajo que utiliza actividad FindInCollection personalizada, las actividades <xref:System.Activities.Statements.AddToCollection%601> y <xref:System.Activities.Statements.ForEach%601> para rellenar una colección con empleados, localizar todos los empleados que tienen roles de desarrollador y se encuentran en Redmond y, a continuación, recorrer en iteración la lista resultante.  
  
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
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LinqToObjects.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a>Vea también  
 [Expresiones lambda (Guía de programación de C#)](http://go.microsoft.com/fwlink/?LinkId=150381)  
 [LINQ to Objects](http://go.microsoft.com/fwlink/?LinkID=150380)
