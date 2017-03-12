---
title: "Delegados (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "02/25/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "delegados [Visual Basic]"
  - "código de Visual Basic, delegados"
ms.assetid: 410b60dc-5e60-4ec0-bfae-426755a2ee28
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Delegados (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los delegados son objetos que hacen referencia a métodos.  Algunas veces están descritos como *punteros de función con seguridad de tipos* porque son parecidos a los punteros de función utilizados en otros lenguajes de programación.  Sin embargo, a diferencia de los punteros a función, los delegados de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] son un tipo de referencia basado en la clase <xref:System.Delegate?displayProperty=fullName>.  Los delegados pueden hacer referencia a los dos métodos compartidos, métodos a los que se pueden llamar sin una instancia específica de una clase, y a métodos de instancia.  
  
## Delegados y eventos  
 Los delegados son útiles en situaciones donde es necesario un intermediario entre el procedimiento que realiza una llamada y el procedimiento que la recibe.  Por ejemplo, puede que desee que un objeto que provoca eventos sea capaz de llamar a diferentes controladores de eventos bajo diferentes circunstancias.  Desgraciadamente, el objeto que provoca los eventos no puede conocer de antemano qué controlador de eventos controla un evento concreto.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] permite asociar dinámicamente los controladores de eventos a eventos mediante la creación de un delegado al usar la instrucción `AddHandler`.  En tiempo de ejecución, el delegado remite las llamadas al controlador de eventos adecuado.  
  
 Aunque puede crear sus propios delegados, en la mayoría de los casos [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] crea el delegado y se ocupa de los detalles.  Por ejemplo, una instrucción `Event` define de forma implícita una clase delegada denominada `<EventName>EventHandler` como clase anidada de la clase que contiene la instrucción `Event`, y con la misma firma que el evento.  La instrucción `AddressOf` crea implícitamente una instancia de un delegado que hace referencia a un procedimiento concreto.  Las dos líneas de código siguientes son equivalentes.  En la primera línea, se ve la creación explícita de una instancia de `Eventhandler`, con una referencia al método `Button1_Click` enviada como argumento.  La segunda línea es una manera más conveniente de conseguir el mismo resultado.  
  
 [!code-vb[VbVbalrDelegates#6](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/delegates_1.vb)]  
  
 Puede utilizar el método abreviado para crear delegados en cualquier lugar donde el compilador pueda determinar el tipo de delegado por el contexto.  
  
## Declarar eventos que utilicen un tipo de delegado existente  
 En algunas situaciones, puede que desee declarar un evento para que utilice un tipo de delegado existente como delegado subyacente.  La sintaxis siguiente describe cómo hacerlo:  
  
 [!code-vb[VbVbalrDelegates#7](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/delegates_2.vb)]  
  
 Esto resulta útil cuando se desea enrutar diversos eventos hacia el mismo controlador.  
  
## Variables delegadas y parámetros  
 Puede utilizar delegados para otras tareas, no relacionadas con eventos, como un subprocesamiento libre o con procedimientos que necesiten llamar a diferentes versiones de funciones en tiempo de ejecución.  
  
 Por ejemplo, suponga que tiene una aplicación de anuncio clasificado que incluye un cuadro de lista con nombres de coches.  Los anuncios están ordenados por títulos, que normalmente son las marcas de los coches.  Un problema con el que puede encontrarse se produce cuando algunos coches incluyen el año del coche antes de la marca.  El problema es que la funcionalidad de ordenación integrada del cuadro de lista ordena únicamente por códigos de carácter; primero coloca todos los anuncios que empiezan por el año y, a continuación, los anuncios que empiezan por la marca.  
  
 Para corregir este problema, puede crear un procedimiento de ordenación en una clase que utilice la ordenación alfabética estándar en la mayoría de los cuadros de lista, pero que pueda cambiar en tiempo de ejecución al procedimiento de ordenación personalizado para anuncios de coches.  Para ello, pasa el procedimiento de ordenación personalizado a la clase de ordenación en tiempo de ejecución, utilizando delegados.  
  
## Expresiones AddressOf y lambda  
 Cada clase delegada define un constructor al cual se pasa la especificación de un método de objeto.  Un argumento para un constructor delegado debe ser una referencia a un método o una expresión lambda.  
  
 Para especificar una referencia a un método, utilice la sintaxis siguiente:  
  
 `AddressOf` \[`expression`.\]`methodName`  
  
 El tipo de tiempo de compilación de `expression` debe ser el nombre de una clase o interfaz que contenga un método del nombre especificado cuya firma coincida con la firma de la clase delegada.  `methodName` puede ser un método compartido o un método de instancia.  Aunque se cree un delegado para el método predeterminado de la clase, `methodName` no es opcional.  
  
 Para especificar una expresión lambda, utilice la sintaxis siguiente:  
  
 `Function` \(\[`parm` como `type`, `parm2` como `type2`, ...\]\) `expression`  
  
 En el siguiente ejemplo se muestra el uso de las expresiones `AddressOf` y lambda para especificar la referencia para un delegado.  
  
 [!code-vb[VbVbalrDelegates#15](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/delegates_3.vb)]  
  
 La firma de la función debe coincidir con la del tipo de delegado.  Para obtener más información sobre las expresiones lambda, vea [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  Para obtener más ejemplos de expresiones lambda y asignaciones de `AddressOf` a delegados, vea [Conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Cómo: Invocar un método delegado](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)|Proporciona un ejemplo que muestra cómo asociar un método a un delegado e invocar luego este método a través del delegado.|  
|[Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)|Muestra cómo utilizar los delegados para pasar un procedimiento a otro procedimiento.|  
|[Conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)|Describe cómo se pueden asignar funciones y subrutinas a delegados o controladores de eventos aunque sus firmas no sean idénticas.|  
|[Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md)|Proporciona información general sobre los eventos en Visual Basic.|