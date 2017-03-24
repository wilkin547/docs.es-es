---
title: "RaiseEvent (instrucción) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 059b1347c4a35b896f5aa19cadb28fbceb8b25c9
ms.lasthandoff: 03/13/2017

---
# <a name="raiseevent-statement"></a>RaiseEvent (Instrucción)
Desencadena un evento declarado en el nivel de módulo dentro de una clase, formulario o documento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Elementos  
 `eventname`  
 Obligatorio. Nombre del evento para desencadenar.  
  
 `argumentlist`  
 Opcional. Lista delimitada por comas de variables, matrices o expresiones. El `argumentlist` argumento debe estar entre paréntesis. Si no hay ningún argumento, se deben omitir los paréntesis.  
  
## <a name="remarks"></a>Comentarios  
 Necesario `eventname` es el nombre de un evento declarado dentro del módulo. Sigue convenciones de nomenclatura de Visual Basic.  
  
 Si el evento no se ha declarado dentro del módulo en el que se genera, se produce un error. El siguiente fragmento de código muestra una declaración de evento y un procedimiento en el que se genera el evento.  
  
 [!code-vb[VbVbalrEvents&#37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 No se puede utilizar `RaiseEvent` para generar eventos que no estén explícitamente declarados en el módulo. Por ejemplo, todos los formularios heredan un <xref:System.Windows.Forms.Control.Click>evento desde <xref:System.Windows.Forms.Form?displayProperty=fullName>, no se genera utilizando `RaiseEvent` en un formulario derivado.</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click> Si declara un `Click` eventos en el módulo de formulario, sombrea el propio formulario <xref:System.Windows.Forms.Control.Click>eventos.</xref:System.Windows.Forms.Control.Click> Se puede invocar el formulario <xref:System.Windows.Forms.Control.Click>evento llamando a la <xref:System.Windows.Forms.Control.OnClick%2A>método.</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click>  
  
 De forma predeterminada, un evento definido en Visual Basic provoca sus controladores de eventos en el orden en que se establecen las conexiones. Dado que los eventos pueden tener `ByRef` parámetros, un proceso que se conecta tarde puede recibir parámetros modificados por un controlador de eventos anterior. Después de ejecutan los controladores de eventos, el control se devuelve a la subrutina que provocó el evento.  
  
> [!NOTE]
>  Los eventos no compartidos no se deben producir en el constructor de la clase en que se declaran. Aunque dichos eventos no provocan errores en tiempo de ejecución, no pueden detectar mediante los controladores de eventos asociados. Utilice la `Shared` modificador para crear un evento compartido si necesita generar un evento desde un constructor.  
  
> [!NOTE]
>  Puede cambiar el comportamiento predeterminado de eventos mediante la definición de un evento personalizado. Para los eventos personalizados, la `RaiseEvent` instrucción invoca el evento `RaiseEvent` descriptor de acceso. Para obtener más información sobre los eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan eventos para contar los segundos de 10 a 0. El código muestra algunos de los métodos relacionados con eventos, propiedades e instrucciones, incluida la `RaiseEvent` instrucción.  
  
 La clase que provoca un evento es el origen del evento, y los métodos que procesan el evento son los controladores de eventos. Un origen de eventos puede tener varios controladores para los eventos que genera. Cuando la clase genera el evento, ese evento se genera en cada clase que eligió controlar eventos para esa instancia del objeto.  
  
 El ejemplo también usa un formulario (`Form1`) con un botón (`Button1`) y un cuadro de texto (`TextBox1`). Al hacer clic en el botón, el primer cuadro de texto muestra una cuenta atrás de 10 a 0 segundos. Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".  
  
 El código de `Form1` especifica los estados inicial y terminal del formulario. También contiene el código que se ejecuta cuando se producen eventos.  
  
 Para utilizar este ejemplo, abra un nuevo proyecto de aplicación de Windows, agregue un botón denominado `Button1` y un cuadro de texto denominado `TextBox1` para el formulario principal, denominado `Form1`. A continuación, haga clic en el formulario y haga clic en **ver código** para abrir el Editor de código.  
  
 Agregar un `WithEvents` variable en la sección de declaraciones de la `Form1` clase.  
  
 [!code-vb[VbVbalrEvents&#14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Agregue el código siguiente al código de `Form1`. Reemplace los procedimientos que pueden existir, como duplicados `Form_Load`, o `Button_Click`.  
  
 [!code-vb[VbVbalrEvents&#15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Presione F5 para ejecutar el ejemplo anterior y haga clic en el botón **iniciar**. El primer cuadro de texto empieza la cuenta atrás de los segundos. Cuando transcurre el tiempo (10 segundos), el primer cuadro de texto muestra "Done".  
  
> [!NOTE]
>  El `My.Application.DoEvents` método procesa los eventos exactamente del mismo modo que el formulario. Para permitir que el formulario controle directamente los eventos, puede usar multithreading. Para obtener más información, consulte [subprocesos](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler (instrucción)](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Identificadores](../../../visual-basic/language-reference/statements/handles-clause.md)
