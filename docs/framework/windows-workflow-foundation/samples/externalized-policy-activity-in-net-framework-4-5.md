---
title: Actividad Externalized Policy en .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 1d163659fa4b04694d9c97087f67fcd0713b56aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Actividad Externalized Policy en .NET Framework 4.5
Este ejemplo muestra cómo la actividad ExternalizedPolicy4 permite ejecutar [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Windows Workflow Foundation (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objetos de [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Windows Workflow Foundation (WF 4.5) directamente mediante el motor de reglas que se distribuye con WF 3.5. Con esta actividad, se puede abrir y ejecutar cualquier <xref:System.Workflow.Activities.Rules.RuleSet>de WF 3.5 existente. Para obtener más información sobre el motor de reglas de WF 3.5 incluido como parte de Windows Workflow Foundation, lea [Introducción al motor de reglas de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=166079). Para obtener más información sobre cómo migrar las reglas a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] en [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], lea la Guía de migración en [Guía de migración](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
## <a name="projects-in-this-sample"></a>Proyectos en este ejemplo  
  
|Nombre del proyecto|Descripción|Archivos principales|  
|-|-|-|  
|ExternalizedPolicy4|Contiene la actividad ExternalizedPolicy4 y su diseñador de WF4.|**ExternalizedPolicy4.cs**: definición de actividad.<br /><br /> **ExternalizedPolicy4Designer.xaml**: diseñador personalizado para la actividad ExternalizedPolicy4. Utiliza el editor de reglas (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>) del motor de reglas de WF 3.5.|  
|ImperativeCodeClientSample|Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo mediante una aplicación ExternalizedPolicy4 que utiliza el código C# imperativo (no se utiliza ningún diseñador).|**ApplyDiscount.rules**: archivo con [!INCLUDE[wf1](../../../../includes/wf1-md.md)] definiciones de reglas.<br /><br /> **Order.cs**: tipo que representa un pedido de cliente. Las reglas se aplican a los objetos de este tipo.<br /><br /> **Program.cs**: configura y ejecuta un flujo de trabajo que tiene una actividad Policy4 para aplicar las reglas definidas en ApplyDiscount.rules a las instancias de objetos Order.<br /><br /> App.config: el archivo de configuración con la ruta de acceso del archivo de reglas.|  
|DesignerClientSample|Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo utilizando una aplicación ExternalPolicy4 en el diseñador de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1.XAML**: flujo de trabajo secuencial que utiliza una actividad Policy4 para realizar evaluaciones de reglas.<br /><br /> **Program.cs**: ejecuta una instancia de flujo de trabajo definida en Sequence1.xaml.|  
  
## <a name="the-externalizedpolicy4-activity"></a>La actividad ExternalizedPolicy4  
 La actividad ExternalizedPolicy4 es un objeto <xref:System.Activities.NativeActivity> que permite ejecutar objetos <xref:System.Workflow.Activities.Rules.RuleSet> de WF 3.5 dentro de flujos de trabajo de WF 4.5. El siguiente ejemplo es una definición simplificada del modelo de objetos público de la actividad.  
  
```  
public class ExternalizedPolicy4Activity<TResult>: CodeActivity  
{  
    public string RulesFilePath   
  
    public string RuleSetName           
  
    [RequiredArgument]  
    public InArgument<T> TargetObject   
  
    [RequiredArgument]  
    public OutArgument<T> ResultObject   
  
    public OutArgument<ValidationErrorCollection> ValidationErrors   
}  
```  
  
|Propiedad|Descripción|  
|-|-|  
|RuleSetFilePath|Ruta de acceso al archivo <xref:System.Workflow.Activities.Rules.RuleSet> de .NET Framework 3.5 que se evaluará cuando se ejecute la actividad.|  
|RuleSetName|Nombre del <xref:System.Workflow.Activities.Rules.RuleSet> que se va a utilizar dentro del archivo .rules.|  
|TargetObject|El objeto con el que se evaluarán los objetos <xref:System.Workflow.Activities.Rules.Rule> del <xref:System.Workflow.Activities.Rules.RuleSet>.|  
|ResultObject|El objeto resultante una vez aplicadas las reglas (por ejemplo, las reglas se aplican con el argumento Input y el resultado se almacena en el argumento Result.|  
|ValidationError|La lista de errores de validación devuelta por el motor de reglas de WF 3.5 al validar la clase <xref:System.Workflow.Activities.Rules.RuleSet> con el objeto de destino antes de realizar la ejecución.|  
  
## <a name="externalizedpolicy4-activity-designer"></a>Diseñador de la actividad ExternalizedPolicy4  
 El diseñador de ExternalizedPolicy4 le permite configurar una actividad para utilizar un conjunto de reglas existente sin escribir código. Simplemente establezca la ruta de acceso donde se encuentra localizado el archivo .rules y especifique el nombre <xref:System.Workflow.Activities.Rules.RuleSet> que desea utilizar. También le permite modificar el objeto <xref:System.Workflow.Activities.Rules.RuleSet>. Después de compilar la solución, se puede encontrar en el cuadro de herramientas de la sección Microsoft.Samples.Activities.Rules. El diseñador le permite seleccionar un archivo .rules y un objeto <xref:System.Workflow.Activities.Rules.RuleSet>. Cuando el **editar RuleSet** se hace clic en botón, WF 3.5 <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> se muestra. Este diálogo representa el editor de reglas de WF 3.5 re-hospedado y se utiliza para ver y modificar las reglas que ejecuta la actividad ExternalizedPolicy4.  
  
## <a name="policy4-and-externalpolicy4"></a>Policy4 y ExternalPolicy4  
 El [actividad Policy en .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) actividad le permite crear y ejecutar un conjunto de reglas de .NET Framework 3.5 en un flujo de trabajo de WF 4.5. El objeto <xref:System.Workflow.Activities.Rules.RuleSet> se serializa alineado en la definición XAML de la actividad Policy4. El ejemplo de ExternalizedPolicy4 muestra cómo utilizar un objeto <xref:System.Workflow.Activities.Rules.RuleSet> externo existente (incluido en un archivo .rules).  
  
## <a name="using-this-sample"></a>Utilizar este ejemplo  
 No se exige ninguna configuración especial para ejecutar este ejemplo. Abra la solución en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]y presione F5 para ejecutar la aplicación.  
  
 Este ejemplo contiene dos aplicaciones cliente: ImperativeCodeClientSample y DesignerClientSample. El cliente ImperativeCodeClientSample muestra cómo configurar y ejecutar la actividad ExternalizedPolicy4 utilizando el código imperativo C#. DesignerClientSample muestra cómo configurar y ejecutar la actividad ExternalizedPolicy4 mediante el diseñador.  
  
#### <a name="to-run-the-imperativecodeclientsample-application"></a>Para ejecutar la aplicación ImperativeCodeClientSample  
  
1.  Abra el archivo de solución Policy4sample.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  En **el Explorador de soluciones**, haga clic en el **ImperativeCodeClientSample** de proyecto y, a continuación, seleccione **establecer como proyecto de inicio**.  
  
3.  Presione CTRL+F5 para ejecutar el proyecto.  
  
#### <a name="to-run-the-designerclientsample-application"></a>Para ejecutar la aplicación DesignerClientSample  
  
1.  Abra el archivo de solución Policy4sample.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  En **el Explorador de soluciones**, haga clic en el **DesignerClientSample** de proyecto y, a continuación, seleccione **establecer como proyecto de inicio**.  
  
3.  Presione CTRL+MAYÚS+B para compilar el proyecto.  
  
4.  Presione CTRL+F5 para ejecutar el proyecto.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
