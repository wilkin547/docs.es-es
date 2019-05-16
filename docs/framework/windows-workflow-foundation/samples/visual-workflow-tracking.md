---
title: Realizar el seguimiento visual del flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 0143448f-2044-40a0-8a3d-941f6d12468b
ms.openlocfilehash: abd9f294018f6aa1fd2020314688258ac00792f7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637801"
---
# <a name="visual-workflow-tracking"></a>Realizar el seguimiento visual del flujo de trabajo
En este ejemplo se muestra cómo escribir una aplicación de seguimiento de flujo de trabajo visual mediante la funcionalidad de depuración disponible en [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].

## <a name="sample-details"></a>Detalles del ejemplo
 La aplicación ejecuta un flujo de trabajo de diagrama de flujo simple (definido en Workflow.xaml) y hospeda en otro host el diseñador de flujo de trabajo para mostrar el flujo de trabajo que se está ejecutando actualmente. A medida que se ejecuta el flujo de trabajo, la actividad que se está ejecutando actualmente se muestra con un contorno amarillo y una flecha de depuración. Además, los registros de seguimiento generados por el flujo de trabajo también se muestran en la ventana de la aplicación. Para obtener más información acerca del seguimiento de flujo de trabajo, consulte [seguimiento y traza del flujo de trabajo](../workflow-tracking-and-tracing.md). Para obtener más información sobre cómo volver a hospedar el Diseñador de flujo de trabajo, consulte [Rehospedar el Diseñador de flujo de trabajo](../rehosting-the-workflow-designer.md).

 El simulador de flujo de trabajo funciona manteniendo dos diccionarios. Uno contiene una asignación entre el objeto de actividad actualmente en ejecución y el número de línea de XAML donde se crea la instancia de la actividad. El otro contiene una asignación entre el identificador de la instancia de actividad y el objeto de actividad. Cuando se emiten registros de seguimiento mediante un perfil de seguimiento personalizado, la aplicación determina el identificador de instancia de la actividad que se está ejecutando actualmente y lo asigna al archivo XAML que creó su instancia. A continuación, se indica al diseñador de flujo de trabajo hospedado en otro host que resalte la actividad en la superficie del diseñador y utilice el mismo método que el depurador del flujo de trabajo, concretamente que dibuje un borde amarillo en torno a la actividad y que muestre una flecha amarilla en el lado izquierdo del diseñador.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Abra el archivo WorkflowSimulator.sln del directorio de ejemplo en Visual Studio 2010.

2. Presione Ctrl+MAYÚS+B para compilar la solución.

3. Presione CTRL + F5 para ejecutar el ejemplo. Así se muestra el archivo Workflow.xaml en una ventana de diseñador de flujo de trabajo hospedada en otro host.

4. Haga clic en el **archivo** menú y seleccione **ejecutar flujo de trabajo...** .

5. Observe que la actividad actualmente en ejecución se resalta tal como se ha descrito previamente y que en el lado derecho de la ventana de la aplicación se muestran los registros de seguimiento.

6. Cuando el flujo de trabajo se ha completado, puede hacer clic en cualquier registro de seguimiento para inspeccionar qué actividad corresponde.

> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\VisualWorkflowTracking`
