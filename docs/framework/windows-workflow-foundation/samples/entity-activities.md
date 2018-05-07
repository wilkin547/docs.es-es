---
title: Actividades de entidad
ms.date: 03/30/2017
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
ms.openlocfilehash: 96301c15b849749299e744a435068c3ec9be2e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="entity-activities"></a>Actividades de entidad
Este ejemplo muestra cómo utilizar ADO.NET Entity Framework con Windows Workflow Foundation para simplificar el acceso a datos.  
  
 ADO.NET Entity Framework permite a los desarrolladores de software trabajar con datos en forma de objetos específicos del dominio, propiedades y relaciones, como Customers, Orders, Order Details y las relaciones entre estas entidades. ADO.NET Entity Framework realiza esto proporcionando un nivel de abstracción que habilita la programación con un modelo de aplicación conceptual en lugar de programar directamente con un esquema de almacenamiento relacional. Para obtener más información acerca de ADO.NET Entity Framework, vea [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Este ejemplo utiliza la base de datos `Northwind` e incluye scripts para crear y quitar la base de datos `Northwind` (Setup.cmd y Cleanup.cmd). Los proyectos de este ejemplo incluyen un Entity Data Model basado en la base de datos `Northwind`. Para encontrar el modelo, abra el archivo `Northwind.edmx` que está incluido en el proyecto. Este es el modelo que define la forma de los objetos a los que se pueden tener acceso mediante ADO.NET Entity Framework.  
  
 En este ejemplo se incluyen las siguientes actividades:  
  
-   `EntitySQLQuery`: la actividad `EntitySQLQuery` le permite recuperar los objetos de la base de datos en función de una cadena de consulta de Entity SQL. Entity SQL es un lenguaje independiente del almacenamiento que es similar a SQL y permite especificar consultas basadas en el modelo conceptual y las entidades que forman una parte del modelo o del dominio. Para obtener más información sobre el lenguaje Entity SQL, consulte [lenguaje Entity SQL](http://go.microsoft.com/fwlink/?LinkId=165646).  
  
-   `EntityLinqQuery`: esta actividad permite recuperar objetos de la base de datos en función de una consulta o un predicado LINQ.  
  
-   `EntityAdd`: la actividad `EntityAdd` permite agregar una entidad o una colección de entidades a la base de datos.  
  
-   `EntityDelete`: la actividad `EntityDelete` permite eliminar una entidad o una colección de entidades de la base de datos.  
  
-   `ObjectContextScope`: las actividades mencionadas previamente solo se pueden utilizar dentro de una instancia de actividad `ObjectContextScope` contenedora. La actividad `ObjectContextScope` configura la conexión a la base de datos. Requiere una cadena de conexión (que se pasa o se recupera utilizando un valor de archivo de configuración). La actividad `ObjectContextScope` simplifica la realización de un grupo de operaciones relacionadas en entidades. Dado que este ámbito mantiene una conexión activa, es un ámbito No Persist. Además, cuando la actividad `ObjectContextScope` sale, cualquier cambio que se realice en los objetos recuperados mediante las actividades de entidad dentro de ese ámbito se conserva automáticamente en la base de datos y no se requiere ninguna acción explícita o subsiguiente para guardar los objetos en la base de datos.  
  
## <a name="using-the-entity-activities"></a>Utilizar las actividades de entidad  
 Los siguientes fragmentos de código muestran cómo utilizar las actividades de entidad presentadas en este ejemplo.  
  
### <a name="entitysql"></a>EntitySql  
 El siguiente fragmento de código muestra cómo consultar todos los clientes en London ordenados por nombre y cómo recorrer en iteración la lista de clientes.  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>();  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>();  
  
// create and return the workflow  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
        {  
            Activities =   
                {               
                    new WriteLine { Text = "Executing query" },                            
                    // query for all customers that are in london   
                    new EntitySqlQuery<Customer>  
                    {  
                        EntitySql =  @"SELECT VALUE Customer   
                                        FROM NorthwindEntities.Customers AS Customer   
                                        WHERE Customer.City = 'London'   
                                        ORDER BY Customer.ContactName",  
                        Result = londonCustomers  
                    },  
  
                    // iterate through the list of customers and display them   
                    new ForEach<Customer>  
                    {                                      
                        Values = londonCustomers,  
                        Body = new ActivityAction<Customer>  
                        {  
                            Argument = iterationVariable,  
                            Handler = new WriteLine   
                            {   
                                  Text = new InArgument<String>(e =>    
                                              iterationVariable.Get(e).ContactName)   
                            }  
                        }  
                    }  
                }  
        }                 
};     
```  
  
### <a name="entitylinqquery"></a>EntityLinqQuery  
 El siguiente fragmento de código muestra cómo consultar todos los clientes en London y cómo recorrer en iteración la lista de clientes resultante.  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>() { Name = "LondonCustomers" };  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>() { Name = "iterationVariable" };  
  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // return all the customers that match with the provided Linq predicate  
            new EntityLinqQuery<Customer>  
            {   
                Predicate = new LambdaValue<Func<Customer, bool>>(  
                          ctx => new Func<Customer, bool>(c => c.City.Equals("London"))),                              
                Result = londonCustomers  
            },  
  
            // iterate through the list of customers and display in the console  
            new ForEach<Customer>  
            {                                      
                Values = londonCustomers,  
                Body = new ActivityAction<Customer>  
                {  
                    Argument = iterationVariable,  
                    Handler = new WriteLine   
                    {   
                        Text = new InArgument<String>(e =>   
                                      iterationVariable.Get(e).ContactName)   
                    }  
                }  
            }  
        }  
    }  
};  
```  
  
### <a name="entityadd"></a>EntityAdd  
 El siguiente fragmento de código muestra cómo agregar un registro de detalle de pedido a un pedido existente.  
  
```  
Variable<IEnumerable<Order>> orders = new Variable<IEnumerable<Order>>();  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();  
Variable<Order> order = new Variable<Order>();  
Variable<OrderDetail> orderDetail = new Variable<OrderDetail>();              
  
return new ObjectContextScope  
{  
    Variables = { order, orders, orderDetail, orderDetails },  
    ContainerName = "NorthwindEntities",  
    ConnectionString = new InArgument<string>(connStr),                  
    Body = new Sequence  
    {                      
        Activities =   
        {                            
           // get the order where we want to add the detail  
           new EntitySqlQuery<Order>  
           {  
               EntitySql =    
                    @"SELECT VALUE [Order]  
                      FROM NorthwindEntities.Orders as [Order]  
                      WHERE Order.OrderID == 10249",  
               Result = orders  
           },  
  
           // store the order in a variable  
           new Assign<Order>   
           {  
               To = new OutArgument<Order>(order),  
               Value = new InArgument<Order>(c => orders.Get(c).First<Order>())  
           },  
  
           // add the detail to the order  
           new EntityAdd<OrderDetail>  
           {  
               Entity = new InArgument<OrderDetail>(c =>   
                                         new OrderDetail {   
                                                  OrderID=10249, ProductID=11,   
                                                  Quantity=1, UnitPrice = 15,   
                                                  Discount = 0, Order = order.Get(c) })  
           }  
        }  
    }  
};  
```  
  
### <a name="entitydelete"></a>EntityDelete  
 El siguiente fragmento de código muestra cómo eliminar un registro de detalle de pedido existente en un pedido (si existe).  
  
```  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();              
  
return new ObjectContextScope  
{  
    Variables = { orderDetails },  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // find the entitiy to be deleted (order detail for product 11 in order 10249)  
            new EntitySqlQuery<OrderDetail>  
            {  
                EntitySql = @"SELECT VALUE OrderDetail  
                                FROM NorthwindEntities.OrderDetails as OrderDetail  
                               WHERE OrderDetail.OrderID == 10249   
                                 AND OrderDetail.ProductID == 11",  
                Result = orderDetails  
            },  
  
            // if the order detail is found, delete it, otherwise, display a message  
            new If  
            {  
                Condition = new InArgument<bool>(c=>orderDetails.Get(c).Count() > 0),  
                Then = new Sequence  
                {   
                    Activities =   
                    {                                      
                        new EntityDelete<OrderDetail>  
                        {  
                            Entity = new InArgument<OrderDetail>(c =>   
                                              orderDetails.Get(c).First<OrderDetail>())  
                        },  
                    }  
                },                              
                Else = new WriteLine { Text = "Order Detail for Deleting not found" }                              
            }                                                  
        }  
    }  
};  
```  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
 Debe crear la base de datos `Northwind` en su instancia local de SQL Server Express antes de ejecutar este ejemplo.  
  
#### <a name="to-set-up-the-northwind-database"></a>Para configurar la base de datos Northwind  
  
1.  Abra un símbolo del sistema.  
  
2.  En la nueva ventana del símbolo del sistema, navegue hasta la carpeta EntityActivities\CS.  
  
3.  Tipo `setup.cmd` y presione ENTRAR.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra el archivo de solución EntityActivities.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
 Después de ejecutar este ejemplo, puede que desee quitar la base de datos `Northwind`.  
  
#### <a name="to-uninstall-the-northwind-database"></a>Para desinstalar la base de datos Northwind  
  
1.  Abra un símbolo del sistema.  
  
2.  En la nueva ventana del símbolo del sistema, navegue hasta la carpeta EntityActivities\CS.  
  
3.  Tipo `cleanup.cmd` y presione ENTRAR.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`