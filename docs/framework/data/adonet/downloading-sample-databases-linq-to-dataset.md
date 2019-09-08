---
title: Descargar bases de datos de ejemplo (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: c67ee699cf594f476a728c7345b47b0c32dea7ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795179"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Descargar bases de datos de ejemplo (LINQ to DataSet)
En los ejemplos y los tutoriales de la documentación de LINQ to DataSet se usa la base de datos de ejemplo AdventureWorks. Puede descargar este producto de forma gratuita del sitio de descarga de Microsoft. Los ejemplos y los tutoriales de la documentación de LINQ to DataSet usan SQL Server como almacén de datos. SQL Server Express Edition, que está disponible de forma gratuita, también se puede usar como almacén de datos en lugar de SQL Server.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Descargar e instalar la base de datos de AdventureWorks  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>Para descargar e instalar la base de datos de ejemplo de AdventureWorks para SQL Server  
  
1. Abra Internet Explorer.  
  
2. Vaya al sitio Web [ejemplos de SQL Server 2005 y bases de datos de ejemplo](https://go.microsoft.com/fwlink/?linkid=31046) .  
  
3. Siga las instrucciones para descargar la base de datos de ejemplo para el tipo de procesador (por ejemplo, AdventureWorksDB.msi) y guarde el archivo .MSI en su equipo local.  
  
4. Si tiene una versión anterior de AdventureWorks instalada desde la descarga o durante la configuración de SQL Server, debe quitarla antes de ejecutar AdventureWorks.msi.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>Para quitar una descarga anterior de una base de datos de ejemplo de AdventureWorks  
  
1. Quite la base de datos de AdventureWorks o AdventureWorksDW.  
  
2. En **Agregar o quitar programas**, seleccione **AdventureWorksDB** o **AdventureWorksBI** y haga clic en **quitar**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>Para quitar una base de datos de ejemplo de AdventureWorks instalada previamente durante la configuración  
  
1. Quite la base de datos de AdventureWorks o AdventureWorksDW.  
  
2. En **Agregar o quitar programas**, seleccione **Microsoft SQL Server 2005** y haga clic en **cambiar**.  
  
3. En **selección de componentes**, seleccione componentes de la **estación de trabajo** y, a continuación, haga clic en **siguiente**.  
  
4. En **la Página principal del Asistente para la instalación de SQL Server**, haga clic en **siguiente**.  
  
5. En **comprobación de la configuración del sistema**, haga clic en **siguiente**.  
  
6. En **cambiar o quitar instancia**, haga clic en **cambiar componentes instalados**.  
  
7. En **selección de características**, expanda el nodo **documentación, ejemplos y bases de datos de ejemplo** .  
  
8. Seleccione **código y aplicaciones de ejemplo**. Expanda bases de datos de **ejemplo**, seleccione la base de datos de ejemplo que se va a quitar y seleccione la **característica completa no estará disponible**. Haga clic en **Next**.  
  
9. Haga clic en **instalar** y finalice el Asistente para la instalación.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>Para adjuntar los archivos de base de datos de ejemplo de AdventureWorks a una instancia de SQL Server  
  
1. Una vez descargado el archivo del instalador de la base de datos de ejemplo de archivo, haga doble clic en el archivo **AdventureWorksDB. msi** (o en el archivo que descargó) para instalar la base de datos. De forma predeterminada, la base de datos se instala en c:\Archivos de programa\Microsoft SQL Server\MSSQL.1\MSSQL\Data.  
  
2. Adjunte los archivos de la base de datos de AdventureWorks a una instancia de SQL Server ejecutando el siguiente script SQLCMD o SQL Server Management Studio:  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Si ha instalado esos archivos en una unidad o en un directorio diferente, debe revisar las rutas de acceso correctamente antes de ejecutar el procedimiento almacenado `sp_attach_db`.  
  
## <a name="downloading-sql-server-express-edition"></a>Descargar SQL Server Express Edition  
 En los ejemplos y los tutoriales de la sección LINQ to DataSet se usa SQL Server 2005 como almacén de datos, pero se pueden modificar para usar SQL Server Express Edition, en su lugar. SQL Server Express Edition está disponible gratuitamente y puede redistribuirse con aplicaciones. Si usa Visual Studio, SQL Server Express Edition se incluye en las ediciones Pro y superior.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>Para descargar e instalar SQL Server Express Edition  
  
1. Inicie Internet Explorer.  
  
2. Vaya a la página de descarga de [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) .  
  
3. Siga las instrucciones de instalación del sitio web.  
  
## <a name="see-also"></a>Vea también

- [Introducción](getting-started-linq-to-dataset.md)
