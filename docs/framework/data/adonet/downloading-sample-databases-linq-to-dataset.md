---
title: Descargar bases de datos de ejemplo (LINQ to DataSet)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8e19e51ecf4868d0d49e26b4aafd7e8b3840992d
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Descargar bases de datos de ejemplo (LINQ to DataSet)
Los ejemplos y tutoriales de la [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentación usar la base de datos de ejemplo AdventureWorks. Puede descargar este producto de forma gratuita del sitio de descarga de Microsoft. Los ejemplos y los tutoriales de la documentación de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] usan SQL Server como almacén de datos. SQL Server Express Edition, que está disponible de forma gratuita, también se puede usar como almacén de datos en lugar de SQL Server.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Descargar e instalar la base de datos de AdventureWorks  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>Para descargar e instalar la base de datos de ejemplo de AdventureWorks para SQL Server  
  
1.  Abra Internet Explorer.  
  
2.  Vaya a la [bases de datos de ejemplo y ejemplos de SQL Server 2005](http://go.microsoft.com/fwlink/?linkid=31046) sitio Web.  
  
3.  Siga las instrucciones para descargar la base de datos de ejemplo para el tipo de procesador (por ejemplo, AdventureWorksDB.msi) y guarde el archivo .MSI en su equipo local.  
  
4.  Si tiene una versión anterior de AdventureWorks instalada desde la descarga o durante la configuración de SQL Server, debe quitarla antes de ejecutar AdventureWorks.msi.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>Para quitar una descarga anterior de una base de datos de ejemplo de AdventureWorks  
  
1.  Quite la base de datos de AdventureWorks o AdventureWorksDW.  
  
2.  De **agregar o quitar programas**, seleccione **AdventureWorksDB** o **AdventureWorksBI** y haga clic en **quitar**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>Para quitar una base de datos de ejemplo de AdventureWorks instalada previamente durante la configuración  
  
1.  Quite la base de datos de AdventureWorks o AdventureWorksDW.  
  
2.  De **agregar o quitar programas**, seleccione **Microsoft SQL Server 2005** y haga clic en **cambio**.  
  
3.  De **selección de componentes**, seleccione **componentes de estación de trabajo** y, a continuación, haga clic en **siguiente**.  
  
4.  De **Bienvenido al Asistente para la instalación de SQL Server**, haga clic en **siguiente**.  
  
5.  De **comprobación de configuración del sistema**, haga clic en **siguiente**.  
  
6.  De **cambiar o quitar instancia**, haga clic en **cambiar componentes instalados**.  
  
7.  De **selección de características**, expanda la **documentación, ejemplos y bases de datos de ejemplo** nodo.  
  
8.  Seleccione **código y las aplicaciones de ejemplo**. Expanda **Sample Databases**, seleccione la base de datos de ejemplo que desea quitar y seleccione **característica completa no estará disponible**. Haga clic en **Siguiente**.  
  
9. Haga clic en **instalar** y finalice el Asistente de instalación.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>Para adjuntar los archivos de base de datos de ejemplo de AdventureWorks a una instancia de SQL Server  
  
1.  Después de que ha descargado el archivo de instalador de base de datos de ejemplo de archivo, haga doble clic en el **AdventureWorksDB.msi** archivo (o el archivo descargado) para instalar la base de datos. De forma predeterminada, la base de datos se instala en c:\Archivos de programa\Microsoft SQL Server\MSSQL.1\MSSQL\Data.  
  
2.  Adjunte los archivos de la base de datos de AdventureWorks a una instancia de SQL Server ejecutando el siguiente script SQLCMD o SQL Server Management Studio:  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Si ha instalado esos archivos en una unidad o en un directorio diferente, debe revisar las rutas de acceso correctamente antes de ejecutar el procedimiento almacenado `sp_attach_db`.  
  
## <a name="downloading-sql-server-express-edition"></a>Descargar SQL Server Express Edition  
 Los ejemplos y tutoriales de la [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sección usar SQL Server 2005 como almacén de datos pero se puede modificar para usar SQL Server Express Edition, en su lugar. SQL Server Express Edition está disponible gratuitamente y puede redistribuirse con aplicaciones. Si se utiliza Visual Studio, SQL Server Express Edition se incluye en las ediciones Pro y superiores.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>Para descargar e instalar SQL Server Express Edition  
  
1.  Inicie Internet Explorer.  
  
2.  Vaya a la [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) página de descarga.  
  
3.  Siga las instrucciones de instalación del sitio web.  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
