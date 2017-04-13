---
title: "Actividad de LINQ to Objects | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Actividad de LINQ to Objects
En este ejemplo se muestra cómo crear una actividad para utilizar LINQ to Objects para consultar elementos de una colección.  
  
## Detalles de la actividad FindInCollection  
 Esta actividad permite a los usuarios consultar elementos de las colecciones en memoria mediante LINQ to Objects.Debe proporcionar un predicado de LINQ en forma de una expresión lambda para filtrar los resultados.Esta actividad se puede utilizar junto con las actividades <xref:System.Activities.Statements.AddToCollection%601>.  
  
 En la siguiente tabla se detallan las propiedades y los valores devueltos de la actividad.  
  
|Propiedad o valor devuelto|Descripción|  
|--------------------------------|-----------------|  
|Propiedad `Collection`|Propiedad necesaria que especifica la colección de origen.|  
|Propiedad `Predicate`|Propiedad necesaria que especifica el filtro para la colección en forma de expresión lambda.|  
|Valor devuelto|La colección filtrada.|  
  
## Ejemplo de código que utiliza la actividad personalizada  
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
  
#### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LinqToObjects.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## Vea también  
 [Expresiones Lambda \(Guía de programación de C\#\)](http://go.microsoft.com/fwlink/?LinkId=150381)   
 [LINQ to Objects](http://go.microsoft.com/fwlink/?LinkID=150380)