---
title: Actividad NoPersistScope
ms.date: 03/30/2017
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
ms.openlocfilehash: 6543756594b6734aec39bf22c5ab6215605341b1
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46485358"
---
# <a name="nopersistscope-activity"></a>Actividad NoPersistScope
En este ejemplo se muestra cómo manipular un estado no serializable y descartable dentro de un flujo de trabajo. Es importante que los flujos de trabajo no intenten conservar el estado no serializable y también que los objetos descartables se limpien después de utilizarse en el flujo de trabajo.  
  
## <a name="demonstrates"></a>Demostraciones  
 Actividad `NoPersistScope` personalizada y diseñador.  
  
## <a name="using-the-nopersistzone-activity"></a>Usar la actividad NoPersistZone  
 Cuando el flujo de trabajo del ejemplo se ejecuta, una actividad personalizada denominada `CreateTextWriter` crea un objeto de tipo <xref:System.IO.TextWriter> y lo guarda en una variable de flujo de trabajo. <xref:System.IO.TextWriter> es un objeto <xref:System.IDisposable>. Este <xref:System.IO.TextWriter>, que se configura para escribir en un archivo denominado 'out.txt' en el directorio en el que se ejecuta el ejemplo, es utilizado por una actividad <xref:System.Activities.Statements.WriteLine> porque devuelve cualquier texto que se escriba en la consola.  
  
 La lógica de devolución se ejecuta dentro de una actividad `NoPersistScope` (cuyo código forma también parte de este ejemplo), que evita que se conserve el flujo de trabajo. Si escribe en `unload` en la consola, el host intenta conservar la instancia de flujo de trabajo, pero esta operación agota el tiempo porque el flujo de trabajo permanece dentro de un `NoPersistScope`. El flujo de trabajo también utiliza una actividad personalizada denominada `Dispose` para eliminar el objeto <xref:System.IO.TextWriter> cuando el flujo de trabajo ha terminado de utilizarlo. La actividad `Dispose` se coloca dentro del bloque <xref:System.Activities.Statements.TryCatch.Finally%2A> de la actividad <xref:System.Activities.Statements.TryCatch> en la que se declara la variable <xref:System.IO.TextWriter>, para asegurarse de que ejecuta aunque se produzca una excepción durante la ejecución del bloque Try.  
  
 Puede escribir en `exit` para completar la instancia de flujo de trabajo y salir del programa.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución NoPersistZone.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **compilar solución** desde el **compilar** menú.  
  
3.  Una vez que se ha realizado correctamente la compilación, presione F5 o seleccione **Iniciar depuración** desde el **depurar** menú como alternativa, puede presionar CTRL + F5 o seleccione **iniciar sin depurar** desde el **Depurar** menú ejecutar sin depuración.  
  
#### <a name="to-cleanup-optional"></a>Para realizar la limpieza (opcional)  
  
1.  Para quitar el almacén de instancias de SQL, ejecute Cleanup.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`