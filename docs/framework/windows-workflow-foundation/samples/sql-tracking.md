---
title: Seguimiento de SQL
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 72bfcaac2903b3e7fa5679422ad4feaa79e93211
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243185"
---
# <a name="sql-tracking"></a>Seguimiento SQL

En este ejemplo se muestra cómo escribir un participante de seguimiento de SQL personalizado que escribe registros de seguimiento en una base de datos SQL. Windows Workflow Foundation (WF) proporciona seguimiento de flujo de trabajo para obtener visibilidad de la ejecución de una instancia de flujo de trabajo. El tiempo de ejecución de seguimiento emite registros de seguimiento de flujo de trabajo durante la ejecución del flujo de trabajo. Para obtener más información sobre el seguimiento del flujo de trabajo, consulte [Seguimiento y seguimiento](../workflow-tracking-and-tracing.md)del flujo de trabajo .

## <a name="use-the-sample"></a>Utilice la muestra

1. Compruebe que tiene instalado SQL Server 2008, SQL Server 2008 Express o una versión más reciente. Los scripts empaquetados con el ejemplo dan por supuesto el uso de una instancia de SQL Express en su equipo local. Si tiene una instancia diferente, modifique los scripts de base de datos antes de ejecutar el ejemplo.

2. Cree la base de datos de seguimiento de SQL Server ejecutando Trackingsetup.cmd en el directorio de scripts (\WF\Basic\Tracking\SqlTracking\CS\Scripts). De esta forma, se creará una base de datos denominada TrackingSample.

   > [!NOTE]
   > El script crea la base de datos en la instancia predeterminada de SQL Express. Si desea realizar la instalación en una instancia de base de datos diferente, modifique el script Trackingsetup.cmd.

3. Abra SqlTrackingSample.sln en Visual Studio 2010.

4. Presione **Ctrl**+**Shift**+**B** para compilar la solución.

5. Presione **F5** para ejecutar la aplicación.

   La ventana del explorador se abre y muestra la lista de directorios de la aplicación.

6. En el explorador, haga clic en StockPriceService.xamlx.

7. El explorador muestra la página StockPriceService, que contiene la dirección WSDL de servicio local. Copie esta dirección.

   Un ejemplo de la dirección `http://localhost:65193/StockPriceService.xamlx?wsdl`WSDL del servicio local es .

8. Con el Explorador de archivos, ejecute el cliente de prueba WCF (WcfTestClient.exe). Se encuentra en el *directorio de Microsoft Visual Studio 10.0-Common7-IDE*.

9. En el cliente de prueba WCF, haga clic en **el** archivo menú y seleccione **agregar servicio**. Pegue la dirección del servicio local en el cuadro de texto. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

10. En el cliente de prueba WCF, haga doble clic en **GetStockPrice**. Esto abre `GetStockPrice` la operación que toma `Contoso` un parámetro, escriba el valor y haga clic en **Invocar**.

11. Los registros de seguimiento emitidos se escriben en una base de datos SQL. Para ver los registros de seguimiento, abra la base de datos TrackingSample en SQL Management Studio y navegue hasta las tablas. La ejecución de una consulta de selección en las tablas muestra los datos dentro de los registros de seguimiento almacenados en las tablas respectivas.

   Para obtener más información acerca de SQL Server Management Studio, vea [Introducción a SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms). Descargue SQL Server Management Studio [aquí](https://aka.ms/ssmsfullsetup).

## <a name="uninstall-the-sample"></a>Desinstale el ejemplo

1. Ejecute el script Trackingcleanup.cmd en el directorio de ejemplo (*.*

    > [!NOTE]
    > Trackingcleanup.cmd intenta eliminar la base de datos en el SQL Express del equipo local. Si está utilizando otra instancia del servidor SQL, modifique Trackingcleanup.cmd.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a>Consulte también

- [Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
