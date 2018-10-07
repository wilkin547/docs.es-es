---
title: Uso de la actividad Pick
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 59f99d2e0a69d796c1ec64093cf73e07b88887c9
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2018
ms.locfileid: "48848288"
---
# <a name="using-the-pick-activity"></a>Uso de la actividad Pick
En este ejemplo se muestra cómo utilizar la actividad <xref:System.Activities.Statements.Pick>.

 La actividad <xref:System.Activities.Statements.Pick> proporciona un modelado de control basado en eventos. Se comporta de forma similar a la instrucción `switch` de C#, que ejecuta solo una de las bifurcaciones en la instrucción `switch`. A diferencia de la instrucción `switch`, en la que se ejecuta una bifurcación basada en un valor, la actividad <xref:System.Activities.Statements.Pick> ejecuta una bifurcación en base a la manera en que se completa una actividad.

 En este ejemplo se pide a un usuario que escriba su nombre en la consola dentro de un determinado período de tiempo. La actividad <xref:System.Activities.Statements.Pick> del ejemplo tiene dos bifurcaciones cuya ejecución depende de si el usuario escribe su nombre en un intervalo de 5 segundos o no. Si el usuario escribe su nombre en 5 segundos, se ejecuta la primera bifurcación, que contiene una actividad `ReadLine` personalizada; de lo contrario, se ejecuta la otra bifurcación, que contiene una actividad <xref:System.Activities.Statements.Delay>. Una vez escrito el nombre de un usuario en la consola, se imprime en la consola. Si no se escribe ninguna entrada en 5 segundos, la operación agota el tiempo de espera.

## <a name="demonstrates"></a>Demostraciones
 Actividad <xref:System.Activities.Statements.Pick>.

## <a name="discussion"></a>Explicación
 En este ejemplo se incluyen un flujo de trabajo de diseñador y un flujo de trabajo codificado.

 Diseñador versión para el Diseñador de flujo de trabajo del ejemplo muestra cómo crear un flujo de trabajo en el diseñador. Están incluidos los siguientes archivos:

-   Program.cs: incluye la función `Main` que ejecuta el flujo de trabajo del ejemplo.

-   ReadString.cs: una actividad personalizada que lee alguna entrada de la consola.

-   Sequence1.xaml: un flujo de trabajo creado mediante el diseñador que utiliza Pick.

 Flujo de trabajo codificado la versión codificada del ejemplo muestra cómo crear un flujo de trabajo en el diseñador. Están incluidos los siguientes archivos:

-   Program.cs: incluye la función `Main` que ejecuta el flujo de trabajo del ejemplo.

-   ReadString.cs: una actividad personalizada que lee alguna entrada de la consola.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1.  Con Visual Studio 2010, abra el archivo de solución Pick.sln.

2.  Para compilar la solución, presione Ctrl+MAYÚS+B.

3.  Presione F5 para ejecutar la solución.

> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`