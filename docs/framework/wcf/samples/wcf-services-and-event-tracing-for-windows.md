---
title: Servicios de WCF y seguimiento de eventos para Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: d45e83919dae52ee3719fe52463711999ba48dd3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555549"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>Servicios de WCF y seguimiento de eventos para Windows
Este ejemplo muestra cómo utilizar la traza analítica en Windows Communication Foundation (WCF) para emitir eventos de seguimiento de eventos para Windows (ETW). Los seguimientos analíticos son los eventos emitidos en puntos clave de la pila de WCF que permiten solucionar problemas de servicios WCF en el entorno de producción.

 Seguimiento la traza analítica en servicios WCF que puede activarse en un entorno de producción con un impacto mínimo en el rendimiento. Estos seguimientos se emiten como eventos para una sesión de ETW.

 Este ejemplo incluye un servicio WCF básico en el que los eventos se emiten desde el servicio en el registro de eventos que se pueden ver mediante el Visor de eventos. También es posible iniciar una sesión ETW dedicada que escucha los eventos desde el servicio WCF. En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1.  Con Visual Studio 2012, abra el archivo de solución EtwAnalyticTraceSample.sln.

2.  Para compilar la solución, presione Ctrl+MAYÚS+B.

3.  Para ejecutar la solución, presione CTRL+F5.

     En el explorador Web, haga clic en **Calculator.svc**. El URI del documento WSDL para el servicio debería aparecer en el explorador. Copie ese URI.

     De forma predeterminada, el servicio empieza a escuchar las solicitudes en el puerto 1378 `http://localhost:1378/Calculator.svc`.

4.  Ejecute al cliente de prueba WCF (WcfTestClient.exe).

     El cliente de prueba WCF (WcfTestClient.exe) se encuentra en `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.  El directorio de instalación de Visual Studio 2012 de forma predeterminada es `C:\Program Files\Microsoft Visual Studio 10.0`.

5.  En el cliente de prueba WCF, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.

     Agregue la dirección del punto de conexión en el cuadro de entrada. De manera predeterminada, es `http://localhost:1378/Calculator.svc`.

6.  Abra la aplicación Visor de eventos.

     Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha eventos de seguimiento emitidos desde el servicio WCF.

7.  Desde el **iniciar** menú, seleccione **herramientas administrativas**y, a continuación, **Visor de eventos**.  Habilitar la **analítico** y **depurar** registros.

8.  En la vista de árbol en el Visor de eventos, vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor-aplicaciones**. Haga clic en **aplicaciones de servidor-aplicaciones**, seleccione **vista**y, a continuación, **mostrar registros analíticos y depuración**.

     Asegúrese de que el **mostrar registros analíticos y depuración** opción está activada.

9. Habilitar la **analítico** registro.

     En la vista de árbol en el Visor de eventos, vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor-aplicaciones**. Haga clic en **analítico** y seleccione **Habilitar registro**.

#### <a name="to-test-the-service"></a>Para probar el servicio

1.  Vuelva al cliente de prueba WCF y haga doble clic en `Divide` y mantenga los valores predeterminados, que especifican el denominador 0.

     Si el denominador es 0, el servicio produce un error.

2.  Observe los eventos emitidos desde el servicio.

     Cambie al Visor de eventos y navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor-aplicaciones**. Haga clic en **analítico** y seleccione **actualizar**.

     Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos. Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.

3.  Repita los pasos 1 y 2, pero con entradas válidas. El valor del parámetro `N2` puede ser cualquier número distinto de 0.

     Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.

 En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.

#### <a name="to-cleanup-optional"></a>Para realizar la limpieza (Opcional)

1.  Abra el Visor de eventos.

2.  Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**. Haga clic en **analítico** y seleccione **Deshabilitar registro**.

3.  Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**. Haga clic en **analítico** y seleccione **Vaciar registro**.

4.  Elija la **borrar** opción para borrar los eventos.

> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Vea también
- [Ejemplos de supervisión de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
