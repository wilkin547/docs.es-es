---
title: "LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# LINQ to SQL
En este ejemplo se muestra cómo crear una actividad para utilizar las entidades de consulta de LINQ to SQL de las tablas en bases de datos de SQL Server.  
  
> [!IMPORTANT]
>  Puede que los ejemplos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<unidadDeInstalación>:\Samples\WCFWFCardspace`  
>   
>  Si este directorio no existe, haga clic en el vínculo de descarga de ejemplo en la parte superior de esta página.Tenga en cuenta que este vínculo descarga e instala todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e [!INCLUDE[infocard](../../../../includes/infocard-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## Detalles de la actividad FindInSqlTable  
 Esta actividad permite a los usuarios consultar entidades de las tablas de una base de datos utilizando LINQ to SQL.Los usuarios de la actividad también pueden proporcionar un predicado de LINQ en forma de expresión lambda para filtrar los resultados.Si no se proporciona ningún predicado, se devuelve la tabla completa.En la siguiente tabla se detallan las propiedades y los valores devueltos de la actividad.  
  
|Propiedad o valor devuelto|Descripción|  
|--------------------------------|-----------------|  
|Propiedad `Collection`|Propiedad necesaria que especifica la colección de origen.|  
|Propiedad `Predicate`|Propiedad necesaria que especifica el filtro para la colección en forma de expresión lambda.|  
|Valor devuelto|La colección filtrada.|  
  
## Ejemplo de código que utiliza la actividad personalizada  
 El siguiente ejemplo de código utiliza la actividad personalizada `FindInSqlTable` para encontrar todas las filas de una tabla de SQL Server denominada `Employee` donde la columna `Role` es igual a `SDE`.  
  
```csharp  
  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
  
```  
  
#### Para utilizar este ejemplo  
  
1.  Abra un símbolo del sistema.  
  
2.  Desplácese hasta la carpeta que contiene este ejemplo.  
  
3.  Ejecute el archivo de comandos Setup.cmd.  
  
    > [!NOTE]
    >  El script Setup.cmd intenta instalar la base de datos de ejemplo en la versión SQL Server Express del equipo local.Si desea instalarla en otra instancia de SQL Server, edite Setup.cmd.  
  
     El script Setup.cmd realiza las siguientes acciones:  
  
    -   Crea una base de datos llamada LinqToSqlSample.  
  
    -   Crea una tabla Roles.  
  
    -   Crea una tabla Employees.  
  
    -   Inserta 3 registros en la tabla Roles.  
  
    -   Inserta 12 registros en la tabla Employees.  
  
4.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LinqToSQL.sln.  
  
5.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
6.  Presione F5 para ejecutar la solución.  
  
#### Para desinstalar la base de datos de ejemplo LinqToSql  
  
1.  Abra un símbolo del sistema.  
  
2.  Desplácese hasta la carpeta que contiene este ejemplo.  
  
3.  Ejecute el archivo de comandos Cleanup.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## Vea también  
 [LINQ to SQL](http://go.microsoft.com/fwlink/?LinkId=150376)   
 [Introducción \(LINQ to SQL\)](http://go.microsoft.com/fwlink/?LinkId=150377)