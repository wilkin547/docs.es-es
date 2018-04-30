---
title: Actividad Policy en .NET Framework 4.5
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ff750942a2d05310669361e83a10a5acefbcbd4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="policy-activity-in-net-framework-45"></a>Actividad Policy en .NET Framework 4.5
La actividad Policy4 permite a Windows Workflow Foundation en [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objetos para su uso en Windows Workflow Foundation en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directamente mediante el motor de reglas que se distribuye con WF 3.5. Utilizando esta actividad, puede crear y ejecutar un objeto <xref:System.Workflow.Activities.Rules.RuleSet> de WF 3.5. Para obtener más información sobre el motor de reglas de WF 3.5 incluido como parte de Windows Workflow Foundation, lea el apartado introducción al motor de reglas de Windows Workflow Foundation. Para obtener más información sobre cómo migrar las reglas de WF en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], lea [Guía de migración](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## <a name="projects-in-this-sample"></a>Proyectos en este ejemplo  
  
|Nombre del proyecto|Descripción|Archivos principales|  
|------------------|-----------------|----------------|  
|Policy4|Contiene la actividad Policy4 y su diseñador de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Policy4.cs**: definición de la actividad Policy4.<br /><br /> **PolicyDesigner.xaml**: diseñador personalizado para la actividad Policy4. Utiliza el editor de reglas ([clase RuleSetDialog](http://go.microsoft.com/fwlink/?LinkId=150378)) de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] motor de reglas.|  
|ImperativeCodeClientSample|Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo mediante una aplicación Policy4 que utiliza el código C# imperativo (no se utiliza ningún diseñador de [!INCLUDE[wf1](../../../../includes/wf1-md.md)]).|**ApplyDiscount.rules**: archivo con [!INCLUDE[wf1](../../../../includes/wf1-md.md)] definiciones de reglas.<br /><br /> **Order.cs**: tipo que representa un pedido de cliente. Las reglas se aplican a los objetos de este tipo.<br /><br /> **Program.cs**: configura y ejecuta un flujo de trabajo que tiene una actividad Policy4 para aplicar las reglas definidas en ApplyDiscount.rules a las instancias de objetos Order.<br /><br /> **App.config**: archivo de configuración con la ruta de acceso del archivo de reglas.|  
|DesignerClientSample|Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo utilizando una aplicación Policy4 en el diseñador de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1.XAML**: flujo de trabajo secuencial que utiliza una actividad Policy4 para realizar evaluaciones de reglas.<br /><br /> `Program.cs`: ejecuta una instancia de flujo de trabajo definida en Sequence1.xaml.|  
  
## <a name="the-policy4-activity"></a>La actividad Policy4  
 La actividad Policy4 es una clase que se deriva de <xref:System.Activities.NativeActivity%601> y permite a los flujos de trabajo ejecutar RuleSets de [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. El siguiente ejemplo de código es una definición simplificada del modelo de objetos público de la actividad.  
  
```csharp  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|RuleSet|WF [clase RuleSet](http://go.microsoft.com/fwlink/?LinkId=150379) para .NET Framework 3.5 que se evaluará cuando se ejecuta la actividad.|  
|TargetObject|El objeto con el que las reglas de la [clase RuleSet](http://go.microsoft.com/fwlink/?LinkId=150379) se evalúan.|  
|ValidationError|La lista de errores de validación devuelta por la [!INCLUDE[wf1](../../../../includes/wf1-md.md)] motor de reglas para .NET Framework 3.5 al validar el [clase RuleSet](http://go.microsoft.com/fwlink/?LinkId=150379) con el objeto de destino antes de la ejecución.|  
  
## <a name="policy4-activity-designer"></a>Diseñador de la actividad Policy4  
 El diseñador de Policy4 agrega la capacidad de configurar una actividad Policy4 sin necesidad de escribir código. Después de compilar la solución, se puede encontrar en el cuadro de herramientas en la sección **Microsoft.Samples.Activities.Rules**.  
  
 El diseñador de WF le permite configurar un objeto de destino y un conjunto de reglas. Cuando el **editar RuleSet** se hace clic en botón, WF [clase RuleSetDialog](http://go.microsoft.com/fwlink/?LinkId=150378) para [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] se muestra. Este diálogo representa el editor de reglas de [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] re-hospedado. Utilice el editor para crear y modificar las reglas que la actividad Policy4 ejecuta.  
  
## <a name="using-this-sample"></a>Utilizar este ejemplo  
 No se exige ninguna configuración especial para ejecutar este ejemplo. Simplemente abra la solución en Visual Studio y presione F5 para ejecutar la aplicación.  
  
 Este ejemplo contiene dos aplicaciones cliente: ImperativeCodeClientSample y DesignerClientSample. El cliente ImperativeCodeClientSample muestra cómo configurar y ejecutar la actividad Policy40 utilizando el código imperativo C#. DesignerClientSample muestra cómo configurar y ejecutar la actividad Policy4 mediante el diseñador.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>Para ejecutar la aplicación cliente ImperativeCodeClientSample  
  
1.  Abra el archivo de solución Policy4Sample.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  En **el Explorador de soluciones**, haga clic en el **ImperativeCodeClientSample** de proyecto y, a continuación, seleccione **establecer como proyecto de inicio**.  
  
3.  Presione CTRL+F5 para ejecutar el proyecto.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>Para ejecutar la aplicación cliente ImperativeCodeClientSample  
  
1.  Abra el archivo de solución Policy4Sample.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  En **el Explorador de soluciones**, haga clic en el **DesignerClientSample** proyecto.  
  
    -   Seleccione **establecer como proyecto de inicio**.  
  
3.  Presione CTRL+MAYÚS+B para compilar el proyecto.  
  
4.  Presione CTRL+F5 para ejecutar el proyecto.