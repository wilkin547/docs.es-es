---
title: "Patr&#243;n de Dispose | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Dispose (método)"
  - "instrucciones de diseño clases biblioteca [.NET Framework], Dispose (método)"
  - "instrucciones de diseño [.NET Framework] de bibliotecas de clases, Finalize (método)"
  - "personalizar el nombre del método Dispose"
  - "Finalize (método)"
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Patr&#243;n de Dispose
Todos los programas adquieren uno o más recursos del sistema, como memoria, identificadores de sistema o conexiones de base de datos, en el transcurso de su ejecución. Los desarrolladores tienen cuidado al usar estos recursos del sistema, porque debe liberarse tras adquirir y usar.  
  
 CLR proporciona compatibilidad para la administración automática de la memoria. Administra la memoria \(memoria asignada mediante el operador de C\# `new`\) no es necesario liberar de forma explícita. Se libera automáticamente por el recolector de elementos no utilizados \(GC\). Esto evita que los desarrolladores la tarea tediosa y difícil de liberación de memoria y ha sido una de las razones principales para la productividad sin precedentes proporcionada por .NET Framework.  
  
 Desafortunadamente, la memoria administrada es sólo uno de muchos tipos de recursos del sistema. Recursos distintos de la memoria administrada todavía deben liberar explícitamente y se conocen como recursos no administrados. El GC específicamente no fue diseñado para administrar estos recursos no administrados, lo que significa que la responsabilidad de administrar los recursos no administrados que se encuentra en manos de los desarrolladores.  
  
 El CLR proporciona ayuda en liberar recursos no administrados.<xref:System.Object?displayProperty=fullName> declara un método virtual <xref:System.Object.Finalize%2A> \(también denominado el finalizador\) que llama el GC antes de la memoria del objeto sea reclamada por el catálogo global y se puede invalidar para liberar recursos no administrados. Los tipos que reemplazan el finalizador se conocen como tipos susceptibles de finalización.  
  
 Aunque los finalizadores son eficaces en algunos escenarios de limpieza, tienen dos inconvenientes significativos:  
  
-   El finalizador se llama cuando el GC detecta que un objeto es apto para la recolección. Esto sucede durante un período indeterminado de tiempo después de que el recurso ya no es necesaria. El retraso entre cuando el desarrollador puede o desea liberar el recurso y la hora cuando el recurso se libera realmente el finalizador puede ser inaceptable en programas que adquieren varios recursos insuficientes \(recursos que se pueden agotar fácilmente\) o en casos en que los recursos son costosos de mantener en uso \(por ejemplo, los búferes de gran cantidad de memoria no administrada\).  
  
-   Cuando el CLR necesita llamar a un finalizador, debe posponer la colección de la memoria del objeto hasta la próxima de ida y vuelta de elementos no utilizados \(los finalizadores que se ejecute entre colecciones\). Esto significa que la memoria del objeto \(y todos los objetos que se hace referencia a\) no se lance durante un período de tiempo más largo.  
  
 Por lo tanto, basarse exclusivamente en los finalizadores podría no ser apropiado en muchos escenarios cuando es importante reclamar los recursos no administrados lo más rápidamente posible, cuando se trabaja con recursos insuficientes, o en escenarios de gran rendimiento alta en el que el GC agregado sobrecarga de finalización no es aceptable.  
  
 Proporciona el marco de la <xref:System.IDisposable?displayProperty=fullName> interfaz que debe implementarse para proporcionar a los programadores un método manual para liberar recursos no administrados como no son necesarios. También proporciona el <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> método que puede indicar el GC que un objeto se ha eliminado manualmente y no necesita finalizarse ya, en cuyo caso se puede reclamar la memoria del objeto anterior. Tipos que implementan la `IDisposable` interfaz se conocen como tipos de elementos desechables.  
  
 El patrón Dispose está diseñado para estandarizar el uso y la implementación de finalizadores y `IDisposable` interfaz.  
  
 El motivo principal para el modelo es reducir la complejidad de la implementación de la <xref:System.Object.Finalize%2A> y la <xref:System.IDisposable.Dispose%2A> métodos. La complejidad procede del hecho de que los métodos comparten algunas pero no todas las rutas de acceso de código \(las diferencias se describen más adelante en este capítulo\). Además, existen motivos históricos para algunos elementos del modelo relacionados con la evolución de la compatibilidad de idioma para la administración de recursos determinista.  
  
 **✓ hacer** implementar el patrón Dispose básico en tipos que contiene instancias de tipos de elementos desechables. Consulte la [patrón Dispose básico](#basic_pattern) sección para obtener más información sobre el patrón básico.  
  
 Si un tipo es responsable de la duración de otros objetos descartables, los desarrolladores necesitan una forma de deshacerse de ellos, demasiado. Uso del contenedor `Dispose` método es una forma cómoda para que esto sea posible.  
  
 **✓ hacer** implementar el patrón Dispose básico y proporcionar un finalizador en tipos de recursos de explotación que deben ser liberados explícitamente y que no tienen finalizadores.  
  
 Por ejemplo, se debe implementar el patrón en tipos de almacenamiento de los búferes de memoria no administrada. El [tipos susceptibles de finalización](#finalizable_types) sección describe directrices relacionadas con la implementación de finalizadores.  
  
 **✓ considere** implementa el patrón Dispose básico en clases que ellos mismos no mantenga los recursos no administrados u objetos descartables pero están probable que tenga los subtipos que lo hacen.  
  
 Un buen ejemplo de esto es la <xref:System.IO.Stream?displayProperty=fullName> clase. Aunque es una clase base abstracta que no contiene todos los recursos, la mayoría de sus subclases y por este motivo, que implementa este patrón.  
  
<a name="basic_pattern"></a>   
## Patrón de Dispose básica  
 La implementación básica del patrón implica implementar el `System.IDisposable` interfaz y declarar la `Dispose(bool)` método que implementa la lógica de limpieza de todos los recursos compartido entre el `Dispose` método y el finalizador opcional.  
  
 En el ejemplo siguiente se muestra una implementación sencilla del patrón básico:  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder(){  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        if (disposing){  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 El parámetro booleano `disposing` indica si el método se invoca desde el `IDisposable.Dispose` implementación o desde el finalizador. El `Dispose(bool)` implementación debe comprobar el parámetro antes de obtener acceso a otros objetos de referencia \(por ejemplo, el campo de recursos en el ejemplo anterior\). Estos objetos sólo deben tener acceso cuando se llama al método desde el `IDisposable.Dispose` implementación \(cuando el `disposing` parámetro es igual a true\). Si el método se invoca desde el finalizador \(`disposing` es false\), no se deben tener acceso a otros objetos. El motivo es que los objetos se finalizan en un orden impredecible y por lo tanto, o cualquiera de sus dependencias, podría haber finalizado.  
  
 Además, esta sección se aplica a las clases con una base que ya no implementan el patrón Dispose. Si se hereda de una clase que implemente el patrón, invalide el `Dispose(bool)` método para proporcionar la lógica de limpieza de recursos adicionales.  
  
 **✓ hacer** declara void virtual protegido `Dispose(bool disposing)` método centralizar toda la lógica relacionada con liberar recursos no administrados.  
  
 Todos los recursos deben limpiarse en este método. Se llama al método desde el finalizador de ambos y `IDisposable.Dispose` \(método\). El parámetro es false si se invoca desde dentro de un finalizador. Se debe usar para asegurarse de que cualquier código que se ejecuta durante la finalización no se tiene acceso a otros objetos susceptibles de finalización. En la siguiente sección se describen los detalles de implementación de finalizadores.  
  
```  
protected virtual void Dispose(bool disposing){  
    if (disposing){  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ hacer** implementar la `IDisposable` interfaz mediante la llamada a `Dispose(true)` seguido de `GC.SuppressFinalize(this)`.  
  
 La llamada a `SuppressFinalize` solo debería ocurrir si `Dispose(true)` se ejecuta correctamente.  
  
```  
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X no** realizar sin parámetros `Dispose` método virtual.  
  
 El `Dispose(bool)` método es el que debe reemplazarse por las subclases.  
  
```  
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
```  
  
 **X no** declarar las sobrecargas de los `Dispose` método distinto de `Dispose()` y `Dispose(bool)`.  
  
 `Dispose` debe considerarse una palabra reservada para codificar este patrón y evitar la confusión entre los implementadores, los usuarios y los compiladores. Algunos lenguajes pueden optar por implementar automáticamente este patrón de determinados tipos.  
  
 **✓ hacer** permitir la `Dispose(bool)` método al que llamar más de una vez. El método puede optar por no hacer nada después de la primera llamada.  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **Evitar X** producir una excepción desde `Dispose(bool)` excepto en situaciones críticas que se ha dañado el proceso que contiene \(pérdidas, estado compartido incoherente, etc.\).  
  
 Los usuarios esperan que una llamada a `Dispose` no producirá una excepción.  
  
 Si `Dispose` podría generar una excepción, no se ejecutará más lógica de limpieza del bloque finally. Para solucionar este problema, el usuario tendría que incluir todas las llamadas a `Dispose` \(dentro del bloque finally\!\) en un bloque try, lo que conduce a controladores de limpieza muy compleja. Si ejecuta un `Dispose(bool disposing)` método, nunca inicia una excepción si disposing es false. Esto finalizará el proceso si se ejecuta en un contexto de finalizador.  
  
 **✓ hacer** producir una <xref:System.ObjectDisposedException> de cualquier miembro que no se puede utilizar después de que se ha eliminado el objeto.  
  
```  
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething(){  
           if(disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
            ...  
    }  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **✓, considere la posibilidad de** de forma `Close()`, además el `Dispose()`, si es cerrar la terminología estándar en el área.  
  
 Al hacerlo, es importante que realice el `Close` idéntico de la implementación `Dispose` y considere implementar la `IDisposable.Dispose` método explícitamente.  
  
```  
public class Stream : IDisposable {  
    IDisposable.Dispose(){  
        Close();  
    }  
    public void Close(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## Tipos susceptibles de finalización  
 Tipos susceptibles de finalización son tipos que extienden el patrón Dispose básico reemplazando el finalizador y proporcionar la ruta de acceso de código de finalización en la `Dispose(bool)` \(método\).  
  
 Los finalizadores son considerablemente difíciles de implementar correctamente, principalmente porque no puede realizar determinadas suposiciones sobre el estado del sistema \(normalmente válidos\) durante su ejecución. Las instrucciones siguientes deben tenerse en consideración cuidadosa.  
  
 Tenga en cuenta que algunas de las instrucciones no sólo al aplican la `Finalize` \(método\), pero a cualquier código que llama desde un finalizador. En el caso del Dispose patrón básico definido anteriormente, esto significa la lógica que se ejecuta dentro de `Dispose(bool disposing)` cuando el `disposing` parámetro es false.  
  
 Si la clase base ya es susceptible de finalización e implementa el patrón Dispose básico, no debe invalidar `Finalize` nuevo. En su lugar, debe reemplazar simplemente la `Dispose(bool)` método para proporcionar la lógica de limpieza de recursos adicionales.  
  
 El código siguiente muestra un ejemplo de un tipo susceptibles de finalización:  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder(){  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing){  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing){ // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 **Evitar X** crear tipos susceptibles de finalización.  
  
 Considere detenidamente un caso en el que piensa que es necesario un finalizador. Hay un número real los costos asociados con instancias de los finalizadores, desde el punto de vista de complejidad de un código y el rendimiento. Prefieren usar contenedores de recursos como <xref:System.Runtime.InteropServices.SafeHandle> para encapsular los recursos no administrados cuando sea posible, en cuyo caso un finalizador se convierte en innecesario porque el contenedor es responsable de su propia limpieza de recursos.  
  
 **X no** susceptibles de finalización permite que los tipos de valor.  
  
 Obtengan finalizados realmente sólo los tipos de referencia CLR y, por tanto, se omitirá cualquier intento de colocar un finalizador en un tipo de valor. Los compiladores de C\+\+ y C\# cumple esta regla.  
  
 **✓ hacer** hacer susceptibles de finalización de un tipo si el tipo es responsable de liberar un recurso no administrado que no tiene su propio finalizador.  
  
 Al implementar el finalizador, simplemente llame `Dispose(false)` y coloque la lógica de limpieza de todos los recursos dentro de la `Dispose(bool disposing)` \(método\).  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        ...  
    }  
}  
```  
  
 **✓ hacer** implementa el patrón Dispose básico en cada tipo susceptibles de finalización.  
  
 Esto ofrece a los usuarios del tipo de medio para realizar explícitamente la limpieza determinista de los mismos recursos que es responsable el finalizador.  
  
 **X no** tener acceso a los objetos susceptibles de finalización en la ruta de acceso del código de finalizador porque no hay riesgo significativo que ya habrá finalizados.  
  
 Por ejemplo, un objeto susceptible de finalización A que tiene una referencia a otro objeto finalizable B no puede utilizar confiable B en del finalizador, o viceversa. Se llaman a los finalizadores en orden aleatorio \(aparte de una garantía de ordenación débil de finalización crítica\).  
  
 Además, tenga en cuenta que obtener recopilará los objetos almacenados en variables estáticas en ciertos puntos durante una descarga del dominio de aplicación o al salir del proceso. Obtener acceso a una variable estática que hace referencia a un objeto finalizable \(o llamar a un método estático que se puede usar los valores almacenados en variables estáticas\) podría no ser seguro if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=fullName> devuelve true.  
  
 **✓ hacer** realizar su `Finalize` método protegido.  
  
 Los desarrolladores de C\#, C\+\+ y VB.NET no es necesario preocuparse, porque los compiladores ayudan a aplicar esta directriz.  
  
 **X no** escape excepciones let de la lógica de finalizador, excepto los errores críticos del sistema.  
  
 Si se produce una excepción de un finalizador, el CLR se apagará de todo el proceso \(a partir de .NET Framework versión 2.0\), que impiden que otros finalizadores de ejecución y recursos de liberarse de una manera controlada.  
  
 **✓ considere** crear y utilizar un objeto susceptible de finalización crítico \(un tipo con una jerarquía de tipos que contiene <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>\) en situaciones en las que un finalizador absolutamente debe ejecutar incluso en caso de dominio de aplicación forzada descarga y cancelaciones de subprocesos.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>   
 <xref:System.Object.Finalize%2A?displayProperty=fullName>   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)   
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)