---
title: Seguimiento de SQL
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 88f44e5362684f755695aab154842fad2274134d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094597"
---
# <a name="sql-tracking"></a>Seguimiento de SQL
Este ejemplo muestra cómo escribir un participante de seguimiento SQL personalizado que escribe registros de seguimiento en una base de datos SQL. Windows Workflow Foundation (WF) proporciona seguimiento de flujo de trabajo para obtener visibilidad de la ejecución de una instancia de flujo de trabajo. El tiempo de ejecución de seguimiento emite registros de seguimiento de flujo de trabajo durante la ejecución del flujo de trabajo. Para obtener más información sobre el seguimiento del flujo de trabajo, vea [seguimiento y](../workflow-tracking-and-tracing.md)seguimiento del flujo de trabajo.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Compruebe que tiene instalado SQL Server 2008, SQL Server 2008 Express o una versión más reciente. Los scripts empaquetados con el ejemplo dan por supuesto el uso de una instancia de SQL Express en su equipo local. Si tiene una instancia diferente, modifique los scripts de base de datos antes de ejecutar el ejemplo.

2. Cree la base de datos de seguimiento de SQL Server ejecutando Trackingsetup.cmd en el directorio de scripts (\WF\Basic\Tracking\SqlTracking\CS\Scripts). De esta forma, se creará una base de datos denominada TrackingSample.

    > [!NOTE]
    > El script crea la base de datos en la instancia predeterminada de SQL Express. Si desea realizar la instalación en una instancia de base de datos diferente, modifique el script Trackingsetup.cmd.

3. Abra SqlTrackingSample. sln en Visual Studio 2010.

4. Presione CTRL+MAYÚS+B para compilar la solución.

5. Presione F5 para ejecutar la aplicación.

     La ventana del explorador se abre y muestra la lista de directorios de la aplicación.

6. En el explorador, haga clic en StockPriceService.xamlx.

7. El explorador muestra la página StockPriceService, que contiene la dirección WSDL de servicio local. Copie esta dirección.

     Un ejemplo de dirección WSDL de servicio local es `http://localhost:65193/StockPriceService.xamlx?wsdl`.

8. Con el explorador de archivos, ejecute el cliente de prueba de WCF (WcfTestClient. exe). Se encuentra en el directorio Microsoft Visual Studio 10.0\Common7\IDE.

9. En el cliente de prueba WCF, haga clic en el menú **archivo** y seleccione **Agregar servicio**. Pegue la dirección del servicio local en el cuadro de texto. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

10. En el cliente de prueba WCF, haga doble clic en **GetStockPrice**. Se abrirá la `GetStockPrice` operación que toma un parámetro, se escribe en el valor `Contoso` y se hace clic en **invocar**.

11. Los registros de seguimiento emitidos se escriben en una base de datos SQL. Para ver los registros de seguimiento, abra la base de datos TrackingSample en SQL Management Studio y navegue hasta las tablas. Para obtener más información acerca de SQL Server Management Studio, consulte [introducing SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms). SQL Server 2008 Management Studio Express se puede descargar [aquí](https://www.microsoft.com/download/details.aspx?id=7593). La ejecución de una consulta de selección en las tablas muestra los datos dentro de los registros de seguimiento almacenados en las tablas respectivas.

#### <a name="to-uninstall-the-sample"></a>Para desinstalar el ejemplo

1. Ejecute el script Trackingcleanup.cmd script en el directorio de ejemplo (\WF\Basic\Tracking\SqlTracking).

    > [!NOTE]
    > Trackingcleanup.cmd intenta eliminar la base de datos en el SQL Express del equipo local. Si está utilizando otra instancia del servidor SQL, modifique Trackingcleanup.cmd.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a>Consulte también

- [Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
