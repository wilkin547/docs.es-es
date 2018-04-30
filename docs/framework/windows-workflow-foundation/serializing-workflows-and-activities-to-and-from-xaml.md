---
title: Serializar flujos de trabajo y actividades a y de XAML
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a36b8a6bdf1a024f4ddee91bd937afac516e391f
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="serializing-workflows-and-activities-to-and-from-xaml"></a>Serializar flujos de trabajo y actividades a y de XAML
Además de compilarse en tipos incluidos en ensamblados, las definiciones de flujo de trabajo también se pueden serializar en XAML. Estas definiciones serializadas se pueden recargar para edición o inspección, pasar a un sistema de compilación para compilación, o bien cargar e invocar. En este tema se proporciona información general sobre la serialización de definiciones de flujo de trabajo y el trabajo con definiciones de flujo de trabajo de XAML.  
  
## <a name="working-with-xaml-workflow-definitions"></a>Trabajar con definiciones de flujo de trabajo de XAML  
 Para crear una definición de flujo de trabajo para la serialización, se utiliza la clase <xref:System.Activities.ActivityBuilder>. La creación de una clase <xref:System.Activities.ActivityBuilder> es muy similar a la creación de una clase <xref:System.Activities.DynamicActivity>. Se especifican los argumento deseados y se configuran las actividades que constituyen el comportamiento. En el siguiente ejemplo, se crea una actividad `Add` que toma dos argumentos de entrada, los suma y devuelve el resultado. Dado que esta actividad devuelve un resultado, se utiliza la clase <xref:System.Activities.ActivityBuilder%601> la genérica.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 Cada una de las instancias de <xref:System.Activities.DynamicActivityProperty> representa uno de los argumentos de entrada al flujo de trabajo y la propiedad <xref:System.Activities.ActivityBuilder.Implementation%2A> contiene las actividades que constituyen la lógica del flujo de trabajo. Observe que las expresiones de valor de r de este ejemplo son expresiones de Visual Basic. Las expresiones lambda no son serializables en XAML a menos que se use <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>. Si los flujos de trabajo serializados están pensados para abrirse o editarse en el diseñador de flujo de trabajo, se deben usar expresiones de Visual Basic. Para obtener más información, consulte [creación de flujos de trabajo, actividades y expresiones mediante código imperativo](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
 Para serializar la definición de flujo de trabajo representada por la instancia de <xref:System.Activities.ActivityBuilder> en XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> para crear <xref:System.Xaml.XamlWriter> y use después <xref:System.Xaml.XamlServices> para serializar la definición de flujo de trabajo mediante <xref:System.Xaml.XamlWriter>. <xref:System.Activities.XamlIntegration.ActivityXamlServices> tiene métodos para asignar instancias de <xref:System.Activities.ActivityBuilder> en XAML y viceversa, y cargar flujos de trabajo de XAML y devolver <xref:System.Activities.DynamicActivity> que se pueda invocar. En el siguiente ejemplo, la instancia de <xref:System.Activities.ActivityBuilder> del ejemplo anterior se serializa en una cadena y también se guarda en un archivo.  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
string serializedAB = sb.ToString();  
  
// Display the XAML to the console.  
Console.WriteLine(serializedAB);  
  
// Serialize the workflow to XAML and save it to a file.  
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");  
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw2, ab);  
sw.Close();  
```  
  
 En el siguiente ejemplo se representa el flujo de trabajo serializado.  
  
```xaml  
<Activity   
  x:TypeArguments="x:Int32"   
  x:Class="Add"   
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />  
  </x:Members>  
  <Sequence>  
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />  
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">  
      <Assign.To>  
        <OutArgument x:TypeArguments="x:Int32">  
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />  
          </OutArgument>  
      </Assign.To>  
    </Assign>  
  </Sequence>  
</Activity>  
```  
  
 Para cargar un flujo de trabajo serializado, el <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> se utiliza el método. Este método toma la definición de flujo de trabajo serializada y devuelve una clase <xref:System.Activities.DynamicActivity> que representa la definición de flujo de trabajo. Observe que el XAML no se deserializa hasta que se llama al método <xref:System.Activities.Activity.CacheMetadata%2A> en el cuerpo de la clase <xref:System.Activities.DynamicActivity> durante el proceso de validación. Si no se llama a la validación explícitamente, se realiza cuando se invoca el flujo de trabajo. Si la definición de flujo de trabajo de XAML no es válida, se produce una excepción <xref:System.ArgumentException>. Las excepciones que se producen desde el método <xref:System.Activities.Activity.CacheMetadata%2A> escapan de la llamada al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> y deben ser administradas por el autor de la llamada. En el siguiente ejemplo, el flujo de trabajo serializado del ejemplo anterior se carga y se invoca utilizando <xref:System.Activities.WorkflowInvoker>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 Cuando se invoca este flujo de trabajo, en la consola se muestra el siguiente resultado.  
  
 **25 + 15**  
**40**    
> [!NOTE]
>  Para obtener más información sobre cómo invocar los flujos de trabajo con argumentos de entrada y salidos, vea [usar WorkflowInvoker y WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) y <xref:System.Activities.WorkflowInvoker.Invoke%2A>.  
  
 Si el flujo de trabajo serializado contiene expresiones de C#, un <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instancia con su <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> propiedad establecida en `true` debe pasarse como un parámetro a <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, en caso contrario un <xref:System.NotSupportedException> se producirá un mensaje similar a la Después: `Expression Activity type 'CSharpValue`1' requiere compilación para poder ejecutarse.  Asegúrese de que se ha compilado el flujo de trabajo. "  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 Para obtener más información, consulte [expresiones de C#](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).  
  
 También se puede cargar una definición de flujo de trabajo serializado en una <xref:System.Activities.ActivityBuilder> instancia mediante el uso de la <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> método. Una vez cargado un flujo de trabajo serializado en una instancia de <xref:System.Activities.ActivityBuilder>, se puede inspeccionar y modificar. Esto resulta útil para los autores de diseñadores de flujo de trabajo personalizados y proporciona un mecanismo para guardar y recargar las definiciones de flujo de trabajo durante el proceso del diseño. En el siguiente ejemplo, se carga la definición de flujo de trabajo serializada del ejemplo anterior y se inspeccionan sus propiedades.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
