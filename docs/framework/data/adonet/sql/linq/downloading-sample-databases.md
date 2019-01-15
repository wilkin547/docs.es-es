---
title: Obtener las bases de datos de SQL Server de ejemplo para obtener ejemplos de código ADO.NET
description: Descargar las bases de datos de SQL Server de ejemplo utilizados en los ejemplos de código en la documentación de ADO.NET, así como herramientas de administración y SQL Server
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 5580f06f3d28ed6d70f75b619498ac8de7bc3326
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307297"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET

Un número de ejemplos y tutoriales en la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación usar bases de datos de ejemplo SQL Server y SQL Server Express. Puede descargar estos productos de forma gratuita de Microsoft.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Obtenga la base de datos de ejemplo Northwind para SQL Server

Descargue el script `instnwnd.sql` desde el repositorio de GitHub siguiente para crear y cargar la base de datos de ejemplo Northwind para SQL Server:

[Northwind y pubs bases de datos de ejemplo para Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Para poder usar la base de datos Northwind, tendrá que ejecutar los datos descargados `instnwnd.sql` archivo de script para volver a crear la base de datos en una instancia de SQL Server mediante el uso de [SQL Server Management Studio](#get_ssms) u otra herramienta similar. Siga las instrucciones del archivo Léame del repositorio.

> [!TIP]
> Si busca la base de datos Northwind para Microsoft Access, consulte [instalar la base de datos de ejemplo Northwind para Microsoft Access](#northwind_access).

## <a name="northwind_access"></a> Obtener la base de datos de ejemplo Northwind para Microsoft Access

La base de datos de ejemplo Northwind para Microsoft Access no está disponible en Microsoft Download Center. Para instalar Northwind directamente desde dentro de acceso, realice lo siguiente:

1. Abre el acceso.

1. ENTRAR **Northwind** en el **buscar plantillas en línea** cuadro y, a continuación, seleccione **ENTRAR**.

1. En la pantalla de resultados, seleccione **Northwind**. Se abre una nueva ventana con una descripción de la base de datos Northwind.

1. En la ventana nueva, en el **nombre de archivo** texto cuadro, proporcione un nombre de archivo para su copia de la base de datos Northwind.

1. Seleccione **Crear**. Acceso a descargas de la base de datos Northwind y prepara el archivo.

1. Una vez completado este proceso, se abre la base de datos con una pantalla de bienvenida.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Obtenga la base de datos de ejemplo AdventureWorks para SQL Server

Descargue la base de datos de ejemplo AdventureWorks para SQL Server desde el repositorio de GitHub siguiente:

[Bases de datos de ejemplo de AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Después de descargar uno de la copia de seguridad de base de datos (\*.bak) de los archivos, restaurar la copia de seguridad a una instancia de SQL Server mediante SQL Server Management Studio (SSMS). Consulte [tener SQL Server Management Studio](#get_ssms).

## <a name="get_ssms"></a> Obtener SQL Server Management Studio
Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS). Descarga de SSMS desde la página siguiente:

[Descargar SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio. En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), conectarse a la base de datos **Explorador de objetos de SQL Server**, o crear una conexión de datos a la base de datos en **Explorador de servidores**. Abrir estos paneles explorador desde el **vista** menú.

## <a name="get_sql"></a> Obtener SQL Server Express

SQL Server Express es una edición gratuita, nivel de entrada de SQL Server que se puede redistribuir con las aplicaciones. Descargar SQL Server Express desde la página siguiente:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Si usas [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB se incluye en la edición gratuita Community de Visual Studio, así como las ediciones Professional y versiones posteriores.  

## <a name="see-also"></a>Vea también

- [Introducción](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
