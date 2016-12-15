---
title: "C&#243;mo: Suscribir y cancelar la suscripci&#243;n a eventos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Editor de código, controladores de eventos"
  - "controladores de eventos [C#], crear"
  - "eventos [C#], crear utilizando el IDE"
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Suscribir y cancelar la suscripci&#243;n a eventos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La suscripción a un evento publicado por otra clase se realiza cuando se desea escribir código personalizado al que se llama cuando se produce ese evento.  Por ejemplo, puede suscribirse al evento `click` de un botón para que la aplicación realice alguna operación cuando el usuario haga clic en el botón.  
  
### Para suscribirse a eventos mediante el IDE de Visual Studio  
  
1.  Si no puede ver la ventana **Propiedades**, en la vista **Diseño** haga clic con el botón secundario del mouse en el formulario o control para el que desea crear un controlador de eventos y seleccione **Propiedades**.  
  
2.  En la parte superior de la ventana **Propiedades**, haga clic en el icono **Eventos**.  
  
3.  Haga doble clic en el evento que desea crear \(por ejemplo, el evento `Load`\).  
  
     [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] crea un método de control de eventos vacío y lo agrega al código.  También puede agregar manualmente el código en la vista **Código**.  Por ejemplo, las líneas siguientes de código declaran un método de control de eventos al que se llamará cuando la clase `Form` genere el evento `Load`.  
  
     [!code-cs[csProgGuideEvents#11](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-subscribe-to-and-unsubscribe-from-events_1.cs)]  
  
     La línea de código que es necesaria para suscribirse al evento también se genera automáticamente con el método `InitializeComponent` en el archivo Form1.Designer.cs del proyecto.  Se asemeja a lo siguiente:  
  
    ```  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### Para suscribirse a eventos mediante programación  
  
1.  Defina un método de control de eventos cuya firma coincida con la firma de delegado del evento.  Por ejemplo, si el evento se basa en el tipo de delegado <xref:System.EventHandler>, el siguiente código representa el código auxiliar del método:  
  
    ```  
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2.  Utilice el operador de suma y asignación \(`+=`\) para asociar el controlador de eventos al evento.  En el ejemplo siguiente, se asume que un objeto denominado `publisher` tiene un evento denominado `RaiseCustomEvent`.  Observe que la clase de suscriptor necesita una referencia a la clase de editor para suscribirse a sus eventos.  
  
    ```  
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     Observe que la sintaxis anterior es nueva en C\# 2.0.  Al igual que en la sintaxis de C\# 1.0, el delegado encapsulador debe crearse explícitamente mediante la palabra clave `new`:  
  
    ```  
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     También puede agregarse un controlador de eventos utilizando una expresión lambda:  
  
    ```  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
        this.Click += (s,e) => { MessageBox.Show(  
           ((MouseEventArgs)e).Location.ToString());};  
    }  
    ```  
  
     Para obtener más información, vea [Cómo: Usar expresiones lambda fuera de LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).  
  
### Para suscribirse a eventos mediante un método anónimo  
  
-   Si no tiene que cancelar la suscripción a un evento más adelante, puede utilizar el operador de suma y asignación \(`+=`\) para asociar un método anónimo al evento.  En el ejemplo siguiente, se asume que un objeto denominado `publisher` tiene un evento denominado `RaiseCustomEvent`  y que se ha definido una clase `CustomEventArgs` para proporcionar algún tipo de información específica del evento.  Observe que la clase de suscriptor necesita una referencia a `publisher` para suscribirse a sus eventos.  
  
    ```  
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     Es importante tener en cuenta que puede no resultar fácil cancelar la suscripción a un evento si se ha utilizado una función anónima para suscribirse a él.  Para cancelar la suscripción en esta situación, es necesario regresar al código donde se ha suscrito al evento, almacenar el método anónimo en una variable de delegado y, a continuación, agregar el delegado al evento.  En general, se recomienda que no utilice funciones anónimas para suscribirse a eventos si va a tener que cancelar la suscripción al evento en el código más adelante.  Para obtener más información sobre las funciones anónimas, vea [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## Cancelar una suscripción  
 Para impedir que se invoque el controlador de eventos cuando se produce el evento, basta con cancelar la suscripción al evento.  Para evitar que se pierdan recursos, debe cancelar la suscripción a los eventos antes de eliminar un objeto suscriptor.  Hasta que se cancela la suscripción a un evento, el delegado multidifusión subyacente al evento en el objeto de publicación tiene una referencia al delegado que encapsula el controlador de eventos del suscriptor.  Mientras el objeto de publicación mantenga esa referencia, la recolección de elementos no utilizados no eliminará el objeto suscriptor.  
  
#### Para cancelar la suscripción a un evento  
  
-   Utilice el operador de resta y asignación \(`-=`\) para cancelar la suscripción a un evento:  
  
    ```  
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     Cuando se haya cancelado la suscripción a un evento de todos los suscriptores, la instancia del evento en la clase de editor se establecerá en `null`.  
  
## Vea también  
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [event](../../../csharp/language-reference/keywords/event.md)   
 [Cómo: Publicar eventos que cumplan las directrices de .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)   
 [\-\= \(Operador\)](../../../csharp/language-reference/operators/subtraction-assignment-operator-1.md)   
 [\+\= \(Operador\)](../../../csharp/language-reference/operators/addition-assignment-operator.md)