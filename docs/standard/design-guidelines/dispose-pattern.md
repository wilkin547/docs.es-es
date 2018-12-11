---
title: Patrón de Dispose
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: KrzysztofCwalina
ms.openlocfilehash: ee6e9898ae93e2e6628eadec150a3c9c05f5d9c5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147722"
---
# <a name="dispose-pattern"></a>Patrón de Dispose
Todos los programas adquieren uno o más recursos del sistema, como memoria, identificadores del sistema o las conexiones de base de datos, durante el transcurso de su ejecución. Los desarrolladores tienen que tener cuidado al usar estos recursos del sistema, porque debe liberarse tras la adquisición y uso.  
  
 El CLR proporciona compatibilidad para la administración automática de la memoria. Memoria administrada (memoria asignada mediante el operador de C# `new`) no tiene que liberarse de manera explícita. Se libera automáticamente por el recolector de elementos no utilizados (GC). Esto libera a los desarrolladores de la tarea tediosa y difícil de liberación de memoria y ha sido una de las razones principales para la productividad sin precedentes proporcionada por .NET Framework.  
  
 Por desgracia, la memoria administrada es solo uno de muchos tipos de recursos del sistema. Recursos distintos de la memoria administrada todavía se deben liberar explícitamente y se conocen como recursos no administrados. El GC específicamente no se diseñó para administrar estos recursos no administrados, lo que significa que la responsabilidad de administrar los recursos no administrados que se encuentra en manos de los desarrolladores.  
  
 El CLR proporciona algo de ayuda en liberar recursos no administrados. <xref:System.Object?displayProperty=nameWithType> declara un método virtual <xref:System.Object.Finalize%2A> (también denominado el finalizador) que se llama por el GC antes de la memoria del objeto sea reclamada por el GC y se puede invalidar para liberar recursos no administrados. Los tipos que reemplazan el finalizador se conocen como tipos susceptibles de finalización.  
  
 Aunque los finalizadores son eficaces en algunos escenarios de limpieza, tienen dos desventajas importantes:  
  
-   El finalizador se llama cuando GC detecta que un objeto es apto para la colección. Esto se produce en un período indeterminado de tiempo después de que el recurso ya no es necesaria. El retraso entre cuando el desarrollador puede o desea liberar el recurso y la hora cuando el recurso se libera realmente por el finalizador podría ser inaceptable en programas que adquieren varios recursos insuficientes (los recursos que pueden agotarse fácilmente) o casos en que los recursos son costosos de mantener en uso (por ejemplo, los búferes de gran cantidad de memoria no administrada).  
  
-   Cuando el CLR necesita llamar a un finalizador, debe posponer la recolección de la memoria del objeto hasta que ida y vuelta de la siguiente de elementos no utilizados (los finalizadores que se ejecute entre colecciones). Esto significa que la memoria del objeto (y todos los objetos que hace referencia a) no se liberará durante un periodo de tiempo.  
  
 Por lo tanto, depender exclusivamente de los finalizadores podría no ser adecuado en muchos escenarios cuando es importante reclamar los recursos no administrados tan pronto como sea posible, cuando se trabaja con recursos insuficientes, o en escenarios de alta de alto rendimiento en el que la sobrecarga de GC agregada no es aceptable de finalización.  
  
 El marco de trabajo proporciona el <xref:System.IDisposable?displayProperty=nameWithType> interfaz que debe implementarse de forma manual para liberar recursos no administrados como no son necesarios para los desarrolladores. También proporciona la <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> método que puede indicar el GC que un objeto se ha eliminado manualmente y no necesita ser finalizados, en cuyo caso se puede reclamar la memoria del objeto anteriormente. Los tipos que implementan la `IDisposable` interfaz se denominan tipos desechables.  
  
 El patrón Dispose está diseñado para estandarizar el uso y la implementación de finalizadores y el `IDisposable` interfaz.  
  
 La motivación principal para el patrón es reducir la complejidad de la implementación de la <xref:System.Object.Finalize%2A> y <xref:System.IDisposable.Dispose%2A> métodos. La complejidad surge del hecho de que los métodos comparten algunos, pero no todas las rutas de acceso de código (las diferencias se describen más adelante en el capítulo). Además, existen motivos históricos para algunos elementos del modelo relacionados con la evolución de la compatibilidad de idioma para la administración de recursos determinista.  
  
 **✓ DO** implementar el patrón de Dispose básico en tipos que contiene instancias de los tipos descartables. Consulte la [patrón Dispose básico](#basic_pattern) sección para obtener más información sobre el patrón básico.  
  
 Si un tipo es responsable de la duración de otros objetos desechables, los desarrolladores necesitan una manera para deshacerse de ellos, demasiado. Uso del contenedor `Dispose` método es una manera cómoda de hacer esto posible.  
  
 **✓ DO** implementar el patrón Dispose básico y se proporciona un finalizador en tipos que contiene recursos que deben ser liberados explícitamente y que no tienen los finalizadores.  
  
 Por ejemplo, se debe implementar el patrón en tipos de almacenamiento de los búferes de memoria no administrada. El [tipos finalizables](#finalizable_types) sección describen las directrices relacionadas con la implementación de los finalizadores.  
  
 **✓ CONSIDER** implementar el patrón de Dispose básicas en las clases que ellos mismos no mantenga los recursos no administrados o los objetos descartables pero están probables que tienen subtipos que realizar.  
  
 Un buen ejemplo de esto es el <xref:System.IO.Stream?displayProperty=nameWithType> clase. Aunque es una clase base abstracta que no contiene ningún recurso, la mayoría de sus subclases y por este motivo, implementa este patrón.  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>Patrón de Dispose básica  
 La implementación básica del patrón implica implementar el `System.IDisposable` interfaz y declarar la `Dispose(bool)` método que implementa la lógica de limpieza de todos los recursos deben compartirse entre el `Dispose` método y el finalizador opcional.  
  
 El ejemplo siguiente muestra una implementación sencilla del patrón básico:  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder() {  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposing) {  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 El parámetro booleano `disposing` indica si el método se invocó desde el `IDisposable.Dispose` implementación o desde el finalizador. El `Dispose(bool)` implementación debe comprobar el parámetro antes de acceder a otros objetos de referencia (por ejemplo, el campo de recursos en el ejemplo anterior). Solo se deben acceder a estos objetos cuando se llama al método desde el `IDisposable.Dispose` implementación (cuando el `disposing` parámetro es igual a true). Si el método se invoca desde el finalizador (`disposing` es false), no se deben tener acceso a otros objetos. El motivo es que los objetos se finalizan en un orden impredecible y por lo tanto, o cualquiera de sus dependencias, es posible que ya hayan finalizado.  
  
 Además, esta sección se aplica a las clases con una base que ya no implementan el patrón Dispose. Si se hereda de una clase que ya implementa el patrón, invalidar el `Dispose(bool)` método para proporcionar lógica de limpieza de recursos adicionales.  
  
 **✓ DO** declarar un `protected virtual void Dispose(bool disposing)` relacionado de método para centralizar toda la lógica para liberar recursos no administrados.  
  
 Todos los recursos deben limpiarse en este método. Se llama al método desde el finalizador de ambas y `IDisposable.Dispose` método. El parámetro es false si se invoca desde dentro de un finalizador. Se debe usar para asegurarse de que cualquier código que se ejecuta durante la finalización no se tiene acceso a otros objetos susceptibles de finalización. Detalles de la implementación de los finalizadores se describen en la sección siguiente.  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ DO** implementar la `IDisposable` interfaz llamando simplemente `Dispose(true)` seguido de `GC.SuppressFinalize(this)`.  
  
 La llamada a `SuppressFinalize` solo debería ocurrir si `Dispose(true)` se ejecuta correctamente.  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X DO NOT** realizar sin parámetros `Dispose` método virtual.  
  
 El `Dispose(bool)` método es lo que debe reemplazarse por las subclases.  
  
```csharp
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
```  
  
 **X DO NOT** declarar las sobrecargas de la `Dispose` otro método que `Dispose()` y `Dispose(bool)`.  
  
 `Dispose` debe considerarse una palabra reservada para ayudar a codificar este patrón y evitar la confusión entre los implementadores, los usuarios y los compiladores. Algunos lenguajes pueden optar por implementar automáticamente este patrón de determinados tipos.  
  
 **✓ DO** permitir la `Dispose(bool)` método al que llamar más de una vez. El método puede optar por no hacer nada tras la primera llamada.  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **X AVOID** producir una excepción desde `Dispose(bool)` excepto en situaciones críticas que se ha dañado el proceso que lo contiene (pérdidas, un estado compartido incoherente, etcetera).  
  
 Los usuarios esperan que una llamada a `Dispose` no producirá una excepción.  
  
 Si `Dispose` podría provocar una excepción, no se ejecutará más lógica de limpieza del bloque finally. Para solucionar este problema, el usuario tendría que incluir todas las llamadas a `Dispose` (en el bloque finally!) en un bloque try, lo que da lugar a los controladores de limpieza muy complejas. Si la ejecución de un `Dispose(bool disposing)` método, nunca produce una excepción si disposing es false. Si lo hace, finalizará el proceso si la ejecución dentro de un contexto de finalizador.  
  
 **✓ DO** producir una <xref:System.ObjectDisposedException> de cualquier miembro que no se puede utilizar una vez que se ha eliminado el objeto.  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething() {  
        if (disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
        ...  
    }  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **✓ CONSIDER** proporciona el método `Close()`, además el `Dispose()`, si es cerrar terminología estándar en el área.  
  
 Al hacerlo, es importante que realice la `Close` idéntico de la implementación `Dispose` y considere implementar la `IDisposable.Dispose` método explícitamente.  
  
```csharp
public class Stream : IDisposable {  
    IDisposable.Dispose() {  
        Close();  
    }  
    public void Close() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a>Tipos susceptibles de finalización  
 Tipos susceptibles de finalización son los tipos que amplían el patrón Dispose básico reemplazando el finalizador y proporcionar la ruta de acceso de código de finalización en el `Dispose(bool)` método.  
  
 Los finalizadores son considerablemente difíciles de implementar correctamente, principalmente porque no se puede realizar determinadas suposiciones sobre el estado del sistema (normalmente válidos) durante su ejecución. Las siguientes directrices se deben tener en consideración cuidadosa.  
  
 Tenga en cuenta que algunas de las instrucciones no sólo al aplican el `Finalize` método, pero para que cualquier código que llama desde un finalizador. En el caso del Dispose patrón básico definido previamente, esto significa lógica que se ejecuta dentro de `Dispose(bool disposing)` cuando el `disposing` parámetro es false.  
  
 Si la clase base ya es susceptibles de finalización e implementa el patrón Dispose básico, no debe invalidar `Finalize` nuevo. En su lugar, debe reemplazar simplemente la `Dispose(bool)` método para proporcionar lógica de limpieza de recursos adicionales.  
  
 El código siguiente muestra un ejemplo de un tipo susceptibles de finalización:  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder() {  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing) { // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    public void Dispose() {
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 **X AVOID** realicen tipos susceptibles de finalización.  
  
 Considere un caso en el que piensa que se necesita un finalizador. Hay un número real los costos asociados con instancias con los finalizadores, desde la perspectiva de complejidad de un código y el rendimiento. Prefiere el uso de contenedores de recursos, como <xref:System.Runtime.InteropServices.SafeHandle> para encapsular los recursos no administrados que sea posible, en cuyo caso un finalizador deja de ser necesario porque el contenedor es responsable de su propia limpieza de recursos.  
  
 **X DO NOT** que los tipos de valor susceptibles de finalización.  
  
 Solo los tipos de referencia realmente obtengan finaliza con CLR y, por tanto, se omitirá cualquier intento de colocar un finalizador en un tipo de valor. Los compiladores de C++ y C# aplican esta regla.  
  
 **✓ DO** que un tipo susceptibles de finalización si el tipo es responsable de liberar un recurso no administrado que no tiene su propio finalizador.  
  
 Al implementar el finalizador, basta con llamar a `Dispose(false)` y coloque la lógica de limpieza de todos los recursos dentro de la `Dispose(bool disposing)` método.  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing) {
        ...  
    }  
}  
```  
  
 **✓ DO** implementar el patrón de Dispose básico en todos los tipos susceptibles de finalización.  
  
 Esto proporciona a los usuarios del tipo de un medio para realizar explícitamente una limpieza determinista de los mismos recursos que es responsable el finalizador.  
  
 **X DO NOT** tener acceso a los objetos susceptibles de finalización en la ruta de acceso del código de finalizador, porque no hay riesgo significativo que ya habrá finalizados.  
  
 Por ejemplo, un objeto susceptible de finalización A que tiene una referencia a otro objeto finalizable B confiable no puede usar B en del finalizador, o viceversa. Los finalizadores se llaman en orden aleatorio (aparte de una garantía de ordenación débil para finalización crítica).  
  
 Además, tenga en cuenta que los objetos almacenados en variables estáticas obtener recopilarán en ciertos puntos durante una descarga del dominio de aplicación o al salir del proceso. Obtener acceso a una variable estática que hace referencia a un objeto susceptible de finalización (o llamar a un método estático que se puede usar los valores almacenados en variables estáticas) podría no ser seguro if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> devuelve true.  
  
 **✓ DO** realizar su `Finalize` método protegido.  
  
 Los desarrolladores de C#, C++ y VB.NET no es necesario que se preocupe, porque los compiladores ayudan a aplicar esta directriz.  
  
 **X DO NOT** escape permiten excepciones de la lógica de finalizador, excepto los errores críticos del sistema.  
  
 Si se produce una excepción de un finalizador, el CLR se apagará de todo el proceso (a partir de .NET Framework versión 2.0), impide que otros finalizadores ejecutando y los recursos de liberarse de manera controlada.  
  
 **✓ CONSIDER** crear y usar un objeto susceptibles de finalización crítico (un tipo con una jerarquía de tipos que contiene <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) para situaciones en que un finalizador absolutamente debe ejecutar incluso frente a la fuerza del dominio de aplicación forzada y subprocesos se anula.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)  
- [Recolección de elementos no utilizados](../../../docs/standard/garbage-collection/index.md)
