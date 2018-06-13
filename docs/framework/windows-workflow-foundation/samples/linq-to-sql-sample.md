---
title: LINQ to SQL ejemplo
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 3cfcaf3de1a22b8bb5505083f127a9888b99dbd8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806723"
---
# <a name="linq-to-sql-sample"></a>LINQ to SQL ejemplo
En este ejemplo se muestra cómo crear una actividad para utilizar las entidades de consulta de LINQ to SQL de las tablas en bases de datos de SQL Server.  
  
> [!IMPORTANT]
>  Puede que los ejemplos WCF ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  Si este directorio no existe, haga clic en el vínculo de descarga de ejemplo en la parte superior de esta página. Tenga en cuenta que este vínculo descarga e instala todos los [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, y [!INCLUDE[infocard](../../../../includes/infocard-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a>Detalles de la actividad FindInSqlTable  
 Esta actividad permite a los usuarios consultar entidades de las tablas de una base de datos utilizando LINQ to SQL. Los usuarios de la actividad también pueden proporcionar un predicado de LINQ en forma de expresión lambda para filtrar los resultados. Si no se proporciona ningún predicado, se devuelve la tabla completa. En la siguiente tabla se detallan las propiedades y los valores devueltos de la actividad.  
  
|Propiedad o valor devuelto|Descripción|  
|------------------------------|-----------------|  
|Propiedad `Collection`|Propiedad necesaria que especifica la colección de origen.|  
|Propiedad `Predicate`|Propiedad necesaria que especifica el filtro para la colección en forma de expresión lambda.|  
|Valor devuelto|La colección filtrada.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>Ejemplo de código que utiliza la actividad personalizada  
 El siguiente ejemplo de código utiliza la actividad personalizada `FindInSqlTable` para encontrar todas las filas de una tabla de SQL Server denominada `Employee` donde la columna `Role` es igual a `SDE`.  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra un símbolo del sistema.  
  
2.  Desplácese hasta la carpeta que contiene este ejemplo.  
  
3.  Ejecute el archivo de comandos Setup.cmd.  
  
    > [!NOTE]
    >  El script Setup.cmd intenta instalar la base de datos de ejemplo en la versión SQL Server Express del equipo local. Si desea instalarla en otra instancia de SQL Server, edite Setup.cmd.  
  
     El script Setup.cmd realiza las siguientes acciones:  
  
    -   Crea una base de datos llamada LinqToSqlSample.  
  
    -   Crea una tabla Roles.  
  
    -   Crea una tabla Employees.  
  
    -   Inserta 3 registros en la tabla Roles.  
  
    -   Inserta 12 registros en la tabla Employees.  
  
4.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LinqToSQL.sln.  
  
5.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
6.  Presione F5 para ejecutar la solución.  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a>Para desinstalar la base de datos de ejemplo LinqToSql  
  
1.  Abra un símbolo del sistema.  
  
2.  Desplácese hasta la carpeta que contiene este ejemplo.  
  
3.  Ejecute el archivo de comandos Cleanup.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a>Vea también  
 [LINQ to SQL](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [Introducción (LINQ to SQL)](http://go.microsoft.com/fwlink/?LinkId=150377)
