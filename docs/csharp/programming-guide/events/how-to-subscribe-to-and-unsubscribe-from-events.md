---
title: 'Procedimiento Suscribir y cancelar la suscripción a eventos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 3df357cb15f7f77cefbf360dd9615ce246afe2ea
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705332"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a>Procedimiento Suscribir y cancelar la suscripción a eventos (Guía de programación de C#)
La suscripción a un evento publicado por otra clase se realiza cuando quiere escribir código personalizado al que se llama cuando se produce ese evento. Por ejemplo, puede suscribirse al evento `click` de un botón para que la aplicación realice alguna operación cuando el usuario haga clic en el botón.  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a>Para suscribirse a eventos mediante el IDE de Visual Studio  
  
1. Si no puede ver la ventana **Propiedades**, en la vista **Diseño** haga clic con el botón derecho en el formulario o control para el que quiere crear un controlador de eventos y seleccione **Propiedades**.  
  
2. En la parte superior de la ventana **Propiedades**, haga clic en el icono **Eventos**.  
  
3. Haga doble clic en el evento que quiera crear, por ejemplo, el evento `Load`.  
  
     Visual C# crea un método de controlador de eventos vacío y lo agrega al código. También puede agregar manualmente el código en la vista **Código**. Por ejemplo, las líneas siguientes de código declaran un método de controlador de eventos al que se llamará cuando la clase `Form` genere el evento `Load`.  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     La línea de código que es necesaria para suscribirse al evento también se genera automáticamente con el método `InitializeComponent` en el archivo Form1.Designer.cs del proyecto. Se parece a lo siguiente:  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a>Para suscribirse a eventos mediante programación  
  
1. Defina un método de controlador de eventos cuya firma coincida con la firma de delegado del evento. Por ejemplo, si el evento se basa en el tipo de delegado <xref:System.EventHandler>, el siguiente código representa el código auxiliar del método:  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2. Use el operador de suma y asignación (`+=`) para asociar el controlador de eventos al evento. En el ejemplo siguiente, se asume que un objeto denominado `publisher` tiene un evento denominado `RaiseCustomEvent`. Observe que la clase de suscriptor necesita una referencia a la clase de editor para suscribirse a sus eventos.  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     Observe que la sintaxis anterior es nueva en C# 2.0. Al igual que en la sintaxis de C# 1.0, el delegado encapsulador debe crearse explícitamente mediante la palabra clave `new`:  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     También puede usar una [expresión lambda](../statements-expressions-operators/lambda-expressions.md) para especificar un controlador de eventos:
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        this.Click += (s,e) =>
            {
                MessageBox.Show(((MouseEventArgs)e).Location.ToString());
            };
    }  
    ```  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a>Para suscribirse a eventos mediante un método anónimo  
  
- Si no tiene que cancelar la suscripción a un evento más adelante, puede usar el operador de suma y asignación (`+=`) para asociar un método anónimo al evento. En el ejemplo siguiente, se presupone que un objeto denominado `publisher` tiene un evento denominado `RaiseCustomEvent` y que se ha definido una clase `CustomEventArgs` para proporcionar algún tipo de información específica del evento. Observe que la clase de suscriptor necesita una referencia a `publisher` para suscribirse a sus eventos.  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     Es importante tener en cuenta que puede no resultar fácil cancelar la suscripción a un evento si se ha usado una función anónima para suscribirse a él. Para cancelar la suscripción en esta situación, es necesario regresar al código donde se ha suscrito al evento, almacenar el método anónimo en una variable de delegado y, después, agregar el delegado al evento. En general, se recomienda que no use funciones anónimas para suscribirse a eventos si va a tener que cancelar la suscripción al evento en el código más adelante. Para obtener más información sobre las funciones anónimas, vea [Funciones anónimas](../statements-expressions-operators/anonymous-functions.md).  
  
## <a name="unsubscribing"></a>Cancelar una suscripción  
 Para impedir que se invoque el controlador de eventos cuando se produce el evento, puede cancelar la suscripción al evento. Para evitar que se pierdan recursos, debe cancelar la suscripción a los eventos antes de eliminar un objeto suscriptor. Hasta que se cancela la suscripción a un evento, el delegado multidifusión subyacente al evento en el objeto de publicación tiene una referencia al delegado que encapsula el controlador de eventos del suscriptor. Mientras el objeto de publicación mantenga esa referencia, la recolección de elementos no utilizados no eliminará el objeto suscriptor.  
  
#### <a name="to-unsubscribe-from-an-event"></a>Para cancelar la suscripción a un evento  
  
- Use el operador de resta y asignación (`-=`) para cancelar la suscripción a un evento:  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     Cuando se haya cancelado la suscripción a un evento de todos los suscriptores, la instancia del evento en la clase de editor se establecerá en `null`.  
  
## <a name="see-also"></a>Vea también

- [Eventos](./index.md)
- [event](../../language-reference/keywords/event.md)
- [Procedimiento para publicar eventos que cumplan las instrucciones de .NET Framework](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [Operadores - y -=](../../language-reference/operators/subtraction-operator.md)
- [Operadores + y +=](../../language-reference/operators/addition-operator.md)
