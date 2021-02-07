---
description: 'Más información sobre: carga desde XAML'
title: Cargar de XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: fd0eca487c0245c7bfa46ca80c06f2adfa577353
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742035"
---
# <a name="load-from-xaml"></a>Cargar de XAML

En este ejemplo se muestra cómo cargar dinámicamente un flujo de trabajo de XAML sin tener que ejecutar la herramienta XamlBuildTask. En su lugar, el ejemplo llama al método <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>. El ejemplo es una aplicación cliente de Windows Presentation Foundation (WPF) que carga flujos de trabajo de XAML mediante la <xref:System.Activities.XamlIntegration.ActivityXamlServices> clase y los ejecuta. Una vez cargados utilizando la clase <xref:System.Activities.XamlIntegration.ActivityXamlServices>, se devuelve una actividad <xref:System.Activities.DynamicActivity%601> que se puede ejecutar.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2010, abra el archivo de solución LoadFromXAML. sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Para ejecutar la solución, presione CTRL+F5.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`
