---
title: Propiedades de ejecución del flujo de trabajo
ms.date: 03/30/2017
ms.assetid: a50e088e-3a45-4267-bd51-1a3e6c2d246d
ms.openlocfilehash: be9ae5924786ea1e23cc649034d927789c64e405
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293798"
---
# <a name="workflow-execution-properties"></a>Propiedades de ejecución del flujo de trabajo

A través del almacenamiento local para el subproceso (TLS), el CLR mantiene un contexto de ejecución para cada subproceso. Este contexto de ejecución rige propiedades de subproceso bien conocidas, como la identidad del subproceso, la transacción ambiente y el conjunto de permisos actual así como las propiedades de subproceso definidas por el usuario como ranuras con nombre.  
  
 A diferencia de los programas que tienen por objetivo directo el CLR, los programas de flujo de trabajo son árboles con ámbito jerárquico de actividades que se ejecutan en un entorno independiente del subproceso. Esto implica que los mecanismos de TLS estándar no se pueden usar directamente para determinar qué contexto está en ámbito de un elemento de trabajo determinado. Por ejemplo, dos bifurcaciones paralelas de ejecución podrían usar distintas transacciones, aunque es posible que el programador intercale su ejecución en el mismo subproceso de CLR.  
  
 Las propiedades de ejecución del flujo de trabajo proporcionan un mecanismo para agregar propiedades específicas del contexto al entorno de una actividad. De esta forma se permite que una actividad declare qué propiedades están en ámbito para su subárbol y se proporcionen enlaces para configurar y destruir el TLS para interoperar correctamente con objetos CLR.  
  
## <a name="creating-and-using-workflow-execution-properties"></a>Crear y usar propiedades de ejecución de flujo de trabajo  

 Las propiedades de ejecución de flujo de trabajo implementan generalmente la interfaz <xref:System.Activities.IExecutionProperty> , aunque las propiedades centradas en mensajería pueden implementar <xref:System.ServiceModel.Activities.ISendMessageCallback> y <xref:System.ServiceModel.Activities.IReceiveMessageCallback> en su lugar. Para crear una propiedad de ejecución de flujo de trabajo, cree una clase que implemente la interfaz <xref:System.Activities.IExecutionProperty> e implemente los miembros <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> y <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>. Estos miembros le dan a la propiedad de ejecución la oportunidad de configurar y anular el almacenamiento local de subprocesos durante cada pulso de trabajo de la actividad que contiene la propiedad, incluidas las actividades secundarias. En este ejemplo, se crea `ConsoleColorProperty`, que establece `Console.ForegroundColor`.  
  
```csharp  
class ConsoleColorProperty : IExecutionProperty  
{  
    public const string Name = "ConsoleColorProperty";  
  
    ConsoleColor original;  
    ConsoleColor color;  
  
    public ConsoleColorProperty(ConsoleColor color)  
    {  
        this.color = color;  
    }  
  
    void IExecutionProperty.SetupWorkflowThread()  
    {  
        original = Console.ForegroundColor;  
        Console.ForegroundColor = color;  
    }  
  
    void IExecutionProperty.CleanupWorkflowThread()  
    {  
        Console.ForegroundColor = original;  
    }  
}  
```  
  
 Los autores de actividad pueden usar esta propiedad registrándola en el reemplazo de ejecución de la actividad. En este ejemplo, se define una actividad `ConsoleColorScope` que registra `ConsoleColorProperty` al agregarla a la colección de <xref:System.Activities.NativeActivityContext.Properties%2A> de la clase <xref:System.Activities.NativeActivityContext> actual.  
  
```csharp  
public sealed class ConsoleColorScope : NativeActivity  
{  
    public ConsoleColorScope()  
        : base()  
    {  
    }  
  
    public ConsoleColor Color { get; set; }  
    public Activity Body { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        context.Properties.Add(ConsoleColorProperty.Name, new ConsoleColorProperty(this.Color));  
  
        if (this.Body != null)  
        {  
            context.ScheduleActivity(this.Body);  
        }  
    }  
}  
```  
  
 Cuando el cuerpo de la actividad comienza un pulso de trabajo, se llama al método <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> de la propiedad y cuando el pulso de trabajo ha finalizado, se llama a <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>. En este ejemplo, se crea un flujo de trabajo que usa una actividad <xref:System.Activities.Statements.Parallel> con tres bifurcaciones. Las primeras dos usan la actividad `ConsoleColorScope` mientras que la tercera no. Las tres bifurcaciones incluyen dos actividades <xref:System.Activities.Statements.WriteLine> y una actividad <xref:System.Activities.Statements.Delay>. Cuando la actividad <xref:System.Activities.Statements.Parallel> se ejecuta, las actividades contenidas en las bifurcaciones se ejecutan de modo intercalado, aunque cuando cada actividad secundaria se ejecuta, `ConsoleColorProperty` aplica el color de la consola correcto.  
  
```csharp  
Activity wf = new Parallel  
{  
    Branches =
    {  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Blue,  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new WriteLine  
                    {  
                        Text = "Start blue text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End blue text."  
                    }  
                }  
            }  
        },  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Red,  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new WriteLine  
                    {  
                        Text = "Start red text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End red text."  
                    }  
                }  
            }  
        },  
        new Sequence  
        {  
            Activities =
            {  
                new WriteLine  
                {  
                    Text = "Start default text."  
                },  
                new Delay  
                {  
                    Duration = TimeSpan.FromSeconds(1)  
                },  
                new WriteLine  
                {  
                    Text = "End default text."  
                }  
            }  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 Cuando se invoca el flujo de trabajo, se escribe la siguiente salida en la ventana de la consola.  
  
```console  
Start blue text.  
Start red text.  
Start default text.  
End blue text.  
End red text.  
End default text.  
```  
  
> [!NOTE]
> Aunque no se muestra en la salida anterior, cada línea de texto en la ventana de la consola se muestra en el color indicado.  
  
 Los autores de actividad personalizados pueden usar las propiedades de ejecución del flujo de trabajo y también proporcionan el mecanismo para controlar la administración de las actividades como <xref:System.ServiceModel.Activities.CorrelationScope> y <xref:System.Activities.Statements.TransactionScope>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.IExecutionProperty>
- <xref:System.Activities.IPropertyRegistrationCallback>
- <xref:System.Activities.RegistrationContext>
