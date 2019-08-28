---
title: Uso de la actividad Pick
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 03b9ff7f552ad0cdcfbe9c46121a2f46f35de52a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037879"
---
# <a name="using-the-pick-activity"></a>Uso de la actividad Pick
En este ejemplo se muestra cómo utilizar la actividad <xref:System.Activities.Statements.Pick>.

 La actividad <xref:System.Activities.Statements.Pick> proporciona un modelado de control basado en eventos. Se comporta de forma similar a la instrucción `switch` de C#, que ejecuta solo una de las bifurcaciones en la instrucción `switch`. A diferencia de la instrucción `switch`, en la que se ejecuta una bifurcación basada en un valor, la actividad <xref:System.Activities.Statements.Pick> ejecuta una bifurcación en base a la manera en que se completa una actividad.

 En este ejemplo se pide a un usuario que escriba su nombre en la consola dentro de un determinado período de tiempo. La actividad <xref:System.Activities.Statements.Pick> del ejemplo tiene dos bifurcaciones cuya ejecución depende de si el usuario escribe su nombre en un intervalo de 5 segundos o no. Si el usuario escribe su nombre en 5 segundos, se ejecuta la primera bifurcación, que contiene una actividad `ReadLine` personalizada; de lo contrario, se ejecuta la otra bifurcación, que contiene una actividad <xref:System.Activities.Statements.Delay>. Una vez escrito el nombre de un usuario en la consola, se imprime en la consola. Si no se escribe ninguna entrada en 5 segundos, la operación agota el tiempo de espera.

## <a name="demonstrates"></a>Demostraciones
 Actividad <xref:System.Activities.Statements.Pick>.

## <a name="discussion"></a>Discusión
 En este ejemplo se incluyen un flujo de trabajo de diseñador y un flujo de trabajo codificado.

 Flujo de trabajo del diseñador la versión del diseñador del ejemplo muestra cómo crear un flujo de trabajo en el diseñador. Están incluidos los siguientes archivos:

- Program.cs: Incluye la `Main` función que ejecuta el flujo de trabajo de ejemplo.

- ReadString.cs: Una actividad personalizada que Lee algunas entradas de la consola.

- Sequence1.xaml: Un flujo de trabajo creado mediante el diseñador que utiliza Pick.

 Flujo de trabajo codificado la versión codificada del ejemplo muestra cómo crear un flujo de trabajo en el diseñador. Están incluidos los siguientes archivos:

- Program.cs: Incluye la `Main` función que ejecuta el flujo de trabajo de ejemplo.

- ReadString.cs: Una actividad personalizada que Lee algunas entradas de la consola.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2010, abra el archivo de solución Pick. sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Presione F5 para ejecutar la solución.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
