---
title: RaiseEvent (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 46b93c060a12d82b34dafdf3aa4ea677df6f54cd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404296"
---
# <a name="raiseevent-statement"></a>RaiseEvent (Instrucción)
Desencadena un evento declarado en el nivel de módulo dentro de una clase, formulario o documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Partes  
 `eventname`  
 Necesario. Nombre del evento que se va a desencadenar.  
  
 `argumentlist`  
 Opcional. Lista delimitada por comas de variables, matrices o expresiones. El `argumentlist` argumento debe ir entre paréntesis. Si no hay ningún argumento, se deben omitir los paréntesis.  
  
## <a name="remarks"></a>Observaciones  
 El requerido `eventname` es el nombre de un evento declarado en el módulo. Sigue Visual Basic convenciones de nomenclatura de variables.  
  
 Si el evento no se ha declarado en el módulo en el que se genera, se produce un error. En el fragmento de código siguiente se muestra una declaración de evento y un procedimiento en el que se genera el evento.  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 No se puede usar `RaiseEvent` para generar eventos que no se declaran explícitamente en el módulo. Por ejemplo, todos los formularios heredan un <xref:System.Windows.Forms.Control.Click> evento de <xref:System.Windows.Forms.Form?displayProperty=nameWithType> , no se pueden generar usando `RaiseEvent` en un formulario derivado. Si declara un `Click` evento en el módulo de formulario, sombrea el evento del formulario <xref:System.Windows.Forms.Control.Click> . Todavía puede invocar el evento del formulario llamando <xref:System.Windows.Forms.Control.Click> al <xref:System.Windows.Forms.Control.OnClick%2A> método.  
  
 De forma predeterminada, un evento definido en Visual Basic genera sus controladores de eventos en el orden en que se establecen las conexiones. Dado que los eventos pueden tener `ByRef` parámetros, un proceso que se conecta tarde puede recibir parámetros modificados por un controlador de eventos anterior. Una vez que se ejecutan los controladores de eventos, se devuelve el control a la subrutina que provocó el evento.  
  
> [!NOTE]
> Los eventos no compartidos no se deben generar en el constructor de la clase en la que se declaran. Aunque estos eventos no causan errores en tiempo de ejecución, pueden no ser detectados por los controladores de eventos asociados. Utilice el `Shared` modificador para crear un evento compartido si necesita generar un evento desde un constructor.  
  
> [!NOTE]
> Puede cambiar el comportamiento predeterminado de los eventos mediante la definición de un evento personalizado. En el caso de los eventos personalizados, la `RaiseEvent` instrucción invoca al `RaiseEvent` descriptor de acceso del evento. Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan eventos para contar los segundos de 10 a 0. El código muestra algunos de los métodos, las propiedades y las instrucciones relacionados con eventos, incluida la `RaiseEvent` instrucción.  
  
 La clase que provoca un evento es el origen del evento, y los métodos que procesan el evento son los controladores de eventos. Un origen de eventos puede tener varios controladores para los eventos que genera. Cuando la clase genera el evento, ese evento se genera en cada clase que eligió controlar eventos para esa instancia del objeto.  
  
 El ejemplo también usa un formulario (`Form1`) con un botón (`Button1`) y un cuadro de texto (`TextBox1`). Al hacer clic en el botón, el primer cuadro de texto muestra una cuenta atrás de 10 a 0 segundos. Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".  
  
 El código de `Form1` especifica los estados inicial y terminal del formulario. También contiene el código que se ejecuta cuando se producen eventos.  
  
 Para usar este ejemplo, abra un nuevo proyecto de aplicación para Windows, agregue un botón denominado `Button1` y un cuadro de texto denominado `TextBox1` al formulario principal, denominado `Form1` . A continuación, haga clic con el botón secundario en el formulario y haga clic en **Ver código** para abrir el editor de código.  
  
 Agregue una `WithEvents` variable a la sección de declaraciones de la `Form1` clase.  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a>Ejemplo  
 Agregue el código siguiente al código de `Form1`. Reemplace los procedimientos duplicados que puedan existir, como `Form_Load` o `Button_Click` .  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 Presione F5 para ejecutar el ejemplo anterior y haga clic en el botón **iniciar**. El primer cuadro de texto empieza la cuenta atrás de los segundos. Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".  
  
> [!NOTE]
> El `My.Application.DoEvents` método no procesa los eventos exactamente del mismo modo que el formulario. Para permitir que el formulario controle los eventos directamente, puede usar multithreading. Para obtener más información, vea [subprocesamiento administrado](../../../standard/threading/index.md).  
  
## <a name="see-also"></a>Vea también

- [Eventos](../../programming-guide/language-features/events/index.md)
- [Event (Instrucción)](event-statement.md)
- [AddHandler (Instrucción)](addhandler-statement.md)
- [RemoveHandler (Instrucción)](removehandler-statement.md)
- [Asas](handles-clause.md)
