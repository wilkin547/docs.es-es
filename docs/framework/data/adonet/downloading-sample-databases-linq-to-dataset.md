---
title: "Descargar bases de datos de ejemplo (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Descargar bases de datos de ejemplo (LINQ to DataSet)
Los ejemplos y los tutoriales de la documentación de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] usan la base de datos de ejemplo de AdventureWorks.  Puede descargar este producto de forma gratuita del sitio de descarga de Microsoft. Los ejemplos y los tutoriales de la documentación de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] usan SQL Server como almacén de datos.  SQL Server Express Edition, que está disponible de forma gratuita, también se puede usar como almacén de datos en lugar de SQL Server.  
  
## Descargar e instalar la base de datos de AdventureWorks  
  
#### Para descargar e instalar la base de datos de ejemplo de AdventureWorks para SQL Server  
  
1.  Abra Internet Explorer.  
  
2.  Vaya al sitio web de [ejemplos y bases de datos de ejemplo de SQL Server 2005](http://go.microsoft.com/fwlink/?linkid=31046).  
  
3.  Siga las instrucciones para descargar la base de datos de ejemplo para el tipo de procesador \(por ejemplo, AdventureWorksDB.msi\) y guarde el archivo .MSI en su equipo local.  
  
4.  Si tiene una versión anterior de AdventureWorks instalada desde la descarga o durante la configuración de SQL Server, debe quitarla antes de ejecutar AdventureWorks.msi.  
  
#### Para quitar una descarga anterior de una base de datos de ejemplo de AdventureWorks  
  
1.  Quite la base de datos de AdventureWorks o AdventureWorksDW.  
  
2.  En **Agregar o quitar programas**, seleccione **AdventureWorksDB** o **AdventureWorksBI** y haga clic en **Quitar**.  
  
#### Para quitar una base de datos de ejemplo de AdventureWorks instalada previamente durante la configuración  
  
1.  Quite la base de datos de AdventureWorks o AdventureWorksDW.  
  
2.  En **Agregar o quitar programas**, seleccione **Microsoft SQL Server 2005** y haga clic en **Cambiar**.  
  
3.  En **Selección de componentes**, seleccione **Componentes de la estación de trabajo** y haga clic en **Siguiente**.  
  
4.  En la **página de bienvenida al asistente para la instalación de SQL Server**, haga clic en **Siguiente**.  
  
5.  En **Comprobación de configuración del sistema**, haga clic en **Siguiente**.  
  
6.  En **Cambiar o quitar instancia**, haga clic en **Cambiar componentes instalados**.  
  
7.  En **Selección de características**, expanda el nodo **Documentación, ejemplos y bases de datos de ejemplo**.  
  
8.  Seleccione **Código y aplicaciones de ejemplo**.  Expanda **Bases de datos de ejemplo**, seleccione la base de datos de ejemplo que desea quitar y seleccione **La característica completa no estará disponible**.  Haga clic en **Siguiente**.  
  
9. Haga clic en **Instalar** y finalice el asistente para la instalación.  
  
#### Para adjuntar los archivos de base de datos de ejemplo de AdventureWorks a una instancia de SQL Server  
  
1.  Cuando se haya descargado el archivo instalador de la base de datos de ejemplo, haga doble clic en el archivo **AdventureWorksDB.msi** \(o el archivo que ha descargado\) para instalar la base de datos.  De forma predeterminada, la base de datos se instala en c:\\Archivos de programa\\Microsoft SQL Server\\MSSQL.1\\MSSQL\\Data.  
  
2.  Adjunte los archivos de la base de datos de AdventureWorks a una instancia de SQL Server ejecutando el siguiente script SQLCMD o SQL Server Management Studio:  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Si ha instalado esos archivos en una unidad o en un directorio diferente, debe revisar las rutas de acceso correctamente antes de ejecutar el procedimiento almacenado `sp_attach_db`.  
  
## Descargar SQL Server Express Edition  
 Los ejemplos y los tutoriales de la sección [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] usan SQL Server 2005 como origen de datos pero se pueden modificar para usar SQL Server Express Edition, en su lugar.  SQL Server Express Edition está disponible gratuitamente y puede redistribuirse con aplicaciones.  Si está usando [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], se incluye SQL Server Express Edition en las ediciones Pro y superiores.  
  
#### Para descargar e instalar SQL Server Express Edition  
  
1.  Inicie Internet Explorer.  
  
2.  Vaya a la página de descarga de [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070).  
  
3.  Siga las instrucciones de instalación del sitio web.  
  
## Vea también  
 [Introducción](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)