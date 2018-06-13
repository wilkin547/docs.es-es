---
title: Retraso absoluto
ms.date: 03/30/2017
ms.assetid: b483139a-39bb-4560-8003-8969a8fc2cd1
ms.openlocfilehash: 3a104f6b879e9cdc899bad2201ad1ed320a38a2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518390"
---
# <a name="absolute-delay"></a>Retraso absoluto
El escenario principal de este ejemplo es el retraso hasta un valor de <xref:System.DateTime> especificado utilizando temporizadores duraderos en una aplicación de flujo de trabajo. Esto es diferente a utilizar la actividad <xref:System.Activities.Statements.Delay> integrada, ya que en este caso solo se permitirá el retraso para un valor de <xref:System.TimeSpan> (o número de minutos/segundos) determinado.  
  
 A continuación se enumeran algunos escenarios de la vida real en los que se puede desear realizar esta distinción:  
  
1.  Desea retrasar el envío de un mensaje de correo durante 30 segundos para asegurarse de que no ha cometido errores.  
  
2.  Está realizando horas extraordinarias y desea retrasar todos sus mensajes de correo hasta el horario laboral normal (por ejemplo, 8 a.m.).  
  
## <a name="demonstrates"></a>Demostraciones  
  
1.  <xref:System.Activities.Statements.DurableTimerExtension> para implementar retraso absoluto  
  
2.  Configurar la persistencia utilizando <xref:System.Activities.WorkflowApplication> para temporizadores duraderos  
  
3.  Uso de <xref:System.Activities.NativeActivity%601> para utilizar puntos de extensibilidad  
  
4.  Uso de <xref:System.Activities.CodeActivity%601> en la actividad SendEmail.  
  
5.  <xref:System.Activities.Statements.Delay>  
  
6.  Flujo de trabajo de solo XAML  
  
 En este ejemplo se muestra cómo crear una actividad personalizada que toma un valor de <xref:System.DateTime> y utiliza temporizadores duraderos para registrar la duración del retraso. Cuando se utilizan temporizadores duraderos, se debe usar una actividad <xref:System.Activities.NativeActivity> para crear un marcador, ya que será necesario registrar este marcador con la extensión de temporizador. En este ejemplo, cuando el temporizador duradero expire, se llamará al método `OnTimerExpired`. Asegúrese de que está agregando la extensión de temporizador en el evento <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> para tener la garantía de que está proporcionando esta información al runtime. El otro único detalle de la implementación es que necesitará implementar la lógica para convertir de <xref:System.DateTime> a <xref:System.TimeSpan>, ya que los temporizadores duraderos solo toman un valor de <xref:System.DateTime>. Observe que esto implica la existencia de un lapso pequeño en la precisión.  
  
> [!NOTE]
>  Hay una ligera pérdida de precisión al convertir de <xref:System.DateTime> a <xref:System.TimeSpan>.  
  
 En este ejemplo también se muestra cómo activar la persistencia para un elemento <xref:System.Activities.WorkflowApplication>. En este ejemplo concreto, utilizaremos temporizadores duraderos en los que los datos de flujo de trabajo se descargarán en la base de datos de persistencia durante el tiempo de inactividad mientras se espera que el temporizador expire. Esta implementación también se puede utilizar para otras acciones de persistencia. En este ejemplo, se muestra cómo configurar la cadena de conexión de persistencia con SQL Server y cómo crear el almacén de instancias para conservar los datos de las instancias de flujo de trabajo. Se proporciona lógica sobre cómo reanudar el flujo de trabajo una vez producido un evento que hace que la instancia de flujo de trabajo se pueda ejecutar.  
  
 Paso a paso a través de este ejemplo, verá el tiempo en el que el retraso integrado comienza y completa, que a su vez producirá que se envíe un mensaje de correo electrónico. A partir de ese momento, la actividad AbsoluteDelay se detendrá hasta un valor de <xref:System.DateTime> especificado (o 0 segundos si el valor de <xref:System.DateTime> ha expirado), produciéndose a su vez el envío de un mensaje de correo electrónico tras la expiración. De este modo, se mostrarán los dos casos de uso diferentes de la funcionalidad de la actividad <xref:System.Activities.Statements.Delay> integrada frente al uso de una actividad AbsoluteDelay.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que tiene instalado en su equipo SQL Server Express (o posterior).  
  
2.  Ejecute setup.cmd (desde WF/Basic/Services/AbsoluteDelay/CS) en un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] para crear la base de datos AbsoluteDelaySampleDB, el esquema de persistencia y la lógica de persistencia.  
  
3.  Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
4.  Especifique la duración de la actividad Delay.  
  
5.  Especifique el valor de ExpirationTime de la actividad AbsoluteDelay.  
  
6.  Actualice los campos SendMailTo, SendMailFrom, SendMailSubject, SendMailBody y SmtpHost en la actividad SendMail.  
  
    > [!NOTE]
    >  Si no especifica un host de SMTP válido, la aplicación producirá una excepción SMTP.  
  
7.  Compile la solución seleccionando **generar**, **generar solución**.  
  
8.  Ejecute la solución presionando **F5**.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\AbsoluteDelay`
