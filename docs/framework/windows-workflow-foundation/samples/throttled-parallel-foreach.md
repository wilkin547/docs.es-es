---
title: Throttled Parallel ForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: fd30a1ac587359a054a273b3deca2e9bb8bc2798
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261833"
---
# <a name="throttled-parallel-foreach"></a>Throttled Parallel ForEach

La actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach%601> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutará. La actividad `ThrottleParallelForEach` se deriva de <xref:System.Activities.NativeActivity>, porque necesita programar otras actividades (las actividades secundarias) y el único acceso posible es a través de la clase <xref:System.Activities.NativeActivityContext>.

## <a name="projects"></a>Proyectos

|**ProjectName**|**Descripción**|**Archivos principales**|
|-|-|-|
|ThrottledParallelForEach|Contiene la actividad `ThrottledParallelForEach` y su diseñador.|ThrottledParallelForEach.cs<br /><br /> La definición de actividad de `ThrottledParallelForEach`.|
|CodeTestClient|Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo con una actividad `ThrottledParallelForEach` utilizando código imperativo.|Program.cs<br /><br /> Define y ejecuta una instancia del flujo de trabajo de muestra.|

## <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2010, abra el archivo ThrottledParallelForEach.sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Presione F5 para ejecutar la solución.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`