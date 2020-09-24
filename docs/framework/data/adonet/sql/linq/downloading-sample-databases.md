---
title: Obtener las bases de datos de ejemplo SQL Server para ejemplos de código de ADO.NET
description: Descargue las bases de datos de SQL Server de ejemplo usadas en los ejemplos de código de la documentación de ADO.NET, así como herramientas de SQL Server y administración
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: f7c0d1eb0089a6bfabc92e1deecf563c3e59cc6a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156061"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Obtener las bases de datos de ejemplo para los ejemplos de código de ADO.NET

Una serie de ejemplos y tutoriales en la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación de utilizan bases de datos de ejemplo SQL Server y SQL Server Express. Puede descargar estos productos de forma gratuita de Microsoft.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Obtener la base de datos de ejemplo Northwind para SQL Server

Descargue el script `instnwnd.sql` desde el siguiente repositorio de github para crear y cargar la base de datos de ejemplo Northwind para SQL Server:

[Bases de datos de ejemplo Northwind y pubs para Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Antes de poder usar la base de datos Northwind, tiene que ejecutar el archivo de script descargado `instnwnd.sql` para volver a crear la base de datos en una instancia de SQL Server mediante [SQL Server Management Studio](#get_ssms) u otra herramienta similar. Siga las instrucciones del archivo Léame del repositorio.

> [!TIP]
> Si está buscando la base de datos Northwind para Microsoft Access, vea [instalar la base de datos de ejemplo Northwind para Microsoft Access](#northwind_access).

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a> Obtención de la base de datos de ejemplo Northwind para Microsoft Access

La base de datos de ejemplo Northwind para Microsoft Access no está disponible en el centro de descarga de Microsoft. Para instalar Northwind directamente desde el acceso, haga lo siguiente:

1. Abra el acceso.

1. Escriba **Northwind** en el cuadro **buscar plantillas en línea** y, a continuación, seleccione **entrar**.

1. En la pantalla resultados, seleccione **Northwind**. Se abre una nueva ventana con una descripción de la base de datos Northwind.

1. En la nueva ventana, en el cuadro de texto **nombre de archivo** , proporcione un nombre de archivo para la copia de la base de datos Northwind.

1. Seleccione **Crear**. Access descarga la base de datos Northwind y prepara el archivo.

1. Una vez completado este proceso, la base de datos se abre con una pantalla de bienvenida.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Obtener la base de datos de ejemplo AdventureWorks para SQL Server

Descargue la base de datos de ejemplo AdventureWorks para SQL Server desde el siguiente repositorio de GitHub:

[Bases de datos de ejemplo AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Después de descargar uno de los archivos de copia de seguridad de base de datos ( \* . bak), restaure la copia de seguridad en una instancia de SQL Server mediante SQL Server Management Studio (SSMS). Vea [obtener SQL Server Management Studio](#get_ssms).

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a> Obtener SQL Server Management Studio

Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS). Descargue SSMS en la página siguiente:

[Descarga de SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)

También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio. En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), conéctese a la base de datos desde **Explorador de objetos de SQL Server**, o cree una conexión de datos a la base de datos en **Explorador de servidores**. Abra estos paneles del explorador en el menú **Ver** .

## <a name="get-sql-server-express"></a><a name="get_sql"></a> Obtener SQL Server Express

SQL Server Express es una edición gratuita de nivel de entrada de SQL Server que se puede redistribuir con las aplicaciones. Descargue SQL Server Express de la siguiente página:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Si utiliza [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB se incluye en la edición gratuita Community de Visual Studio, así como en las ediciones Professional y superior.  

## <a name="see-also"></a>Vea también

- [Introducción](getting-started.md)
