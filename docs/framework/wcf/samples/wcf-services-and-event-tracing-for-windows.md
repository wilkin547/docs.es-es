---
title: Servicios de WCF y seguimiento de eventos para Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183211"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>Servicios de WCF y seguimiento de eventos para Windows
En este ejemplo se muestra cómo usar el seguimiento analítico en Windows Communication Foundation (WCF) para emitir eventos en Seguimiento de eventos para Windows (ETW). Los seguimientos analíticos son eventos emitidos en puntos clave de la pila de WCF que permiten la solución de problemas de servicios WCF en el entorno de producción.

 Seguimiento analítico en los servicios WCF es el seguimiento que se puede activar en un entorno de producción con un impacto mínimo en el rendimiento. Estos seguimientos se emiten como eventos para una sesión de ETW.

 Este ejemplo incluye un servicio WCF básico en el que los eventos se emiten desde el servicio al registro de eventos, que se puede ver mediante el Visor de eventos. También es posible iniciar una sesión ETW dedicada que escucha eventos del servicio WCF. En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2012, abra el archivo de solución EtwAnalyticTraceSample.sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Para ejecutar la solución, presione CTRL+F5.

     En el explorador web, haga clic en **Calculator.svc**. El URI del documento WSDL para el servicio debería aparecer en el explorador. Copie ese URI.

     De forma predeterminada, el servicio comienza a escuchar `http://localhost:1378/Calculator.svc`las solicitudes en el puerto 1378.

4. Ejecute el cliente de prueba WCF (WcfTestClient.exe).

     El cliente de prueba WCF (WcfTestClient.exe) se encuentra en `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.  El dir de instalación predeterminado de `C:\Program Files\Microsoft Visual Studio 10.0`Visual Studio 2012 es .

5. En el cliente de prueba WCF, agregue el servicio seleccionando **Archivo**y, a continuación, **Agregar servicio**.

     Agregue la dirección del punto de conexión en el cuadro de entrada. El valor predeterminado es `http://localhost:1378/Calculator.svc`.

6. Abra la aplicación Visor de eventos.

     Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos está escuchando los eventos de seguimiento emitidos desde el servicio WCF.

7. En el menú **Inicio** , seleccione **Herramientas administrativas**y, a continuación, Visor **de eventos**.  Habilite los registros **analíticos** y **de depuración.**

8. En la vista de árbol del Visor de eventos, vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, Aplicaciones **del servidor**de aplicaciones . Haga clic con el botón secundario en **Application Server-Applications**, seleccione **View**y, a continuación, Mostrar registros **analíticos y de depuración**.

     Asegúrese de que la opción Mostrar registros **analíticos y de depuración** esté marcada.

9. Habilite el registro **analítico.**

     En la vista de árbol del Visor de eventos, vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, Aplicaciones **del servidor**de aplicaciones . Haga clic con el botón derecho en **Analítico** y seleccione **Habilitar registro**.

#### <a name="to-test-the-service"></a>Para probar el servicio

1. Vuelva al cliente de prueba `Divide` WCF y haga doble clic y mantenga los valores predeterminados, que especifican un denominador de 0.

     Si el denominador es 0, el servicio produce un error.

2. Observe los eventos emitidos desde el servicio.

     Vuelva al Visor de eventos y vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, Aplicaciones **del servidor**de aplicaciones . Haga clic con el botón derecho en **Analítico** y seleccione **Actualizar**.

     Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos. Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.

3. Repita los pasos 1 y 2, pero con entradas válidas. El valor del parámetro `N2` puede ser cualquier número distinto de 0.

     Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.

 En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.

#### <a name="to-cleanup-optional"></a>Para realizar la limpieza (Opcional)

1. Abra el Visor de eventos.

2. Vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor de**aplicaciones . Haga clic con el botón derecho en **Analítico** y seleccione **Desactivar registro**.

3. Vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor de**aplicaciones . Haga clic con el botón derecho en **Analítico** y seleccione **Borrar registro**.

4. Elija la opción **Borrar** para borrar los eventos.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
