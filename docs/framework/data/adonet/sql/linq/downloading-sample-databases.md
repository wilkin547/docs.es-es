---
title: Obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET
description: Descargar las bases de datos de ejemplo utilizados en los ejemplos de código en la documentación de ADO.NET, así como herramientas de administración y SQL Server
ms.date: 10/12/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 75ae1895d683b669f51b33130fc2f47010e39814
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347532"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET

Un número de ejemplos y tutoriales en la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación usar bases de datos y SQL Server Express. Puede descargar estos productos de forma gratuita de Microsoft.

## <a name="get-the-adventureworks-sample-database"></a>Obtener la base de datos de ejemplo AdventureWorks

Descargue la base de datos de ejemplo AdventureWorks desde el repositorio de GitHub siguiente:

[Bases de datos de ejemplo de AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Después de descargar uno de la copia de seguridad de base de datos (\*.bak) de los archivos, restaurar la copia de seguridad a una instancia de SQL Server mediante SQL Server Management Studio (SSMS). Consulte [tener SQL Server Management Studio](#get_ssms).

## <a name="get-the-northwind-sample-database"></a>Obtener la base de datos de ejemplo Northwind

Descargue la base de datos de ejemplo Northwind desde la página siguiente en Microsoft Download Center:

[Bases de datos de ejemplo Pubs y Northwind](https://go.microsoft.com/fwlink?linkid=64296)

Una vez descargado el archivo, haga doble clic en el archivo para extraer las bases de datos y los scripts. De forma predeterminada, los archivos se instalan en la carpeta `<drive>:\SQL Server 2000 Sample Databases`.

Para poder usar la base de datos Northwind, que debe hacer una de las siguientes acciones:

- Volver a crear la base de datos en una instancia de SQL Server ejecutando el `instnwnd.sql` archivo de script en la carpeta de instalación.

- Adjuntar el `northwnd.mdf` archivo con sus correspondientes `*.ldf` archivo de registro a una instancia de SQL Server.

## <a name="get_sql"></a> Obtener SQL Server Express

SQL Server Express es una edición gratuita, nivel de entrada de SQL Server que se puede redistribuir con las aplicaciones. Descargar SQL Server Express desde la página siguiente:
  
[Ediciones de SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express)

Si usas [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB se incluye en la edición Community, así como las ediciones Professional y versiones posteriores.  

## <a name="get_ssms"></a> Obtener SQL Server Management Studio
Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS). Descarga de SSMS desde la página siguiente:

[Descargar SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio. En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), conectarse a la base de datos **Explorador de objetos de SQL Server**, o crear una conexión de datos a la base de datos en **Explorador de servidores**. Abrir estos paneles explorador desde el **vista** menú.
  
## <a name="see-also"></a>Vea también

- [Introducción](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
