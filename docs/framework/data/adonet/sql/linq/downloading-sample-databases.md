---
title: Obtenga las bases de datos de SQL Server de ejemplo para ADO.NET ejemplos de código
description: Descargue las bases de datos de SQL Server de ejemplo utilizadas en los ejemplos de código de la documentación de ADO.NET, así como SQL Server y las herramientas de administración
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148392"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Obtenga las bases de datos de ejemplo para ejemplos de código ADO.NET

Varios ejemplos y tutoriales [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de la documentación usan bases de datos de SQL Server de ejemplo y SQL Server Express. Puede descargar estos productos de forma gratuita desde Microsoft.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Obtenga la base de datos de ejemplo Northwind para SQL Server

Descargue el `instnwnd.sql` script del siguiente repositorio GitHub para crear y cargar la base de datos de ejemplo Northwind para SQL Server:

[Bases de datos de ejemplo Northwind y pubs para Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Para poder usar la base de datos Northwind, debe ejecutar el archivo de script descargado `instnwnd.sql` para volver a crear la base de datos en una instancia de SQL Server mediante SQL Server Management [StudioSQL Server Management Studio](#get_ssms) o una herramienta similar. Siga las instrucciones del archivo Léame del repositorio.

> [!TIP]
> Si está buscando la base de datos Northwind para Microsoft Access, consulte Instalar la base de datos de [ejemplo Northwind para Microsoft Access](#northwind_access).

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a>Obtenga la base de datos de ejemplo Northwind para Microsoft Access

La base de datos de ejemplo Northwind para Microsoft Access no está disponible en el Centro de descarga de Microsoft. Para instalar Northwind directamente desde Access, haga lo siguiente:

1. Abra Acceso.

1. Escriba **Northwind** en el cuadro **Buscar plantillas en línea** y, a continuación, seleccione **Intro**.

1. En la pantalla de resultados, seleccione **Northwind**. Se abre una nueva ventana con una descripción de la base de datos Northwind.

1. En la nueva ventana, en el cuadro de texto **Nombre** de archivo, proporcione un nombre de archivo para la copia de la base de datos Northwind.

1. Seleccione **Crear**. Access descarga la base de datos Northwind y prepara el archivo.

1. Una vez completado este proceso, la base de datos se abre con una pantalla de bienvenida.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Obtenga la base de datos de ejemplo AdventureWorks para SQL Server

Descargue la base de datos de ejemplo AdventureWorks para SQL Server desde el siguiente repositorio GitHub:

[Bases de datos de ejemplo AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Después de descargar uno\*de los archivos de copia de seguridad de base de datos (.bak), restaure la copia de seguridad en una instancia de SQL Server mediante SQL Server Management Studio (SSMS). Consulte [Obtener SQL Server Management Studio](#get_ssms).

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a>Obtenga SQL Server Management Studio
Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS). Descargue SSMS desde la página siguiente:

[Descarga de SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)

También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio. En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), conéctese a la base de datos desde el Explorador de objetos de SQL **ServerSQL Server**o cree una conexión de datos a la base de datos en el **Explorador**de servidores . Abra estos paneles del explorador desde el menú **Ver.**

## <a name="get-sql-server-express"></a><a name="get_sql"></a>Obtener SQL Server Express

SQL Server Express es una edición gratuita de nivel de entrada de SQL Server que puede redistribuir con aplicaciones. Descargue SQL Server Express desde la página siguiente:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Si usa [Visual Studio,](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)SQL Server Express LocalDB se incluye en la edición gratuita de la comunidad de Visual Studio, así como en las ediciones Professional y superior.  

## <a name="see-also"></a>Consulte también

- [Introducción](getting-started.md)
