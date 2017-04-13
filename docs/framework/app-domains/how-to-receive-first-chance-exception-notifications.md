---
title: "C&#243;mo: Recibir notificaciones de excepciones de primera oportunidad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "excepciones, notificaciones de primera oportunidad"
  - "notificaciones de excepciones de primera oportunidad"
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Recibir notificaciones de excepciones de primera oportunidad
El evento <xref:System.AppDomain.FirstChanceException> de la clase <xref:System.AppDomain> permite recibir una notificación sobre una excepción que se produce antes de que el Common Language Runtime comience a buscar los controladores de excepciones.  
  
 El evento se genera en el nivel del dominio de aplicación.  Un subproceso de ejecución puede atravesar varios dominios de aplicación, de modo que una excepción que no se controla en un dominio se puede controlar en otro.  La notificación se produce en cada dominio de aplicación que ha agregado un controlador para el evento, hasta que un dominio de aplicación controle la excepción.  
  
 Los procedimientos y los ejemplos de este artículo muestran cómo recibir notificaciones de excepciones de primera oportunidad en un programa simple que tiene un dominio de aplicación y en un dominio de aplicación que se crea.  
  
 Para obtener un ejemplo más complejo que abarca varios dominios de aplicación, vea el ejemplo para el evento <xref:System.AppDomain.FirstChanceException>.  
  
## Recibir notificaciones de primera oportunidad en el dominio de aplicación predeterminado  
 En el siguiente procedimiento, el punto de entrada de la aplicación, el método `Main()`, se ejecuta en el dominio de aplicación predeterminado.  
  
#### Para mostrar notificaciones de primera oportunidad en el dominio de aplicación predeterminado  
  
1.  Defina un controlador para el evento <xref:System.AppDomain.FirstChanceException> mediante una función lambda y adjúntelo al evento.  En este ejemplo, el controlador de eventos imprime el nombre del dominio de aplicación donde se controló el evento y la propiedad <xref:System.Exception.Message%2A> de la excepción.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]  
  
2.  Produzca una excepción y detéctela.  Antes de que el runtime encuentre el controlador de excepciones, se produce el evento <xref:System.AppDomain.FirstChanceException> y se muestra un mensaje.  Este mensaje va seguido del mensaje mostrado por el controlador de excepciones.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]  
  
3.  Inicie una excepción pero no la detecte.  Antes de que el runtime busque un controlador de excepciones, se produce el evento <xref:System.AppDomain.FirstChanceException> y se muestra un mensaje.  No hay ningún controlador de excepciones, de modo que la aplicación finaliza.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]  
  
     El código que se muestra en los tres primeros pasos de este procedimiento forma una aplicación de consola completa.  La salida de la aplicación varía, dependiendo del nombre del archivo .exe, porque el nombre del dominio de aplicación predeterminado consta del nombre y de la extensión del archivo .exe.  A continuación, se muestra la salida de este ejemplo.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]  
  
## Recibir notificaciones de primera oportunidad en otro dominio de aplicación  
 Si su programa contiene más de un dominio de aplicación, puede elegir cuáles reciben notificaciones.  
  
#### Para recibir notificaciones de excepción de primera oportunidad en un dominio de aplicación creado por usted  
  
1.  Defina un controlador de eventos para el evento <xref:System.AppDomain.FirstChanceException>.  En este ejemplo se utiliza un método `static` \(`Shared` en Visual Basic\) que imprime el nombre del dominio de aplicación donde se controló el evento y la propiedad <xref:System.Exception.Message%2A> de la excepción.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]  
  
2.  Cree un dominio de aplicación y agregue el controlador de eventos al evento <xref:System.AppDomain.FirstChanceException> para ese dominio de aplicación.  En este ejemplo, el dominio de aplicación se denomina `AD1`.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]  
  
     Puede controlar este evento en el dominio de aplicación predeterminado de la misma manera.  Utilice la propiedad <xref:System.AppDomain.CurrentDomain%2A?displayProperty=fullName> `static` \(`Shared` en Visual Basic\) en `Main()` para obtener una referencia al dominio de aplicación predeterminado.  
  
#### Para mostrar notificaciones de primera oportunidad en el dominio de aplicación  
  
1.  Cree un objeto `Worker` en el dominio de aplicación creado en el procedimiento anterior.  La clase `Worker` debe ser pública y debe derivar de <xref:System.MarshalByRefObject>, como se muestra en el ejemplo completo al final de este artículo.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]  
  
2.  Llame a un método del objeto `Worker` que produce una excepción.  En este ejemplo, se llama dos veces al método `Thrower`.  La primera vez, el argumento de método es `true`, que hace que el método detecte su propia excepción.  La segunda, el argumento es `false` y el método `Main()` detecta la excepción en el dominio de aplicación predeterminado.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]  
  
3.  Ponga código en el método `Thrower` para comprobar si controla su propia excepción.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]  
  
## Ejemplo  
 En el siguiente ejemplo se crea un dominio de aplicación denominado `AD1` y se agrega un controlador de eventos al evento <xref:System.AppDomain.FirstChanceException> del dominio de aplicación.  En el ejemplo se crea una instancia de la clase `Worker` en el dominio de aplicación y se llama a un método `Thrower` que produce una excepción <xref:System.ArgumentException>.  Dependiendo del valor de su argumento, el método detecta la excepción o no.  
  
 Cada vez que el método `Thrower` produce una excepción en `AD1`, se genera el evento <xref:System.AppDomain.FirstChanceException> en `AD1` y el controlador de eventos muestra un mensaje.  Después, el motor en tiempo de ejecución busca un controlador de excepciones.  En el primer caso, el controlador de excepciones se encuentra en `AD1`.  En el segundo, la excepción no se controla en `AD1` pero se detecta en el dominio de aplicación predeterminado.  
  
> [!NOTE]
>  El nombre del dominio de aplicación predeterminado es el mismo que el del ejecutable.  
  
 Si agrega un controlador para el evento <xref:System.AppDomain.FirstChanceException> en el dominio de aplicación predeterminado, el evento se genera y controla antes de que el dominio de aplicación predeterminado controle la excepción.  Para verlo, agregue el código de C\# `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` \(en Visual Basic, `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceExceptio`n\) al comienzo de `Main()`.  
  
 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]  
  
## Compilar el código  
  
-   Este ejemplo es una aplicación de línea de comandos.  Para compilarlo y ejecutarlo en [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], agregue el código de C\# `Console.ReadLine();` \(en Visual Basic, `Console.ReadLine()`\) al final de `Main()` para impedir que la ventana de comandos se cierre antes de haber leído el resultado.  
  
## Vea también  
 <xref:System.AppDomain.FirstChanceException>