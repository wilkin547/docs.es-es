---
title: Control de errores en una actividad de diagrama de flujo utilizando TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 81bfeb911658a6f363a9f0f95ecc7db68a02dbe2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331265"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Control de errores en una actividad de diagrama de flujo utilizando TryCatch
En este ejemplo se muestra cómo se puede usar la actividad <xref:System.Activities.Statements.TryCatch> dentro de una actividad de flujo de control compleja.

 En este ejemplo, se pasan un código de la promoción y el número de hijos como variables a una actividad <xref:System.Activities.Statements.Flowchart> que calcula un descuento en función de fórmulas que corresponden al código de promoción. En el ejemplo se incluyen las versiones de código imperativo y de diseñador de flujo de trabajo del ejemplo.

 En la siguiente tabla se detallan las variables de la actividad `CreateFlowchartWithFaults`.

|Parámetros|Descripción|
|----------------|-----------------|
|promoCode|El código de la promoción. Tipo: String<br /><br /> Los posibles valores con descripción en paréntesis:<br /><br /> -Única (Single)<br />-MNK (casado sin hijos).<br />-MWK (casado con hijos).|
|numKids|El número de hijos. Tipo: int|

 La actividad `CreateFlowchartWithFaults` utiliza una actividad <xref:System.Activities.Statements.FlowSwitch%601> que activa el argumento `promoCode` y calcula el descuento mediante la siguiente fórmula.

|Valor de `promoCode`|Descuento (%)|
|--------------------------|--------------------|
|Single|10|
|MNK|15|
|MWK|15 + (1 – 1 /`numberOfKids`)\*10 **Nota:**  Este cálculo podría producir una excepción <xref:System.DivideByZeroException>. Por tanto, el cálculo del descuento se incluye en una actividad <xref:System.Activities.Statements.TryCatch> que detecta la excepción <xref:System.DivideByZeroException> y establece el descuento en cero.|

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2010, abra el archivo de solución FlowchartWithFaultHandling.sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Presione F5 para ejecutar la solución.

> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a>Vea también

- [Flujos de trabajo del diagrama de flujo](../flowchart-workflows.md)
- [Excepciones](../exceptions.md)
