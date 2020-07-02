---
title: Procedimiento para recibir notificaciones de excepciones de primera oportunidad
description: Obtenga notificaciones de excepciones de primera oportunidad en .NET mediante el evento FirstChanceException de la clase AppDomain, antes de que CLR busque controladores de excepciones.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- first-chance exception notifications
- exceptions, first chance notifications
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
ms.openlocfilehash: e8b5ae5fb69c7befd329316aee11523f79d73fcd
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104743"
---
# <a name="how-to-receive-first-chance-exception-notifications"></a>Procedimiento para recibir notificaciones de excepciones de primera oportunidad
El evento <xref:System.AppDomain.FirstChanceException> de la clase <xref:System.AppDomain> permite recibir una notificación de que se ha producido una excepción antes de que Common Language Runtime empiece a buscar controladores de excepciones.

 El evento se genera en el nivel de dominio de aplicación. Un subproceso de ejecución puede pasar a través de varios dominios de aplicación, así que una excepción no controlada en un dominio de aplicación podría controlarse en otro. La notificación se produce en cada dominio de aplicación que haya agregado un controlador para el evento, hasta que un dominio de aplicación controle la excepción.

 Los procedimientos y los ejemplos de este artículo muestran cómo recibir notificaciones de primera excepción en un programa sencillo con un dominio de aplicación y en un dominio de aplicación que cree.

 Para ver un ejemplo más complejo que abarca varios dominios de aplicación, vaya al ejemplo del evento <xref:System.AppDomain.FirstChanceException>.

## <a name="receiving-first-chance-exception-notifications-in-the-default-application-domain"></a>Recepción de notificaciones de primera excepción en el dominio de aplicación predeterminado
 En el siguiente procedimiento, el punto de entrada de la aplicación, el método `Main()`, se ejecuta en el dominio de aplicación predeterminado.

#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-default-application-domain"></a>Para mostrar notificaciones de primera excepción en el dominio de aplicación predeterminado

1. Defina un controlador de eventos para el evento <xref:System.AppDomain.FirstChanceException> mediante una función lambda y adjúntelo al evento. En este ejemplo, el controlador de eventos imprime el nombre del dominio de aplicación donde se ha controlado el evento y la propiedad <xref:System.Exception.Message%2A> de la excepción.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]

2. Inicie una excepción y captúrela. Antes de que el runtime busque el controlador de excepciones, se genera el evento <xref:System.AppDomain.FirstChanceException> y se muestra un mensaje. Este mensaje va seguido del que muestra el controlador de excepciones.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]

3. Inicie una excepción, pero no la capture. Antes de que el runtime busque un controlador de excepciones, se genera el evento <xref:System.AppDomain.FirstChanceException> y se muestra un mensaje. No hay ningún controlador de excepciones, por lo que la aplicación finaliza.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]

     El código que se muestra en los tres primeros pasos de este procedimiento forma una aplicación de consola completa. El resultado de la aplicación varía según el nombre del archivo .exe, porque el nombre del dominio de aplicación predeterminado consta del nombre y la extensión del archivo .exe. Vea el resultado del ejemplo siguiente.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]

## <a name="receiving-first-chance-exception-notifications-in-another-application-domain"></a>Recepción de notificaciones de primera excepción en otro dominio de aplicación
 Si el programa contiene más de un dominio de aplicación, puede elegir cuáles reciben notificaciones.

#### <a name="to-receive-first-chance-exception-notifications-in-an-application-domain-that-you-create"></a>Para recibir notificaciones de primera excepción en un dominio de aplicación que cree

1. Defina un controlador de eventos para el evento <xref:System.AppDomain.FirstChanceException>. En este ejemplo se usa un método `static` (`Shared` en Visual Basic) que imprime el nombre del dominio de aplicación donde se ha controlado el evento y la propiedad <xref:System.Exception.Message%2A> de la excepción.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]

2. Cree un dominio de aplicación y agregue el controlador de eventos al evento <xref:System.AppDomain.FirstChanceException> de ese dominio de aplicación. En este ejemplo, el dominio de aplicación se denomina `AD1`.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]

     Puede controlar este evento en el dominio de aplicación predeterminado de la misma manera. Use la propiedad <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType>`static` (`Shared` en Visual Basic) en `Main()` para obtener una referencia al dominio de aplicación predeterminado.

#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-application-domain"></a>Para mostrar notificaciones de primera excepción en el dominio de aplicación

1. Cree un objeto `Worker` en el dominio de aplicación que ha creado en el procedimiento anterior. La clase `Worker` debe ser pública y debe derivar de <xref:System.MarshalByRefObject>, como se muestra en el ejemplo completo al final de este artículo.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]

2. Llame a un método del objeto `Worker` que inicia una excepción. En este ejemplo, se llama al método `Thrower` dos veces. La primera vez, el argumento del método es `true`, lo que hace que el método capture su propia excepción. La segunda vez, el argumento es `false` y el método `Main()` captura la excepción en el dominio de aplicación predeterminado.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]

3. Coloque código en el método `Thrower` para controlar si el método controla su propia excepción.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente se crea un dominio de aplicación denominado `AD1` y se agrega un controlador de eventos al evento <xref:System.AppDomain.FirstChanceException> del dominio de aplicación. En el ejemplo se crea una instancia de la clase `Worker` en el dominio de aplicación y se llama a un método denominado `Thrower` que inicia una <xref:System.ArgumentException>. Según el valor de su argumento, el método captura la excepción o no la controla.

 Cada vez que el método `Thrower` inicia una excepción en `AD1`, se genera el evento <xref:System.AppDomain.FirstChanceException> en `AD1` y el controlador de eventos muestra un mensaje. Luego el runtime busca un controlador de excepciones. En el primer caso, el controlador de excepciones se encuentra en `AD1`. En el segundo caso, la excepción no se controla en `AD1` y se captura en el dominio de aplicación predeterminado.

> [!NOTE]
> El nombre del dominio de aplicación predeterminado es el mismo que el nombre del ejecutable.

 Si agrega un controlador para el evento <xref:System.AppDomain.FirstChanceException> al dominio de aplicación predeterminado, el evento se genera y se controla antes de que el dominio de aplicación predeterminado controle la excepción. Para verlo, agregue el código de C# `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` (en Visual Basic, `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`) al principio de `Main()`.

 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.AppDomain.FirstChanceException>
