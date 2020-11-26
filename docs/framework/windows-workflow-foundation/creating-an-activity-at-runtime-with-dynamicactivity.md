---
title: Crear una actividad en el tiempo de ejecución con DynamicActivity
description: DynamicActivity es una clase concreta sellada con un constructor público. Use la clase para ensamblar la funcionalidad de actividad en tiempo de ejecución mediante un DOM de actividad.
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: b65d7e385690b77d44c73e7a8a4ed38b04f30ea6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242102"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a>Crear una actividad en el tiempo de ejecución con DynamicActivity

<xref:System.Activities.DynamicActivity> es una clase concreta sellada con un constructor público. <xref:System.Activities.DynamicActivity> se puede usar para ensamblar la funcionalidad de actividad en tiempo de ejecución usando un DOM de actividad.  
  
## <a name="dynamicactivity-features"></a>Características de DynamicActivity  

 <xref:System.Activities.DynamicActivity> tiene acceso a las propiedades, argumentos y variables de ejecución pero no a los servicios en tiempo de ejecución como la programación de actividades secundarias o el seguimiento.  
  
 Las propiedades de nivel superior se pueden establecer con los objetos <xref:System.Activities.Argument> de flujo de trabajo. En código imperativo, estos argumentos se crean usando las propiedades CLR en un nuevo tipo. En XAML, se declaran con las etiquetas `x:Class` y `x:Member`.  
  
 Las actividades se construyeron mediante la interfaz <xref:System.Activities.DynamicActivity> con el diseñador usando <xref:System.ComponentModel.ICustomTypeDescriptor>. Las actividades creadas en el diseñador se pueden cargar dinámicamente mediante <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, tal y como se muestra en el siguiente procedimiento.  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a>Para crear una actividad en el tiempo de ejecución usando el código imperativo  
  
1. OpenVisual Studio 2010.  
  
2. Seleccione **archivo**, **nuevo**, **proyecto**. Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** . Seleccione **aplicación de consola de flujos de trabajo secuenciales** en la ventana **plantillas** . Proporcione el nombre siguiente al nuevo proyecto: DynamicActivitySample.  
  
3. Haga clic con el botón secundario en Workflow1. XAML en el proyecto HelloActivity y seleccione **eliminar**.  
  
4. Abra Program.cs. Agregue la siguiente directiva a la parte superior del archivo.  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. Sustituya el contenido del método `Main` con el siguiente código, que crea una actividad <xref:System.Activities.Statements.Sequence> que contiene una actividad <xref:System.Activities.Statements.WriteLine> única y la asigna a la propiedad <xref:System.Activities.DynamicActivity.Implementation%2A> de una nueva actividad dinámica.  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6. Ejecute la aplicación. Una ventana de consola con el texto "Hola mundo!" aparecerá.  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a>Para crear una actividad en el tiempo de ejecución usando XAML  
  
1. Abra Visual Studio 2010.  
  
2. Seleccione **archivo**, **nuevo**, **proyecto**. Seleccione **flujo de trabajo 4,0** en **Visual C#** en la ventana **tipos de proyecto** y seleccione el nodo **V2010** . Seleccione  **aplicación de consola de flujos de trabajo** en la ventana **plantillas** . Proporcione el nombre siguiente al nuevo proyecto: DynamicActivitySample.  
  
3. Abra Workflow1.xaml en el proyecto HelloActivity. Haga clic en la opción **argumentos** en la parte inferior del diseñador. Cree un nuevo argumento `In` llamado `TextToWrite` de tipo `String`.  
  
4. Arrastre una actividad **WriteLine** de la sección **primitivas** del cuadro de herramientas a la superficie del diseñador. Asigne el valor `TextToWrite` a la propiedad **Text** de la actividad.  
  
5. Abra Program.cs. Agregue la siguiente directiva a la parte superior del archivo.  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. Reemplace el contenido del método `Main` por el siguiente código.  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. Ejecute la aplicación. Una ventana de consola con el texto "Hola mundo!" Aparece .  
  
8. Haga clic con el botón secundario en el archivo Workflow1. XAML en el **Explorador de soluciones** y seleccione **Ver código**. Tenga en cuenta que la clase de actividad se crea con `x:Class` y la propiedad se crea con `x:Property`.  
  
## <a name="see-also"></a>Vea también

- [Crear flujos de trabajo, actividades y expresiones mediante código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md)
