---
title: "Procedimientos recomendados para excepciones | Microsoft Docs"
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
  - "excepciones, procedimientos recomendados"
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
caps.latest.revision: 28
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 28
---
# Procedimientos recomendados para excepciones
Una aplicación diseñada correctamente controla las excepciones y los errores para evitar que se bloquee.  En este artículo se describen los procedimientos recomendados para controlar y crear excepciones.  
  
## Control de excepciones  
 En la lista siguiente se incluyen algunas directrices generales para controlar excepciones en la aplicación.  
  
-   Usar el código de control de excepciones \(bloques `try`\/`catch`\) correctamente.  También puede comprobar mediante programación si se da una condición que es probable que ocurra sin utilizar el control de excepciones.  
  
     **Comprobaciones mediante programación**.  En el ejemplo siguiente se usa una instrucción `if` para comprobar si se ha cerrado una conexión.  Si este no es el caso, el ejemplo cierra la conexión en lugar de producir una excepción.  
  
     [!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
     [!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
     [!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  
  
     **Control de excepciones**.  En el ejemplo siguiente se utiliza un bloque `try`\/`catch` para comprobar la conexión y producir una excepción si la conexión no está cerrada.  
  
     [!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
     [!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
     [!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  
  
     El método que se elija depende de la frecuencia con que se espera que se produzca el evento.  
  
    -   Utilice el control de excepciones si el evento no se produce con frecuencia, es decir, si el evento es muy excepcional e indica un error \(como un final de archivo inesperado\).  Cuando se usa el control de excepciones, se ejecuta menos código en condiciones normales.  
  
    -   Utilice el método mediante programación para comprobar si hay errores cuando el evento se produce con frecuencia y se puede considerar como parte de la ejecución normal.  Cuando se comprueba si hay errores mediante programación, se ejecuta más código cuando se produce una excepción.  
  
-   Utilice bloques `try`\/`catch` en torno a código que podría generar una excepción y utilice un bloque `finally` para limpiar los recursos, en caso necesario.  De esta manera, la instrucción `try` genera la excepción, la instrucción `catch` controla la excepción y la instrucción `finally` cierra o desasigna recursos tanto si se produce una excepción como si no.  
  
-   Ordene siempre las excepciones de los bloques `catch` de la más específica a la menos.  Con esta técnica se controla la excepción específica antes de que pase a un bloque `catch` más general.  
  
## Creación y generación de excepciones  
 La lista siguiente contiene las instrucciones para crear sus propias excepciones y cuándo deben producirse.  Para obtener más información, vea [Instrucciones de diseño para excepciones](../../../docs/standard/design-guidelines/exceptions.md).  
  
-   Diseñe las clases de manera que nunca se produzca una excepción en el uso normal.  Por ejemplo, una clase <xref:System.IO.FileStream> proporciona métodos que ayudan a determinar si se ha alcanzado el final del archivo.  Así se evita la excepción que se produce si se lee más allá del final del archivo.  En el ejemplo siguiente se muestra cómo leer hasta el final del archivo.  
  
     [!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
     [!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
     [!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  
  
-   Produzca excepciones en lugar de devolver un código de error o HRESULT.  
  
-   Devuelva NULL para los casos de errores muy frecuentes en lugar de generar una excepción.  Un caso de error muy común se puede considerar como un flujo de control normal.  Al devolver un valor null en estos casos, se minimiza el impacto en el rendimiento de una aplicación.  
  
-   Utilice, en la mayoría de los casos, los tipos de excepción de .NET Framework predefinidos.  Solo se deben introducir nuevas clases de excepción si no se puede aplicar ningún tipo predefinido.  
  
-   Inicie una excepción <xref:System.InvalidOperationException> si un conjunto de propiedades o una llamada a un método no resultan apropiados de acuerdo con el estado actual del objeto.  
  
-   Inicie una excepción <xref:System.ArgumentException> o una clase derivada de <xref:System.ArgumentException> si se pasan parámetros no válidos.  
  
-   Para la mayoría de las aplicaciones, derive excepciones personalizadas de la clase <xref:System.Exception>.  Al derivar de la clase <xref:System.ApplicationException>, no se aporta un valor significativo.  
  
-   Termine los nombres de clases de excepción con la palabra "Exception".  Por ejemplo:  
  
     [!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
     [!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
     [!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  
  
-   En C\# y C\+\+, al menos utilice tres constructores comunes al crear sus propias clases de excepciones: el constructor predeterminado, un constructor que tome un mensaje de cadena y un constructor que tome un mensaje de cadena y una excepción interna.  Para obtener un ejemplo, vea [Cómo: Crear excepciones definidas por el usuario](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md).  
  
    1.  <xref:System.Exception.%23ctor>, que utiliza valores predeterminados.  
  
    2.  <xref:System.Exception.%23ctor%28System.String%29>, que acepta un mensaje de cadena.  
  
    3.  <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, que acepta un mensaje de cadena y una excepción interna.  
  
-   Cuando cree excepciones definidas por el usuario, debe garantizar que los metadatos de las excepciones están disponibles para el código que se ejecute de forma remota, incluso cuando se produzcan excepciones en distintos dominios de aplicación.  Por ejemplo, supongamos que el dominio de aplicación A crea el dominio de aplicación B, que ejecuta código que produce una excepción.  Para que el dominio de aplicación A detecte y controle la excepción correctamente, debe poder encontrar el ensamblado que contiene la excepción que produce el dominio de aplicación B.  Si el dominio de aplicación B produce una excepción contenida en un ensamblado de su base de aplicación pero no de la base de la aplicación del dominio de aplicación A, este último dominio no encontrará la excepción y Common Language Runtime producirá una excepción <xref:System.IO.FileNotFoundException>.  Para evitar esta situación, puede implementar el ensamblado que contiene la información de la excepción de dos maneras:  
  
    -   Ponga el ensamblado en una base de aplicación compartida por los dos dominios de aplicación.  
  
         O bien  
  
    -   Si los dominios no comparten una base de aplicación común, firme el ensamblado que contiene la información de la excepción con un nombre seguro e impleméntelo en la caché global de ensamblados.  
  
-   Incluya una cadena descriptiva localizada en todas las excepciones.  El mensaje de error que ve el usuario deriva de la cadena descriptiva de la excepción que se produjo y no de la clase de excepción.  
  
-   Utilice mensajes de error gramaticalmente correctos, incluida la puntuación de cierre.  Cara oración de una cadena descriptiva de una excepción debe acabar con un punto.  Por ejemplo, "La tabla de registro se ha desbordado." es una cadena de descripción adecuada.  
  
-   Proporcione propiedades de <xref:System.Exception> para el acceso mediante programación.  Únicamente proporcione información adicional para una excepción \(además de la cadena descriptiva\) si hay un escenario de programación en que dicha información sea útil.  Por ejemplo, <xref:System.IO.FileNotFoundException> proporciona la propiedad <xref:System.IO.FileNotFoundException.FileName%2A>.  
  
-   El seguimiento de pila comienza en la instrucción en que se produce la excepción y termina en la instrucción `catch` que detecta la excepción.  Tenga esto en cuenta para decidir dónde ubicar una instrucción `throw`.  
  
-   Utilice métodos de compilador de excepciones.  Es habitual que una clase produzca la misma excepción desde distintos lugares de su implementación.  Para evitar el exceso de código, use métodos auxiliares que creen la excepción y la devuelvan.  Por ejemplo:  
  
     [!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
     [!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
     [!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
     También puede utilizar el constructor de la excepción para compilarla.  Esto está más indicado para clases de excepción globales, como <xref:System.ArgumentException>.  
  
-   Cuando produzca una excepción, elimine los resultados intermedios.  Los autores de llamadas deben poder asumir que no se producen efectos no deseados cuando se produce una excepción desde un método.  
  
## Vea también  
 [Excepciones](../../../docs/standard/exceptions/index.md)