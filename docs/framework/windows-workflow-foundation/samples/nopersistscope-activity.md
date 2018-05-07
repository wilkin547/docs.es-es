---
title: Actividad NoPersistScope
ms.date: 03/30/2017
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
ms.openlocfilehash: e4779bf28fc2fc1341cce5134a872b108278611c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="nopersistscope-activity"></a>Actividad NoPersistScope
En este ejemplo se muestra cómo manipular un estado no serializable y descartable dentro de un flujo de trabajo. Es importante que los flujos de trabajo no intenten conservar el estado no serializable y también que los objetos descartables se limpien después de utilizarse en el flujo de trabajo.  
  
## <a name="demonstrates"></a>Demostraciones  
 Actividad `NoPersistScope` personalizada y diseñador.  
  
## <a name="using-the-nopersistzone-activity"></a>Usar la actividad NoPersistZone  
 Cuando el flujo de trabajo del ejemplo se ejecuta, una actividad personalizada denominada `CreateTextWriter` crea un objeto de tipo <xref:System.IO.TextWriter> y lo guarda en una variable de flujo de trabajo. <xref:System.IO.TextWriter> es un objeto <xref:System.IDisposable>. Este <xref:System.IO.TextWriter>, que se configura para escribir en un archivo denominado 'out.txt' en el directorio en el que se ejecuta el ejemplo, es utilizado por una actividad <xref:System.Activities.Statements.WriteLine> porque devuelve cualquier texto que se escriba en la consola.  
  
 La lógica de devolución se ejecuta dentro de una actividad `NoPersistScope` (cuyo código forma también parte de este ejemplo), que evita que se conserve el flujo de trabajo. Si escribe en `unload` en la consola, el host intenta conservar la instancia de flujo de trabajo pero caduca esta operación porque el flujo de trabajo permanece dentro de un `NoPersistScope`. El flujo de trabajo también utiliza una actividad personalizada denominada `Dispose` para eliminar el objeto <xref:System.IO.TextWriter> cuando el flujo de trabajo ha terminado de utilizarlo. La actividad `Dispose` se coloca dentro del bloque <xref:System.Activities.Statements.TryCatch.Finally%2A> de la actividad <xref:System.Activities.Statements.TryCatch> en la que se declara la variable <xref:System.IO.TextWriter>, para asegurarse de que ejecuta aunque se produzca una excepción durante la ejecución del bloque Try.  
  
 Puede escribir en `exit` para completar la instancia de flujo de trabajo y salir del programa.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución NoPersistZone.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **generar solución** desde el **generar** menú.  
  
3.  Cuando la compilación finalice correctamente, presione F5 o seleccione **Iniciar depuración** desde el **depurar** menú como alternativa, puede presionar CTRL + F5 o seleccione **iniciar sin depurar** desde el **Depurar** menú para ejecutarlo sin depuración.  
  
#### <a name="to-cleanup-optional"></a>Para realizar la limpieza (opcional)  
  
1.  Para quitar el almacén de instancias de SQL, ejecute Cleanup.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`