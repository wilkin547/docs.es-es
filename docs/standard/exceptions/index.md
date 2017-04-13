---
title: "Controlar y generar excepciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Common Language Runtime, excepciones"
  - "errores [.NET Framework], excepciones"
  - "excepciones [.NET Framework]"
  - "excepciones [.NET Framework], controlar"
  - "excepciones [.NET Framework], iniciar"
  - "filtrar excepciones"
  - "tiempo de ejecución, excepciones"
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Controlar y generar excepciones
<a name="top"></a> Las aplicaciones tienen que ser capaces de controlar de forma coherente los errores que se producen durante la ejecución. Common Language Runtime proporciona un modelo uniforme de notificación de errores a las a las aplicaciones. Todas las operaciones de .NET Framework indican un error iniciando excepciones.  
  
 Este tema contiene las siguientes secciones:  
  
-   [Excepciones en .NET Framework](#exceptions_in_the_net_framework)  
  
-   [Excepciones vs. métodos tradicionales de control de errores](#exceptions_vs_traditional_errorhandling_methods)  
  
-   [Cómo administra las excepciones el runtime](#how_the_runtime_manages_exceptions)  
  
-   [Filtrar excepciones de runtime](#filtering_runtime_exceptions)  
  
-   [Temas relacionados](#related_topics)  
  
-   [Referencia](#reference)  
  
<a name="exceptions_in_the_net_framework"></a>   
## Excepciones en .NET Framework  
 Una excepción es cualquier condición de error o comportamiento inesperado que encuentra un programa en ejecución. Las excepciones pueden generarse debido a un error en el código propio o en el código al que se llama \(por ejemplo, una biblioteca compartida\), a recursos del sistema operativo no disponibles, a condiciones inesperadas que encuentra el Common Language Runtime \(por ejemplo, imposibilidad de comprobar el código\), etc. La aplicación puede recuperarse de algunas de estas condiciones, pero no de todas. Aunque es posible recuperarse de la mayoría de las excepciones que se producen en la aplicación, no ocurre lo mismo con las excepciones de runtime.  
  
 En .NET Framework, una excepción es un objeto que hereda de la clase <xref:System.Exception?displayProperty=fullName>. Una excepción se inicia desde un área del código en la que ha producido un problema. La excepción se pasa hacia arriba en la pila hasta que la aplicación la controla o el programa finaliza.  
  
 [Volver al principio](#top)  
  
<a name="exceptions_vs_traditional_errorhandling_methods"></a>   
## Excepciones vs. métodos tradicionales de control de errores  
 Tradicionalmente, el modelo de control de errores de un lenguaje se basaba en el modo exclusivo del lenguaje de detectar los errores y buscarles controladores, o bien en el mecanismo de control de errores ofrecido por el sistema operativo. El runtime implementa control de excepciones con las características siguientes:  
  
-   Controla las excepciones independientemente del lenguaje que genera o controla la excepción.  
  
-   No requiere ninguna sintaxis de lenguaje específica para controlar las excepciones, pero permite que cada lenguaje defina su propia sintaxis.  
  
-   Permite que las excepciones se inicien en varios procesos en incluso límites de máquina.  
  
 Las excepciones ofrecen varias ventajas sobre otros métodos de notificación de errores, por ejemplo, los códigos de retorno; los errores no pasan desapercibidos; los valores no válidos no continúan propagándose por el sistema; no es necesario comprobar los códigos de retorno; se puede agregar fácilmente el código de control de excepciones para aumentar la confiabilidad del programa; por último, el control de excepciones del runtime es más rápido que el control de errores de C\+\+ basado en Windows.  
  
 Dado que los subprocesos de ejecución recorren de forma rutinaria bloques de código administrado y no administrado, el runtime pueden iniciar o detectar las excepciones tanto en código administrado como no administrado. El código no administrado puede incluir excepciones SEH de tipo C\+\+ y HRESULTS basados en COM.  
  
<a name="how_the_runtime_manages_exceptions"></a>   
## Cómo administra las excepciones el runtime  
 El runtime usa un modelo de control de excepciones basado en objetos de excepción y bloques protegidos de código. Para representar una excepción cuando se produce, se crea un objeto <xref:System.Exception>.  
  
 El runtime crea una tabla de información de excepciones para cada ejecutable. Cada método del ejecutable tiene una matriz asociada de información de control de excepciones \(que puede estar vacía\) en la tabla de información de excepciones. Cada entrada de la matriz describe un bloque protegido de código, los filtros de excepción asociados a ese código y los controladores de excepción \(instrucciones `catch`\). Esta tabla de excepciones es muy eficiente y no penaliza el rendimiento en el tiempo de procesador ni en el uso de memoria cuando no se producen excepciones. Los recursos solo se usan cuando se produce una excepción.  
  
 La tabla de información de excepciones representa cuatro tipos de controladores de excepciones para los bloques protegidos:  
  
-   Un controlador `finally` que se ejecuta cada vez que se cierra el bloque, tanto si se cierra por flujo de control normal o debido a una excepción no controlada.  
  
-   Un controlador de errores que debe ejecutarse si se produce una excepción, pero que no se ejecuta al finalizar el flujo de control normal.  
  
-   Un controlador filtrado por tipo que controla las excepciones de una clase especificada o de cualquiera de sus clases derivadas.  
  
-   Un controlador filtrado por usuario que ejecuta código especificado por el usuario y determina si la excepción debe controlarse con el controlador asociado o debe pasarse al siguiente bloque protegido.  
  
 Cada lenguaje implementa estos controladores de excepción según sus especificaciones. Por ejemplo, Visual Basic proporciona acceso al controlador filtrado por usuario mediante una comparación de variables \(con la palabra clave `When`\) en la instrucción `catch`; C\# no implementa el controlador filtrado por usuario.  
  
 Cuando se produce una excepción, el runtime inicia un proceso de dos pasos:  
  
1.  El runtime busca la matriz del primer bloque protegido que realiza lo siguiente:  
  
    -   Protege una región que contiene la instrucción que se está ejecutando actualmente.  
  
    -   Contiene un controlador de excepciones o un filtro que controla la excepción.  
  
2.  Si se produce una coincidencia, el runtime crea un objeto <xref:System.Exception> que describe la excepción. A continuación, el runtime ejecuta todas las instrucciones `finally` o las instrucciones de error entre la instrucción donde se produjo la excepción y la instrucción que la controla. Tenga en cuenta que el orden de los controladores de excepciones es importante; el controlador de excepciones más interno es el que se evalúa primero. Observe también que los controladores de excepciones pueden tener acceso a las variables locales y a la memoria local de la rutina que detecta la excepción; sin embargo, se pierden los valores intermedios en el momento en que se inicia la excepción.  
  
     Si no hay ninguna coincidencia en el método actual, el runtime explora todos los llamadores del método actual y sigue esta ruta de acceso en dirección ascendente por la pila. Si ningún llamador tiene una coincidencia, el runtime permite que el depurador tenga acceso a la excepción. Si el depurador no se asocia a la excepción, el runtime genera el evento <xref:System.AppDomain.UnhandledException?displayProperty=fullName>. Si no hay ningún agente de escucha para este evento, el runtime vuelca un seguimiento de pila y finaliza la aplicación.  
  
 [Volver al principio](#top)  
  
<a name="filtering_runtime_exceptions"></a>   
## Filtrar excepciones de runtime  
 Puede filtrar las excepciones que detecte y controle por tipo o según los criterios definidos por el usuario.  
  
 Los controladores filtrados por tipo administran un tipo concreto de excepción \(o de sus clases derivadas\). En el ejemplo siguiente se muestra un controlador filtrado por tipo que está diseñado para detectar una excepción concreta, que en este caso es <xref:System.IO.FileNotFoundException>.  
  
 [!code-cpp[CatchException#5](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception3.cpp#5)]
 [!code-csharp[CatchException#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception3.cs#5)]
 [!code-vb[CatchException#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception3.vb#5)]  
  
 Los controladores de excepciones filtradas por usuario detectan y controlan las excepciones en función de los requisitos que se definen para la excepción. Para obtener más información acerca del filtrado de excepciones de este modo, vea el artículo sobre [uso de excepciones específicas en un bloque Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md).  
  
 [Volver al principio](#top)  
  
<a name="related_topics"></a>   
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Clase Exception y propiedades](../../../docs/standard/exceptions/exception-class-and-properties.md)|Describe los elementos de un objeto de excepción.|  
|[Jerarquía de excepciones](../../../docs/standard/exceptions/exception-hierarchy.md)|Describe las excepciones de las que derivan la mayoría de las excepciones.|  
|[Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)|Explica cómo controlar excepciones mediante instrucciones catch, throw y finally.|  
|[Procedimientos recomendados para excepciones](../../../docs/standard/exceptions/best-practices-for-exceptions.md)|Describe los métodos sugeridos para controlar excepciones.|  
|[Controlar excepciones de interoperabilidad COM](../../../docs/standard/exceptions/handling-com-interop-exceptions.md)|Describe cómo controlar las excepciones iniciadas y detectadas en código no administrado.|  
|[How to: Map HRESULTs and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)|Describe la asignación de excepciones entre código administrado y no administrado.|  
  
<a name="reference"></a>   
## Referencia  
 <xref:System.Exception?displayProperty=fullName>  
  
 <xref:System.ApplicationException?displayProperty=fullName>  
  
 <xref:System.SystemException?displayProperty=fullName>