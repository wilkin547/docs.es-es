---
title: "Actividad NoPersistScope | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Actividad NoPersistScope
En este ejemplo se muestra cómo manipular un estado no serializable y descartable dentro de un flujo de trabajo.Es importante que los flujos de trabajo no intenten conservar el estado no serializable y también que los objetos descartables se limpien después de utilizarse en el flujo de trabajo.  
  
## Demostraciones  
 Actividad `NoPersistScope` personalizada y diseñador.  
  
## Usar la actividad NoPersistZone  
 Cuando el flujo de trabajo del ejemplo se ejecuta, una actividad personalizada denominada `CreateTextWriter` crea un objeto de tipo <xref:System.IO.TextWriter> y lo guarda en una variable de flujo de trabajo.<xref:System.IO.TextWriter> es un objeto <xref:System.IDisposable>.Este <xref:System.IO.TextWriter>, que se configura para escribir en un archivo denominado 'out.txt' en el directorio en el que se ejecuta el ejemplo, es utilizado por una actividad <xref:System.Activities.Statements.WriteLine> porque devuelve cualquier texto que se escriba en la consola.  
  
 La lógica de devolución se ejecuta dentro de una actividad `NoPersistScope` \(cuyo código forma también parte de este ejemplo\), que evita que se conserve el flujo de trabajo.Si escribe `descarga` en la consola, el host intenta conservar la instancia de flujo de trabajo, pero esta operación supera el tiempo de espera porque el flujo de trabajo permanece dentro de un `NoPersistScope`.El flujo de trabajo también utiliza una actividad personalizada denominada `Dispose` para eliminar el objeto <xref:System.IO.TextWriter> cuando el flujo de trabajo ha terminado de utilizarlo.La actividad `Dispose` se coloca dentro del bloque <xref:System.Activities.Statements.TryCatch.Finally%2A> de la actividad <xref:System.Activities.Statements.TryCatch> en la que se declara la variable <xref:System.IO.TextWriter>, para asegurarse de que ejecuta aunque se produzca una excepción durante la ejecución del bloque Try.  
  
 Puede escribir `salir` completar la instancia de flujo de trabajo y salir del programa.  
  
#### Para ejecutar el ejemplo  
  
1.  Abra la solución NoPersistZone.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL\+MAYÚS\+B o seleccione **Compilar solución** en el menú **Compilar**.  
  
3.  Cuando la compilación se complete correctamente, presione F5 o seleccione **Iniciar depuración** en el menú **Depurar**; también, puede presionar CTRL\+F5 o seleccionar **Iniciar sin depurar** en el menú **Depurar** para realizar la ejecución sin depuración.  
  
#### Para realizar la limpieza \(opcional\)  
  
1.  Para quitar el almacén de instancias de SQL, ejecute Cleanup.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>: \WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`  
  
## Vea también